---
id: convert-to-3d-with-advanced-options
url: conversion/net/convert-to-3d-with-advanced-options
title: Convert to 3D formats with advanced options
weight: 21
description: "Learn about ThreeDConvertOptions class for 3D file formats (FBX, OBJ, GLTF, 3DS, U3D) in GroupDocs.Conversion for .NET."
keywords: Convert to FBX, Convert to OBJ, Convert to GLTF, 3D conversion, 3D model conversion
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

GroupDocs.Conversion provides the [ThreeDConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/threedconvertoptions) class to specify 3D file format conversion settings. This class implements [IPagedConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/ipagedconvertoptions) for page selection support.

## Supported 3D Formats

The following 3D (Three-Dimensional) file formats are supported:

| Format | Extension | Description |
|--------|-----------|-------------|
| **FBX** | .fbx | Autodesk FilmBox (motion capture, animation) |
| **3DS** | .3ds | 3D Studio (DOS) mesh file format |
| **3MF** | .3mf | 3D Manufacturing Format |
| **AMF** | .amf | Additive Manufacturing File Format |
| **ASE** | .ase | Autodesk ASCII Scene Export |
| **DAE** | .dae | Digital Asset Exchange (COLLADA) |
| **DRC** | .drc | Google Draco compressed 3D |
| **FBX** | .fbx | Autodesk Filmbox |
| **GLTF** | .gltf | GL Transmission Format (JSON) |
| **GLB** | .glb | Binary GL Transmission Format |
| **OBJ** | .obj | Wavefront 3D Object File |
| **PLY** | .ply | Polygon File Format |
| **RVM** | .rvm | AVEVA Plant Design Model |
| **U3D** | .u3d | Universal 3D File Format |
| **USD** | .usd | Universal Scene Description |
| **USDZ** | .usdz | Universal Scene Description (ZIP) |
| **VRML** | .vrml | Virtual Reality Modeling Language |
| **X** | .x | DirectX 3D Graphics (legacy) |
| **JT** | .jt | Jupiter Tessellation (ISO 14306) |

## Properties

**[Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions-1/format/)** - Specifies the desired 3D file format. Available options include: *Fbx, Obj, Gltf, ThreeDS, U3d, Dae, Drc, Rvm, Amf, Ply*, and others.

**[PageNumber](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/ipagedconvertoptions/pagenumber)** - Specifies the starting page number for conversion (when source has multiple views/scenes).

**[PagesCount](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/ipagedconvertoptions/pagescount)** - Specifies the number of pages to convert.

## Conversion Examples

ThreeDConvertOptions supports conversion between 3D formats. The following examples demonstrate common conversions.

### FBX to OBJ

Convert an Autodesk FBX model to Wavefront OBJ format:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;

string sourceFile = "character-model.fbx";
string outputFile = "character-model.obj";

using (var converter = new Converter(sourceFile))
{
    var options = new ThreeDConvertOptions
    {
        Format = ThreeDFileType.Obj
    };
    converter.Convert(outputFile, options);
}
```

### OBJ to FBX

Convert a Wavefront OBJ model to Autodesk FBX format:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;

string sourceFile = "building-model.obj";
string outputFile = "building-model.fbx";

using (var converter = new Converter(sourceFile))
{
    var options = new ThreeDConvertOptions
    {
        Format = ThreeDFileType.Fbx
    };
    converter.Convert(outputFile, options);
}
```

### FBX to GLTF

Convert an FBX model to GLTF (GL Transmission Format) for web and mobile:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;

string sourceFile = "product-design.fbx";
string outputFile = "product-design.gltf";

using (var converter = new Converter(sourceFile))
{
    var options = new ThreeDConvertOptions
    {
        Format = ThreeDFileType.Gltf
    };
    converter.Convert(outputFile, options);
}
```

### OBJ to 3DS

Convert an OBJ model to 3D Studio format:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;

string sourceFile = "terrain-model.obj";
string outputFile = "terrain-model.3ds";

using (var converter = new Converter(sourceFile))
{
    var options = new ThreeDConvertOptions
    {
        Format = ThreeDFileType.ThreeDS
    };
    converter.Convert(outputFile, options);
}
```

### FBX to U3D

Convert an FBX model to Universal 3D format for PDF embedding:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;

string sourceFile = "mechanical-part.fbx";
string outputFile = "mechanical-part.u3d";

using (var converter = new Converter(sourceFile))
{
    var options = new ThreeDConvertOptions
    {
        Format = ThreeDFileType.U3d
    };
    converter.Convert(outputFile, options);
}
```

## Format Support Notes

3D to 3D conversions are supported for most format combinations:
- FBX → OBJ, GLTF, 3DS, U3D, DAE, DRC, AMF, PLY, RVM
- OBJ → FBX, GLTF, 3DS, U3D, DAE, DRC, AMF, PLY, RVM
- GLTF → FBX, OBJ, 3DS, U3D, DAE, DRC, AMF, PLY, RVM
- 3DS → FBX, OBJ, GLTF, U3D, DAE, DRC, AMF, PLY, RVM
- All source 3D formats → Common target formats (FBX, OBJ, GLTF, etc.)

**Note:** To convert FROM 3D formats to PDF, use [PdfConvertOptions]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-to-pdf-with-advanced-options.md" >}}).

## More Resources

- [API Reference: ThreeDConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/threedconvertoptions)
- [API Reference: ThreeDFileType](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/threedfiletype)
- [Convert 3D Formats]({{< ref "conversion/net/developer-guide/basic-usage/convert/3d.md" >}})
- [Supported File Formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}})
