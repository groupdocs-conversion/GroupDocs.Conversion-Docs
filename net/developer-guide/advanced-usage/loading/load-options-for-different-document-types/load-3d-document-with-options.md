---
id: load-3d-document-with-options
url: conversion/net/load-3d-document-with-options
title: Load 3D document with options
weight: 19
description: "Learn how to load and convert 3D model documents (FBX, OBJ, GLTF, 3DS) with advanced options using GroupDocs.Conversion for .NET API."
keywords: Load 3D document, Load and convert FBX, Load and convert OBJ, Load and convert GLTF, 3D model conversion
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) provides [ThreeDLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/threedloadoptions) to control how source 3D model documents are processed. 3D documents include formats like FBX, OBJ, GLTF, 3DS, U3D, and other 3D modeling file formats.

The following options are available:

| Option | Description |
|--------|-------------|
|**[Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/threedloadoptions/format)** | The document type is auto-detected during loading, but you can explicitly specify the source format. Available options include: *Fbx, ThreeDS, ThreeMF, Amf, Ase, Dae, Drc, Gltf, Obj, Ply, Rvm, U3d, Usd, Usdz, Vrml, X* |

## Load FBX document

The following code snippet shows how to load an FBX (Filmbox) document with explicit format specification:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new ThreeDLoadOptions
{
    Format = ThreeDFileType.Fbx
};

using (Converter converter = new Converter("character-model.fbx", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("character-model.pdf", options);
}
```

## Load OBJ document

The following code snippet shows how to load an OBJ (Wavefront) document:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new ThreeDLoadOptions
{
    Format = ThreeDFileType.Obj
};

using (Converter converter = new Converter("building-model.obj", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("building-model.pdf", options);
}
```

## Convert FBX to OBJ

The following code snippet shows how to load an FBX document and convert it to OBJ format:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new ThreeDLoadOptions
{
    Format = ThreeDFileType.Fbx
};

using (Converter converter = new Converter("animated-scene.fbx", getLoadOptions))
{
    ThreeDConvertOptions options = new ThreeDConvertOptions
    {
        Format = ThreeDFileType.Obj
    };
    converter.Convert("animated-scene.obj", options);
}
```

## Convert OBJ to GLTF

The following code snippet shows how to convert from OBJ to GLTF format:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new ThreeDLoadOptions
{
    Format = ThreeDFileType.Obj
};

using (Converter converter = new Converter("product-design.obj", getLoadOptions))
{
    ThreeDConvertOptions options = new ThreeDConvertOptions
    {
        Format = ThreeDFileType.Gltf
    };
    converter.Convert("product-design.gltf", options);
}
```

## Convert FBX to U3D

The following code snippet shows how to convert from FBX to U3D (Universal 3D) format:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new ThreeDLoadOptions
{
    Format = ThreeDFileType.Fbx
};

using (Converter converter = new Converter("game-asset.fbx", getLoadOptions))
{
    ThreeDConvertOptions options = new ThreeDConvertOptions
    {
        Format = ThreeDFileType.U3d
    };
    converter.Convert("game-asset.u3d", options);
}
```
