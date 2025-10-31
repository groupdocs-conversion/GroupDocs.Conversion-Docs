---
id: convert-to-cad-with-advanced-options
url: conversion/net/convert-to-cad-with-advanced-options
title: Convert to CAD formats with advanced options
weight: 19
description: "Learn about CadConvertOptions class for CAD file formats (DWG, DXF, DWF) in GroupDocs.Conversion for .NET."
keywords: Convert to CAD, Convert to DWG, Convert to DXF, CAD conversion
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

GroupDocs.Conversion provides the [CadConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/cadconvertoptions) class to specify CAD file format conversion settings. This class implements [IPagedConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/ipagedconvertoptions) for page selection and [IPageSizeConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/ipagesizeconvertoptions) for page sizing.

## Supported CAD Formats

The following CAD (Computer-Aided Design) formats are recognized:

| Format | Extension | Description |
|--------|-----------|-------------|
| **DWG** | .dwg | AutoCAD Drawing Database (binary format) |
| **DXF** | .dxf | Drawing Exchange Format (ASCII/binary) |
| **DWF** | .dwf | Design Web Format (compressed 2D/3D) |
| **DWFX** | .dwfx | Design Web Format XPS |
| **DWT** | .dwt | AutoCAD Drawing Template |
| **DGN** | .dgn | MicroStation Design File |
| **IFC** | .ifc | Industry Foundation Classes (BIM) |
| **STL** | .stl | Stereolithography (3D printing) |
| **PLT** | .plt | HPGL Plot File |
| **IGS** | .igs | IGES Drawing File |
| **CF2** | .cf2 | Common File Format (3D package designs) |

## Properties

**[Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions-1/format/)** - Specifies the desired CAD file format. Available options are: *Dwg, Dxf, Dwf, Dwfx, Dwt, Dgn, Ifc, Stl, Plt, Igs, Cf2*.

**[PageSize](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/ipagesizeconvertoptions/pagesize)** - Sets the page size (A3, A4, Letter, etc.) for the output document.

**[PageWidth](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/ipagesizeconvertoptions/pagewidth)** - Sets custom page width in points. When set, PageSize automatically changes to Custom.

**[PageHeight](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/ipagesizeconvertoptions/pageheight)** - Sets custom page height in points. When set, PageSize automatically changes to Custom.

**[PageNumber](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/ipagedconvertoptions/pagenumber)** - Specifies the starting page number for conversion.

**[PagesCount](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/ipagedconvertoptions/pagescount)** - Specifies the number of pages to convert.

## API Structure

The following example shows the API structure for CadConvertOptions:

```csharp
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;

// Create options object
CadConvertOptions options = new CadConvertOptions
{
    Format = CadFileType.Dwg,
    PageSize = GroupDocs.Conversion.Options.Convert.PageSize.A4,
    PageNumber = 1,      // Starting page
    PagesCount = 10      // Number of pages to process
};
```

## Conversion Examples

CadConvertOptions supports conversion between CAD formats. The following examples demonstrate common conversions.

### DWG to DXF

Convert an AutoCAD DWG file to DXF (Drawing Exchange Format):

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;

string sourceFile = "drawing.dwg";
string outputFile = "drawing.dxf";

using (var converter = new Converter(sourceFile))
{
    var options = new CadConvertOptions
    {
        Format = CadFileType.Dxf
    };
    converter.Convert(outputFile, options);
}
```

### DWG to DWF

Convert a DWG file to DWF (Design Web Format):

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;

string sourceFile = "blueprint.dwg";
string outputFile = "blueprint.dwf";

using (var converter = new Converter(sourceFile))
{
    var options = new CadConvertOptions
    {
        Format = CadFileType.Dwf
    };
    converter.Convert(outputFile, options);
}
```

## Page Size Options

Control output page dimensions using PageSize or custom dimensions:

### Using Standard Page Size

Set a standard page size (A4, A3, Letter, etc.):

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;

string sourceFile = "technical-drawing.dwg";
string outputFile = "technical-drawing-a4.dxf";

using (var converter = new Converter(sourceFile))
{
    var options = new CadConvertOptions
    {
        Format = CadFileType.Dxf,
        PageSize = PageSize.A4
    };
    converter.Convert(outputFile, options);
}
```

### Using Custom Page Dimensions

Define custom page width and height in points:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;

string sourceFile = "floor-plan.dwg";
string outputFile = "floor-plan-custom.dxf";

using (var converter = new Converter(sourceFile))
{
    var options = new CadConvertOptions
    {
        Format = CadFileType.Dxf,
        PageWidth = 800,   // Width in points
        PageHeight = 600   // Height in points
    };
    converter.Convert(outputFile, options);
}
```

## Format Support Notes

CAD to CAD conversions are supported for select format combinations:
- DWG → DXF, DWF
- DGN → DXF, DWF
- DWT → DXF, DWF
- STL → DXF, DWF (limited support)
- Other CAD formats → DXF, DWF (varies by format)

Conversions from non-CAD formats (PDF, Word, Excel) to CAD formats are not supported.

**Note:** To convert FROM CAD formats to PDF or images, use [PdfConvertOptions]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-to-pdf-with-advanced-options.md" >}}) or [ImageConvertOptions]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-to-image-with-advanced-options.md" >}}).

## More Resources

- [API Reference: CadConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/cadconvertoptions)
- [API Reference: CadFileType](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/cadfiletype)
- [Convert CAD Formats]({{< ref "conversion/net/developer-guide/basic-usage/convert/cad.md" >}})
- [Supported File Formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}})
