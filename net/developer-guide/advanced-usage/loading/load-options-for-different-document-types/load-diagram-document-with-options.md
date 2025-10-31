---
id: load-diagram-document-with-options
url: conversion/net/load-diagram-document-with-options
title: Load diagram document with options
weight: 21
description: "Learn how to load and convert diagram files (VSD, VSDX, Visio) with advanced options using GroupDocs.Conversion for .NET API."
keywords: Load diagram file, Load and convert VSD, Load and convert VSDX, Load and convert Visio, Diagram file conversion
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) provides [DiagramLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/diagramloadoptions) to control how source diagram files are processed. Diagram files include formats like VSD, VSDX, VDX, VSDM, VSSX, and other Microsoft Visio formats.

The following options are available:

| Option | Description |
|--------|-------------|
|**[Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/diagramloadoptions/format)** | The document type is auto-detected during loading, but you can explicitly specify the source format. Available options include: *Vsd, Vsdx, Vsx, Vtx, Vdx, Vssx, Vstx, Vsdm, Vssm, Vstm* |
|**[DefaultFont](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/diagramloadoptions/defaultfont)** | Default font for rendering the diagram. The following font will be used if a diagram font is missing. |

## Load VSD file

The following code snippet shows how to load a VSD (Visio Drawing) file with explicit format specification:

With v24.10 and later:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new DiagramLoadOptions
{
    Format = DiagramFileType.Vsd
};

using (Converter converter = new Converter("design-diagram.vsd", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("design-diagram.pdf", options);
}
```

Before v24.10:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadOptions> getLoadOptions = () => new DiagramLoadOptions
{
    Format = DiagramFileType.Vsd
};

using (Converter converter = new Converter("design-diagram.vsd", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("design-diagram.pdf", options);
}
```

## Load VSDX file

The following code snippet shows how to load a VSDX (Visio Drawing XML) file:

With v24.10 and later:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new DiagramLoadOptions
{
    Format = DiagramFileType.Vsdx
};

using (Converter converter = new Converter("flowchart.vsdx", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("flowchart.pdf", options);
}
```

Before v24.10:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadOptions> getLoadOptions = () => new DiagramLoadOptions
{
    Format = DiagramFileType.Vsdx
};

using (Converter converter = new Converter("flowchart.vsdx", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("flowchart.pdf", options);
}
```

## Load VSD with default font

The following code snippet shows how to load a VSD file with a default font for missing fonts:

With v24.10 and later:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new DiagramLoadOptions
{
    Format = DiagramFileType.Vsd,
    DefaultFont = "Arial"
};

using (Converter converter = new Converter("network-diagram.vsd", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("network-diagram.pdf", options);
}
```

Before v24.10:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadOptions> getLoadOptions = () => new DiagramLoadOptions
{
    Format = DiagramFileType.Vsd,
    DefaultFont = "Arial"
};

using (Converter converter = new Converter("network-diagram.vsd", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("network-diagram.pdf", options);
}
```

## Convert VSDX to Word document

The following code snippet shows how to load a VSDX file and convert it to a Word document:

With v24.10 and later:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new DiagramLoadOptions
{
    Format = DiagramFileType.Vsdx
};

using (Converter converter = new Converter("process-flow.vsdx", getLoadOptions))
{
    WordProcessingConvertOptions options = new WordProcessingConvertOptions();
    converter.Convert("process-flow.docx", options);
}
```

Before v24.10:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadOptions> getLoadOptions = () => new DiagramLoadOptions
{
    Format = DiagramFileType.Vsdx
};

using (Converter converter = new Converter("process-flow.vsdx", getLoadOptions))
{
    WordProcessingConvertOptions options = new WordProcessingConvertOptions();
    converter.Convert("process-flow.docx", options);
}
```

## Convert between diagram formats

The following code snippet shows how to convert from VSD to VSDX format:

With v24.10 and later:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new DiagramLoadOptions
{
    Format = DiagramFileType.Vsd
};

using (Converter converter = new Converter("legacy-diagram.vsd", getLoadOptions))
{
    DiagramConvertOptions options = new DiagramConvertOptions
    {
        Format = DiagramFileType.Vsdx
    };
    converter.Convert("legacy-diagram.vsdx", options);
}
```

Before v24.10:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadOptions> getLoadOptions = () => new DiagramLoadOptions
{
    Format = DiagramFileType.Vsd
};

using (Converter converter = new Converter("legacy-diagram.vsd", getLoadOptions))
{
    DiagramConvertOptions options = new DiagramConvertOptions
    {
        Format = DiagramFileType.Vsdx
    };
    converter.Convert("legacy-diagram.vsdx", options);
}
```

## Convert VSDX to PowerPoint

The following code snippet shows how to load a VSDX file and convert it to a PowerPoint presentation:

With v24.10 and later:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new DiagramLoadOptions
{
    Format = DiagramFileType.Vsdx
};

using (Converter converter = new Converter("org-chart.vsdx", getLoadOptions))
{
    PresentationConvertOptions options = new PresentationConvertOptions();
    converter.Convert("org-chart.pptx", options);
}
```

Before v24.10:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadOptions> getLoadOptions = () => new DiagramLoadOptions
{
    Format = DiagramFileType.Vsdx
};

using (Converter converter = new Converter("org-chart.vsdx", getLoadOptions))
{
    PresentationConvertOptions options = new PresentationConvertOptions();
    converter.Convert("org-chart.pptx", options);
}
```
