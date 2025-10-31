---
id: convert-to-project-management-with-advanced-options
url: conversion/net/convert-to-project-management-with-advanced-options
title: Convert to Project Management formats with advanced options
weight: 17
description: "Learn how to convert documents to Microsoft Project and Primavera formats (MPP, MPT, MPX, XER) using GroupDocs.Conversion for .NET."
keywords: Convert to Project, Convert to MPP, Convert to MPX, Microsoft Project conversion, Primavera conversion
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

GroupDocs.Conversion provides the [ProjectManagementConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/projectmanagementconvertoptions) class to control conversion to project management file formats.

## Supported Project Management Formats

The following project management formats are supported:

| Format | Extension | Description | Application |
|--------|-----------|-------------|-------------|
| **MPP** | .mpp | Microsoft Project binary format | Microsoft Project |
| **MPT** | .mpt | Microsoft Project template | Microsoft Project |
| **MPX** | .mpx | Microsoft Project Exchange (ASCII format) | Microsoft Project & Primavera |
| **XER** | .xer | Primavera P6 format | Primavera P6 |

## Properties

**[Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions-1/format/)** - Specifies the desired project management file format. Available options are: *Mpp, Mpt, Mpx, Xer*.

## Converting FROM Project Management Formats

You can convert project management files to other formats like PDF. This is useful for sharing project schedules with stakeholders.

### Convert MPX to PDF

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;

// Load the source MPX file
using (Converter converter = new Converter("project-schedule.mpx"))
{
    // Set PDF convert options
    PdfConvertOptions options = new PdfConvertOptions();

    // Convert and save
    converter.Convert("project-schedule.pdf", options);
}
```

### Convert MPP to PDF

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;

// Load the source MPP file
using (Converter converter = new Converter("construction-plan.mpp"))
{
    // Set PDF convert options
    PdfConvertOptions options = new PdfConvertOptions();

    // Convert and save
    converter.Convert("construction-plan.pdf", options);
}
```

### Convert XER (Primavera) to PDF

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;

// Load the source Primavera XER file
using (Converter converter = new Converter("engineering-project.xer"))
{
    // Set PDF convert options
    PdfConvertOptions options = new PdfConvertOptions();

    // Convert and save
    converter.Convert("engineering-project.pdf", options);
}
```

## ProjectManagementConvertOptions Usage

The ProjectManagementConvertOptions class is used to specify the target project management format when converting TO project formats.

```csharp
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;

// Specify target format for project management conversion
ProjectManagementConvertOptions options = new ProjectManagementConvertOptions
{
    Format = ProjectManagementFileType.Mpx
};
```

**Note:** Conversion from standard document formats (PDF, Word, Excel) to project management formats is not supported. Project management formats require specific data structures for tasks, resources, dependencies, and timelines that are not present in general documents.

## More Resources

- [API Reference: ProjectManagementConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/projectmanagementconvertoptions)
- [API Reference: ProjectManagementFileType](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/projectmanagementfiletype)
- [Supported File Formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}})
- [Common Conversion Options]({{< ref "conversion/net/developer-guide/advanced-usage/converting/common-conversion-options/_index.md" >}})
