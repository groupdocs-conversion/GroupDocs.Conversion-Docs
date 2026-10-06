---
id: convert-to-gis-with-advanced-options
url: conversion/net/convert-to-gis-with-advanced-options
title: Convert to GIS formats with advanced options
weight: 22
description: "Learn about GisConvertOptions class for GIS file formats (GeoJSON, KML, GPX, TopoJSON, GML, OSM) in GroupDocs.Conversion for .NET."
keywords: Convert to GeoJSON, Convert to KML, Convert to GPX, Convert to GML, Convert to OSM, Convert KMZ, GIS conversion, Geographic data conversion
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

GroupDocs.Conversion provides the [GisConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/gisconvertoptions) class to specify GIS (Geographic Information System) file format conversion settings.

## Supported GIS Formats

The following GIS (Geographic Information System) formats can be both loaded and saved:

| Format | Extension | Description |
|--------|-----------|-------------|
| **GeoJSON** | .geojson | JSON-based format for geographical features |
| **KML** | .kml | Keyhole Markup Language (Google Earth) |
| **GPX** | .gpx | GPS Exchange Format |
| **TopoJSON** | .topojson | GeoJSON extension with topology encoding |
| **GML** | .gml | Geography Markup Language (XML-based) |
| **OSM** | .osm | OpenStreetMap XML format |

The following GIS formats can be loaded and converted to any of the formats above:

| Format | Extension | Description |
|--------|-----------|-------------|
| **GeoJSON Text Sequence** | .geojsons | Newline-delimited sequence of GeoJSON features |
| **KMZ** | .kmz | Zipped KML (Google Earth) |

## Properties

**[Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions-1/format/)** - Specifies the desired GIS file format. Available options are: *GeoJson, Kml, Gpx, TopoJson, Gml, Osm*.

## Conversion Examples

GisConvertOptions supports conversion between GIS formats. The following examples demonstrate common conversions.

### GeoJSON to KML

Convert a GeoJSON file to KML (Keyhole Markup Language) for Google Earth:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;

string sourceFile = "geographic-data.geojson";
string outputFile = "geographic-data.kml";

using (var converter = new Converter(sourceFile))
{
    var options = new GisConvertOptions
    {
        Format = GisFileType.Kml
    };
    converter.Convert(outputFile, options);
}
```

### GPX to GeoJSON

Convert a GPX (GPS Exchange Format) file to GeoJSON:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;

string sourceFile = "tracking-route.gpx";
string outputFile = "tracking-route.geojson";

using (var converter = new Converter(sourceFile))
{
    var options = new GisConvertOptions
    {
        Format = GisFileType.GeoJson
    };
    converter.Convert(outputFile, options);
}
```

### GeoJSON to TopoJSON

Convert a GeoJSON file to TopoJSON format for topology-preserving conversions:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;

string sourceFile = "map-boundaries.geojson";
string outputFile = "map-boundaries.topojson";

using (var converter = new Converter(sourceFile))
{
    var options = new GisConvertOptions
    {
        Format = GisFileType.TopoJson
    };
    converter.Convert(outputFile, options);
}
```

### KMZ to GeoJSON

Convert a KMZ (zipped KML) file exported from Google Earth to GeoJSON:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;

string sourceFile = "placemarks.kmz";
string outputFile = "placemarks.geojson";

using (var converter = new Converter(sourceFile))
{
    var options = new GisConvertOptions
    {
        Format = GisFileType.GeoJson
    };
    converter.Convert(outputFile, options);
}
```

### GeoJSON to GML

Convert a GeoJSON file to GML (Geography Markup Language):

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;

string sourceFile = "parcels.geojson";
string outputFile = "parcels.gml";

using (var converter = new Converter(sourceFile))
{
    var options = new GisConvertOptions
    {
        Format = GisFileType.Gml
    };
    converter.Convert(outputFile, options);
}
```

## Format Support Notes

Every supported GIS source format — GeoJSON, GeoJSON Text Sequence, GML, GPX, KML, KMZ, OSM and TopoJSON — converts to every GIS target format: GeoJSON, GML, GPX, KML, OSM and TopoJSON.

GML and OSM are available as conversion targets starting with version 26.9. GIS conversion is available on .NET Framework 4.6.2 as well as on .NET 6 and later starting with version 26.9.

**Note:** To convert FROM GIS formats to PDF, images, or other document formats, use [PdfConvertOptions]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-to-pdf-with-advanced-options.md" >}}), [ImageConvertOptions]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-to-image-with-advanced-options.md" >}}), or other appropriate ConvertOptions classes.

## More Resources

- [API Reference: GisConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/gisconvertoptions)
- [API Reference: GisFileType](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/gisfiletype)
- [Convert GIS Formats]({{< ref "conversion/net/developer-guide/basic-usage/convert/gis.md" >}})
- [Supported File Formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}})
