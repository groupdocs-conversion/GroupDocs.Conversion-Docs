---
id: load-gis-document-with-options
url: conversion/net/load-gis-document-with-options
title: Load GIS document with options
weight: 17
description: "Learn how to load and convert GIS documents (GeoJSON, KML, GPX) with advanced options using GroupDocs.Conversion for .NET API."
keywords: Load GIS document, Load and convert GeoJSON, Load and convert KML, Load and convert GPX, GIS file conversion
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) provides [GisLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/gisloadoptions) to control how source GIS (Geographic Information System) documents are processed. GIS documents include formats like GeoJSON, KML, GPX, and other geospatial data files.

The following options are available:

| Option | Description |
|--------|-------------|
|**[Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/gisloadoptions/format)** | The document type is auto-detected during loading, but you can explicitly specify the source format. Available options include: *GeoJson, Gpx, Kml, Osm, TopoJson, Gml* |
|**[Width](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/gisloadoptions/width)** | Sets the desired page width (in pixels) for rendering the GIS document. Default value is 1000. |
|**[Height](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/gisloadoptions/height)** | Sets the desired page height (in pixels) for rendering the GIS document. Default value is 1000. |

## Load GeoJSON document

The following code snippet shows how to load a GeoJSON document with explicit format specification:

With v24.10 and later:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new GisLoadOptions
{
    Format = GisFileType.GeoJson
};

using (Converter converter = new Converter("map-data.geojson", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("map-data.pdf", options);
}
```

Before v24.10:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadOptions> getLoadOptions = () => new GisLoadOptions
{
    Format = GisFileType.GeoJson
};

using (Converter converter = new Converter("map-data.geojson", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("map-data.pdf", options);
}
```

## Load GPX document

The following code snippet shows how to load a GPX (GPS Exchange Format) document:

With v24.10 and later:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new GisLoadOptions
{
    Format = GisFileType.Gpx
};

using (Converter converter = new Converter("route-tracking.gpx", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("route-tracking.pdf", options);
}
```

Before v24.10:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadOptions> getLoadOptions = () => new GisLoadOptions
{
    Format = GisFileType.Gpx
};

using (Converter converter = new Converter("route-tracking.gpx", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("route-tracking.pdf", options);
}
```

## Load GIS document with custom dimensions

The following code snippet shows how to load a GeoJSON document and set custom rendering dimensions:

With v24.10 and later:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new GisLoadOptions
{
    Format = GisFileType.GeoJson,
    Width = 1500,
    Height = 1200
};

using (Converter converter = new Converter("city-boundaries.geojson", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("city-boundaries.pdf", options);
}
```

Before v24.10:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadOptions> getLoadOptions = () => new GisLoadOptions
{
    Format = GisFileType.GeoJson,
    Width = 1500,
    Height = 1200
};

using (Converter converter = new Converter("city-boundaries.geojson", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("city-boundaries.pdf", options);
}
```

## Convert GIS document to image

The following code snippet shows how to load a GeoJSON document and convert it to an image with custom dimensions:

With v24.10 and later:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new GisLoadOptions
{
    Format = GisFileType.GeoJson,
    Width = 800,
    Height = 600
};

using (Converter converter = new Converter("region-map.geojson", getLoadOptions))
{
    ImageConvertOptions options = new ImageConvertOptions
    {
        Format = ImageFileType.Png
    };
    converter.Convert("region-map.png", options);
}
```

Before v24.10:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadOptions> getLoadOptions = () => new GisLoadOptions
{
    Format = GisFileType.GeoJson,
    Width = 800,
    Height = 600
};

using (Converter converter = new Converter("region-map.geojson", getLoadOptions))
{
    ImageConvertOptions options = new ImageConvertOptions
    {
        Format = ImageFileType.Png
    };
    converter.Convert("region-map.png", options);
}
```

## Convert between GIS formats

The following code snippet shows how to convert from GPX to KML format:

With v24.10 and later:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new GisLoadOptions
{
    Format = GisFileType.Gpx
};

using (Converter converter = new Converter("hiking-trail.gpx", getLoadOptions))
{
    GisConvertOptions options = new GisConvertOptions
    {
        Format = GisFileType.Kml
    };
    converter.Convert("hiking-trail.kml", options);
}
```

Before v24.10:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadOptions> getLoadOptions = () => new GisLoadOptions
{
    Format = GisFileType.Gpx
};

using (Converter converter = new Converter("hiking-trail.gpx", getLoadOptions))
{
    GisConvertOptions options = new GisConvertOptions
    {
        Format = GisFileType.Kml
    };
    converter.Convert("hiking-trail.kml", options);
}
```
