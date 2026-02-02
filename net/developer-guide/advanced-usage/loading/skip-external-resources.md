---
id: skip-loading-external-resources
url: conversion/net/skip-loading-external-resources
title: Skip loading of external resources
weight: 4
description: "Learn this article and check how to restrict loading of external resources during conversion"
keywords: Restrict loading of external resources during conversion, external resources, Skip loading of external resources during conversion, Loading external resources
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

## What are external resources?

*External resources* refer to various types of content or files that are not directly embedded within the document but are instead referenced and loaded from external locations. These resources enhance the functionality, appearance, and interactivity of the document. Common external resources include images, audio, video, fonts, CSS, scripts, frameworks, and so on. **GroupDocs.Conversion** considers external any resource that a document is trying to load from an external URL.

Utilizing external resources optimizes the performance, maintainability, and scalability of web pages and other documents. These resources are typically cached by browsers, which can reduce the load time of subsequent visits to a website. However, relying too heavily on external resources can also introduce dependencies and potential points of failure if the external sources become unavailable.

## Security considerations

Loading external resources from untrusted documents can pose security risks:

* **Server-Side Request Forgery (SSRF)**: A malicious document could contain references to internal network resources, potentially allowing attackers to probe or access internal services.
* **NTLM credential leaks**: Documents with UNC paths (e.g., `\\server\share`) could trigger automatic NTLM authentication, potentially leaking credentials.
* **Data exfiltration**: External resources could be used to track document access or exfiltrate data.

To mitigate these risks, [**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) implements a **secure by default** approach - the `SkipExternalResources` property is set to `true` by default in all supporting load options classes.

## Supported document types

The external resource loading control is available for the following document types:

| Document Type | LoadOptions Class |
|---------------|-------------------|
| Web/HTML | [WebLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/webloadoptions) |
| Word Processing | [WordProcessingLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/wordprocessingloadoptions) |
| Presentations | [PresentationLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/presentationloadoptions) |
| Spreadsheets | [SpreadsheetLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions) |
| Email | [EmailLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/emailloadoptions) |
| SVG | [SvgLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/svgloadoptions) |

All these classes implement the [IResourceLoadingOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/iresourceloadingoptions) interface, which defines the `SkipExternalResources` and `WhitelistedResources` properties.

## Restricting external resources

By default, `SkipExternalResources` is set to `true`, which means external resources are already blocked. If you have previously enabled external resource loading and want to restrict it again, set the `SkipExternalResources` property to `true`.

The following code snippets show how to skip loading of external resources for different document types:

### Web/HTML documents

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

var loadOptions = new WebLoadOptions
{
    SkipExternalResources = true
};
using (var converter = new Converter("sample.html", (LoadContext loadContext) => loadOptions))
{
    var options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

### Word processing documents

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

var loadOptions = new WordProcessingLoadOptions
{
    SkipExternalResources = true
};
using (var converter = new Converter("sample.docx", (LoadContext loadContext) => loadOptions))
{
    var options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

### Presentation documents

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

var loadOptions = new PresentationLoadOptions
{
    SkipExternalResources = true
};
using (var converter = new Converter("sample.pptx", (LoadContext loadContext) => loadOptions))
{
    var options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

### Spreadsheet documents

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

var loadOptions = new SpreadsheetLoadOptions
{
    SkipExternalResources = true
};
using (var converter = new Converter("sample.xlsx", (LoadContext loadContext) => loadOptions))
{
    var options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

### Email documents

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

var loadOptions = new EmailLoadOptions
{
    SkipExternalResources = true
};
using (var converter = new Converter("sample.eml", (LoadContext loadContext) => loadOptions))
{
    var options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

### SVG documents

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

var loadOptions = new SvgLoadOptions
{
    SkipExternalResources = true
};
using (var converter = new Converter("sample.svg", (LoadContext loadContext) => loadOptions))
{
    var options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

## Allowlisting specific external resources

Sometimes you may want to skip loading most of the external resources, but still load some particular resources from trusted sources.

To allow-list specific resources during the conversion, use the `WhitelistedResources` property. This property accepts a list of strings containing portions of URLs to be allowed. The `WhitelistedResources` property is effective only when the `SkipExternalResources` property is set to `true`.

The following code snippet shows how to load JPG and JPEG images and any resources from the `example.com` domain while restricting all other external resources:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

var loadOptions = new WebLoadOptions
{
    SkipExternalResources = true,
    WhitelistedResources = new List<string> { "jpg", "jpeg", "example.com" }
};
using (var converter = new Converter("sample.html", (LoadContext loadContext) => loadOptions))
{
    var options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

The same approach works for all supported document types. For example, to allow specific resources when converting an email document:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

var loadOptions = new EmailLoadOptions
{
    SkipExternalResources = true,
    WhitelistedResources = new List<string> { "trusted-domain.com", ".png", ".jpeg" }
};
using (var converter = new Converter("newsletter.eml", (LoadContext loadContext) => loadOptions))
{
    var options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

Resources matching any entry in the whitelist will be loaded normally, while all other external resources will be skipped.

## Enabling external resources loading

If you need to load all external resources (not recommended for untrusted documents), set `SkipExternalResources` to `false`:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

var loadOptions = new WebLoadOptions
{
    SkipExternalResources = false
};
using (var converter = new Converter("trusted-document.html", (LoadContext loadContext) => loadOptions))
{
    var options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```
