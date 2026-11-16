---
id: remove-office-metadata
url: conversion/java/use-cases/remove-office-metadata/
title: "Prepare Office Reports for External Sharing in Java"
description: "Compare retained and cleared Office properties when converting DOCX, XLSX and PPTX to PDF with Java 26.10."
keywords: ["remove document metadata Java", "Office to PDF Java", "clear custom document properties", "DOCX metadata removal Java", "XLSX metadata removal Java", "PowerPoint metadata removal Java", "GroupDocs.Conversion Java", "Java 26.10"]
productName: GroupDocs.Conversion for Java
author: GroupDocs Team
draft: false
toc: true
hideChildren: false
---

# Prepare Office Reports for External Sharing in Java

{{< alert style="info" >}}
Companion sample repository (pending publication):
[remove-office-properties-java](https://github.com/groupdocs-conversion/remove-office-properties-java)
{{< /alert >}}

Office property cleanup is a GroupDocs.Conversion capability for Java that removes selected source document properties while preparing conversion output. This use case compares a retained-property export with a cleaned export. It covers Word, Excel and PowerPoint inputs on version 26.10. Each input contains fictional values for an author, a title and a custom reference. The application produces PDF deliverables and Office comparison copies. You can inspect the two sets before applying the policy to your own reporting workflow.

## Introduction

An external report needs a defined property policy. The text may be ready for a customer while its author field still names an internal review team. A custom reference can also be meaningful inside your company and unnecessary outside it. Exporting the document does not, by itself, prove that those values disappeared. This guide treats conversion and property verification as separate responsibilities. We check the source markers after each run rather than infer success from a clean-looking page.

Visible text, notes, comments and embedded files require separate review. The sample saves new outputs in Result/ without modifying the three source files.

## What This Guide Covers

You will configure typed load options, export three Office formats and inspect control outputs. The Java classes are WordProcessingLoadOptions, SpreadsheetLoadOptions and PresentationLoadOptions. Each exposes setClearBuiltInDocumentProperties and setClearCustomDocumentProperties. Both flags are set before the Converter opens its input. The sample applies the same policy across the three families while keeping their format-specific loaders explicit.

### Prerequisites and installation

Use JDK 11 or 17, Maven and the included fictional documents. The demonstrated dependency is com.groupdocs:groupdocs-conversion:26.10. A license covering this release is needed to reproduce unrestricted output; otherwise evaluation limits can interrupt the comparison. The project supplies pom.xml with the GroupDocs repository and an executable main class. Run the application from the directory containing that file.

```sh
mvn compile exec:java
```

OfficeMetadataDemo.java contains the feature methods under src/main/java/com/groupdocs/demo/. PropertyChecks.java is a separate verification utility. documents/ holds report.docx, report.xlsx and report.pptx. RUN.md explains the license placeholder and execution command. Result/ appears at runtime and is excluded from version control.

## Quick Decision Matrix

| Requirement | Policy |
|---|---|
| Preserve source properties for an internal copy | Pass false to both flags |
| Remove built-in and custom properties for an external copy | Pass true to both flags |
| Verify removal independently of page appearance | Inspect the control Office output |
| Remove personal information in visible content | Use a separate content-review process |
| Clean an existing PDF source with this example | Outside the tested workflow |

## Method Comparison Overview

### Which properties does this workflow remove?

The workflow clears built-in and custom source document properties when both load-option flags are true. In the included Office fixtures, the checked values are the author, title and InternalReference property. The same-format control outputs lose those markers, and their PDF exports lose Author and Title. Generated PDF Producer information can remain, so a successful run does not mean every metadata field is empty.

The settings control categories rather than individual field names. An archival copy may need provenance that an external copy should omit. I would keep those destinations distinct and name the cleaned file explicitly.

## Detailed Method Analysis

### Method 1: Word report conversion

#### How It Works

convertWord receives a boolean named clear. WordProcessingLoadOptions carries that value into both property settings. The lambda supplies those options when Converter loads documents/report.docx. The method first writes a PDF and then a DOCX comparison copy. Those outputs share a retained or clean suffix, making the policy visible in their filenames.

#### When to Use

Choose this path for a Word-authored report that will leave the authoring environment as PDF. Use the DOCX output as a test artifact rather than another customer deliverable. Its OOXML property parts offer a direct check of the source markers. Neither output establishes that the visible report text is suitable for release.

#### Implementation

The first block shows the complete extracted method body. It belongs inside a method with a boolean clear parameter and the relevant GroupDocs imports. The application creates Result/ before calling it. To select the external-copy policy, the caller passes true:

```java
OfficeMetadataDemo.convertWord(true);
```

```java
WordProcessingLoadOptions options = new WordProcessingLoadOptions();
options.setClearBuiltInDocumentProperties(clear);
options.setClearCustomDocumentProperties(clear);
String target = "Result/docx-" + (clear ? "clean" : "retained");
try (Converter converter = new Converter("documents/report.docx", () -> options)) {
    converter.convert(target + ".pdf", new PdfConvertOptions());
    converter.convert(target + ".docx", new WordProcessingConvertOptions());
}
```

#### Pros and Cons

The Word path keeps the cleanup decision next to loading, so the PDF and control copy use the same source policy. The extra DOCX is useful during verification but adds output that must be managed. It should not be silently included in the customer's delivery package. No elapsed-time claim is made for producing the pair.

### Method 2: Spreadsheet report conversion

#### How It Works

convertExcel uses SpreadsheetLoadOptions with the same two boolean settings. The input is documents/report.xlsx, not the PDF created by the Word method. PdfConvertOptions selects the deliverable format, while SpreadsheetConvertOptions creates the XLSX control. Metadata decisions are independent of spreadsheet pagination. Review both concerns before distributing a report whose columns might cross page boundaries.

#### When to Use

This variant fits a reporting pipeline that already receives Excel workbooks. A worksheet can contain a suitable report while workbook properties still retain internal ownership information. The sample tests property values separately from the cells. Empty spacing and page setup remain matters for the layout policy.

#### Implementation

The caller selects cleanup in the same way as for Word. Each call loads a new Converter and closes it after writing the pair. The two blocks separate policy selection from the implementation. Keep the typed SpreadsheetLoadOptions when substituting your own input.

```java
OfficeMetadataDemo.convertExcel(true);
```

```java
SpreadsheetLoadOptions options = new SpreadsheetLoadOptions();
options.setClearBuiltInDocumentProperties(clear);
options.setClearCustomDocumentProperties(clear);
String target = "Result/xlsx-" + (clear ? "clean" : "retained");
try (Converter converter = new Converter("documents/report.xlsx", () -> options)) {
    converter.convert(target + ".pdf", new PdfConvertOptions());
    converter.convert(target + ".xlsx", new SpreadsheetConvertOptions());
}
```

#### Pros and Cons

The XLSX control confirms that the custom marker was removed at the Office-property level. It does not verify formulas, charts or every output page. Inspect the PDF layout with your representative workbook. The included sparse fixture demonstrates metadata behavior rather than a production reporting specification.

### Method 3: Presentation report conversion

#### How It Works

convertPowerPoint loads the PPTX fixture through PresentationLoadOptions. It applies the two property flags before conversion and writes PDF plus a PPTX comparison. The control carries the same format as its source so PropertyChecks can read the standard property parts. A slide that looks unchanged can still have different document properties. That distinction is the reason for testing both file content and property storage.

#### When to Use

Use this route when a presentation becomes a customer-facing PDF attachment. The fixture is a fictional one-slide report with document-level markers. Speaker notes, slide text and embedded objects are not evaluated by the property check. Include them in a separate review if your delivery policy covers them.

#### Implementation

Run the presentation method with the required boolean policy. Output names distinguish the cleaned and retained sets. The extracted body uses only the typed load options and conversion APIs shown here. The application's main method handles directory creation and license setup outside this snippet.

```java
OfficeMetadataDemo.convertPowerPoint(true);
```

```java
PresentationLoadOptions options = new PresentationLoadOptions();
options.setClearBuiltInDocumentProperties(clear);
options.setClearCustomDocumentProperties(clear);
String target = "Result/pptx-" + (clear ? "clean" : "retained");
try (Converter converter = new Converter("documents/report.pptx", () -> options)) {
    converter.convert(target + ".pdf", new PdfConvertOptions());
    converter.convert(target + ".pptx", new PresentationConvertOptions());
}
```

#### Pros and Cons

The same policy applies across the three Office families without replacing their loaders with a guessed generic type. Maintaining separate methods makes the format coverage visible to reviewers. It also means a newly added input family needs its own verified example. Benchmarking conversion speed is outside this guide.

## Side-by-Side Feature Comparison

| Input | Loader | Control output | Deliverable |
|---|---|---|---|
| DOCX | WordProcessingLoadOptions | DOCX | PDF |
| XLSX | SpreadsheetLoadOptions | XLSX | PDF |
| PPTX | PresentationLoadOptions | PPTX | PDF |

## Best Practices and Recommendations

Inspect the retained output first. If a marker is already absent there, its absence in the clean output proves nothing about the flag. PropertyChecks therefore requires the marker in one result and rejects it in the other. This positive-and-negative comparison is more informative than a single empty-field assertion. We also inspected PDF Author and Title separately with Poppler pdfinfo.

## Common Pitfalls and How to Avoid Them

Do not advertise this as complete personal-data removal. The title of a report can appear in both document properties and visible text. Clearing one location leaves the other intact. Keep license files outside the repository, and do not distribute the retained controls by mistake.

## FAQ

### Does the example cover PDF input?

No. The demonstrated sources are DOCX, XLSX and PPTX. A separate 26.10 PDF-input check failed when built-in property clearing was enabled. This guide limits its claims to the Office paths that completed successfully.

### Must the exported PDF have no properties at all?

No. Generated Producer information can remain after the source markers disappear. Check the properties named by your policy rather than requiring an entirely empty metadata dictionary. Review visible content independently.

## Conclusion

Run the fixture with both policies before adapting it. Confirm the six Office control checks and inspect the three cleaned PDFs. Then replace one fictional input at a time with an approved representative document. Keep the property policy explicit in the export step.

## See Also

- [Companion Office cleanup article](https://blog.groupdocs.com/conversion/remove-office-metadata-java/)
- [Complete Java sample](https://github.com/groupdocs-conversion/remove-office-properties-java)
- [GroupDocs.Conversion Java documentation](https://docs.groupdocs.com/conversion/java/)
