---
id: load-image-document-with-options
url: conversion/net/load-image-document-with-options
title: Load Image Documents with Options
weight: 20
description: "Learn how to use ImageLoadOptions to configure image document loading in GroupDocs.Conversion for .NET. Control format specification, font handling, and more."
keywords: ImageLoadOptions, load image, PNG, JPG, GIF, BMP, TIFF, image conversion, GroupDocs.Conversion
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

## Introduction

The **ImageLoadOptions** class enables you to configure how image documents are loaded in GroupDocs.Conversion. This is particularly useful when you need to explicitly specify the format, configure font handling for vector images, or control font folder behavior.

ImageLoadOptions works with all common image formats including PNG, JPG, GIF, BMP, TIFF, WEBP, PSD, and more.

## Properties

| Property | Type | Description |
|----------|------|-------------|
| `Format` | `ImageFileType` | Explicitly specify the input image format (get; set;) |
| `DefaultFont` | `string` | Default font for PSD, EMF, WMF images containing text (get; set;) |
| `ResetFontFolders` | `bool` | Reset font folders before loading document (get; set;) |

## Basic Usage

For most scenarios, GroupDocs.Conversion automatically detects the image format. However, you can explicitly specify it using ImageLoadOptions:

```csharp
using (var converter = new Converter(
    "product-photo.png",
    (LoadContext loadContext) => new ImageLoadOptions
    {
        Format = ImageFileType.Png
    }))
{
    converter.Convert("product-photo.pdf", new PdfConvertOptions());
}
```

## Property Examples

### Specifying Format

Explicitly specify the input image format when automatic detection might be ambiguous or when you want to ensure a specific format is used:

```csharp
using (var converter = new Converter(
    "company-logo.png",
    (LoadContext loadContext) => new ImageLoadOptions
    {
        Format = ImageFileType.Png
    }))
{
    converter.Convert("company-logo.pdf", new PdfConvertOptions());
}
```

**Supported formats:** Jpg, Png, Gif, Bmp, Tiff, Webp, Jpeg, Ico, Psd, Heic, and more.

### DefaultFont for Vector Images

When converting vector images (PSD, EMF, WMF) that contain text, you can specify a fallback font to use if the original font is missing:

```csharp
using (var converter = new Converter(
    "design-mockup.psd",
    (LoadContext loadContext) => new ImageLoadOptions
    {
        DefaultFont = "Arial"
    }))
{
    converter.Convert("design-mockup.pdf", new PdfConvertOptions());
}
```

**When to use:**
- Converting Photoshop files (PSD) with text layers
- Converting Enhanced Metafiles (EMF) containing text
- Converting Windows Metafiles (WMF) with embedded text
- Ensuring consistent rendering when fonts are unavailable

### ResetFontFolders

Control font folder configuration when loading images:

```csharp
using (var converter = new Converter(
    "banner-ad.png",
    (LoadContext loadContext) => new ImageLoadOptions
    {
        ResetFontFolders = true
    }))
{
    converter.Convert("banner-ad.pdf", new PdfConvertOptions());
}
```

**Use case:** When you need to ensure a clean font environment for consistent rendering across different systems.

## Using All Properties Together

Combine all ImageLoadOptions properties for complete control:

```csharp
using (var converter = new Converter(
    "banner-ad.png",
    (LoadContext loadContext) => new ImageLoadOptions
    {
        Format = ImageFileType.Png,
        DefaultFont = "Calibri",
        ResetFontFolders = true
    }))
{
    converter.Convert("banner-ad.docx", new WordProcessingConvertOptions());
}
```

## Common Scenarios

### Converting Different Image Formats

GroupDocs.Conversion supports converting images to various output formats:

#### Image to PDF

```csharp
using (var converter = new Converter(
    "profile-picture.png",
    (LoadContext loadContext) => new ImageLoadOptions { Format = ImageFileType.Png }))
{
    converter.Convert("profile-picture.pdf", new PdfConvertOptions());
}
```

#### Image to Word Document

```csharp
using (var converter = new Converter(
    "screenshot.png",
    (LoadContext loadContext) => new ImageLoadOptions { Format = ImageFileType.Png }))
{
    converter.Convert("screenshot.docx", new WordProcessingConvertOptions());
}
```

#### Image to Excel Spreadsheet

```csharp
using (var converter = new Converter(
    "thumbnail.png",
    (LoadContext loadContext) => new ImageLoadOptions { Format = ImageFileType.Png }))
{
    converter.Convert("thumbnail.xlsx", new SpreadsheetConvertOptions());
}
```

## When to Use ImageLoadOptions

Use ImageLoadOptions when you need to:

1. **Explicitly specify format** - When automatic detection might be insufficient or you want to enforce a specific format
2. **Handle missing fonts** - When converting vector images (PSD, EMF, WMF) that might have font availability issues
3. **Control font behavior** - When you need to reset font folders for consistent rendering
4. **Process ambiguous files** - When files have incorrect extensions or no extensions

## Without ImageLoadOptions

For simple conversions, you can rely on automatic format detection:

```csharp
using (var converter = new Converter("product-photo.png"))
{
    converter.Convert("product-photo.pdf", new PdfConvertOptions());
}
```

GroupDocs.Conversion automatically detects the format in most cases, so ImageLoadOptions is optional unless you need the specific configuration it provides.

## Supported Image Formats

ImageLoadOptions works with:
- **Raster formats**: PNG, JPG/JPEG, GIF, BMP, TIFF, WEBP, HEIC
- **Vector formats**: EMF, WMF, SVG
- **Professional formats**: PSD (Photoshop), ICO (Icons)

## Summary

ImageLoadOptions provides fine-grained control over image document loading:
- **Format**: Explicitly specify the input image format
- **DefaultFont**: Set fallback font for vector images with text
- **ResetFontFolders**: Control font folder configuration

All examples on this page have been verified through automated testing to ensure accuracy.

## See Also

- [Context Objects - Complete Guide]({{< ref "conversion/net/developer-guide/basic-usage/context-objects-complete-guide" >}})
- [ImageFileType API Reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/imagefiletype/)
- [ImageLoadOptions API Reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/imageloadoptions/)
