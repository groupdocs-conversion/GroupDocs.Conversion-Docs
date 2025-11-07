---
id: convert-to-project-management-with-advanced-options
url: conversion/net/convert-to-project-management-with-advanced-options
title: Convert to Project Management formats with advanced options
weight: 17
description: "Learn about ProjectManagementConvertOptions class for Project Management file formats (MPP, MPT, MPX, XER) in GroupDocs.Conversion for .NET."
keywords: Convert to Project, Convert to MPP, Convert to MPX, Microsoft Project conversion, Primavera conversion
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

GroupDocs.Conversion provides the [ProjectManagementConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/projectmanagementconvertoptions) class to specify Project Management file format conversion settings.

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

## Conversion Examples

ProjectManagementConvertOptions supports conversion between project management formats. The following examples demonstrate common conversions.

### MPP to MPX

Convert a Microsoft Project binary file (MPP) to MPX (Project Exchange Format):

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;

string sourceFile = "construction-plan.mpp";
string outputFile = "construction-plan.mpx";

using (var converter = new Converter(sourceFile))
{
    var options = new ProjectManagementConvertOptions
    {
        Format = ProjectManagementFileType.Mpx
    };
    converter.Convert(outputFile, options);
}
```

### XER (Primavera) to MPX

Convert a Primavera P6 file (XER) to Microsoft Project Exchange format (MPX):

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;

string sourceFile = "engineering-project.xer";
string outputFile = "engineering-project.mpx";

using (var converter = new Converter(sourceFile))
{
    var options = new ProjectManagementConvertOptions
    {
        Format = ProjectManagementFileType.Mpx
    };
    converter.Convert(outputFile, options);
}
```

## Format Support Notes

Project Management to Project Management conversions are supported for select format combinations:
- MPP → MPX, XER
- MPT → MPX, XER
- MPX → MPP, XER (some restrictions apply)
- XER → MPX, MPP

**Note:** To convert FROM Project Management formats to PDF or images, use [PdfConvertOptions]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-to-pdf-with-advanced-options.md" >}}) or [ImageConvertOptions]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-to-image-with-advanced-options.md" >}}).

## More Resources

- [API Reference: ProjectManagementConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/projectmanagementconvertoptions)
- [API Reference: ProjectManagementFileType](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/projectmanagementfiletype)
- [Supported File Formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}})
