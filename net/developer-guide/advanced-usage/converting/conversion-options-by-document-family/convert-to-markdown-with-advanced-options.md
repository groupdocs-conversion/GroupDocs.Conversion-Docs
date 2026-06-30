---
id: convert-to-markdown-with-advanced-options
url: conversion/net/convert-to-markdown-with-advanced-options
title: Convert to Markdown with advanced options
weight: 23
description: "Follow this guide and learn how to convert documents to Markdown format with advanced image handling — embed images as base64, write them as external files, or redirect them to a custom destination via the image saving callback using GroupDocs.Conversion for .NET."
keywords: Convert to Markdown, Markdown images, base64 images, ImageSavingCallback, IMarkdownImageSavingCallback, MarkdownOptions
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---
When converting documents to Markdown (`WordProcessingFileType.Md`), images from the source document can be handled in two ways:

- **Inline as base64** — images are embedded directly in the `.md` as data URIs, producing a single self-contained file. This is the default.
- **Custom destination via callback** — you take control of each image: where the bytes go (disk, memory, cloud storage, …) and what URI is written into the Markdown.

Both are configured through [MarkdownOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/markdownoptions) on [WordProcessingConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions).

## Inline images as base64 (default)

By default, [MarkdownOptions.ExportImagesAsBase64](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/markdownoptions/exportimagesasbase64) is `true`, so images are encoded into the Markdown as data URIs — the result is a single self-contained `.md` file with no separate image outputs.

```csharp
using (Converter converter = new Converter("sample.pdf"))
{
    WordProcessingConvertOptions options = new WordProcessingConvertOptions
    {
        Format = WordProcessingFileType.Md
        // MarkdownOptions.ExportImagesAsBase64 is true by default
    };
    converter.Convert("converted.md", options);
}
```

The resulting Markdown looks like:

```markdown
![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUg...)
```

Use this when you need a portable, single-file output — for example, storing Markdown in a database, sending it over a message channel, or rendering it in a viewer that cannot resolve relative image paths.

## Customize image output with a callback

*Available in GroupDocs.Conversion for .NET 26.6 and later.*

For full control over where images are written and which URI appears in the Markdown, implement [IMarkdownImageSavingCallback](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/imarkdownimagesavingcallback) and assign it to [MarkdownOptions.ImageSavingCallback](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/markdownoptions/imagesavingcallback). The callback is invoked once per image, regardless of the source format (PDF, DOCX, PPTX, …).

When a callback is assigned, it takes precedence automatically — images are written through the callback even if `ExportImagesAsBase64` is left at its default.

The callback receives a [MarkdownImageSavingArgs](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/markdownimagesavingargs) instance with three mutable properties:

- **ImageFileName** — the URI written into the Markdown as the image reference. Set this to a file name, a placeholder id, or any string.
- **ImageStream** — the destination stream the converter writes the image bytes into. Replace it to redirect the bytes.
- **KeepImageStreamOpen** — when `false` (default) the converter flushes and closes the stream; when `true` the caller keeps ownership and can read the stream after `Convert()` returns.

### Scenario 1 — capture images in memory with placeholder IDs

Redirect every image into an in-memory buffer and write a unique placeholder id into the Markdown instead of a file path. Useful when you want to post-process images, upload them to external storage, or reference them from a different system.

```csharp
class CaptureImagesCallback : IMarkdownImageSavingCallback
{
    private int _index;
    private readonly Dictionary<string, MemoryStream> _images;

    public CaptureImagesCallback(Dictionary<string, MemoryStream> images) => _images = images;

    public void ImageSaving(MarkdownImageSavingArgs args)
    {
        var id = $"image{_index++}";
        var buffer = new MemoryStream();
        _images[id] = buffer;
        args.ImageStream = buffer;            // redirect image bytes into our buffer
        args.ImageFileName = id;              // placeholder URI written into the .md
        args.KeepImageStreamOpen = true;      // keep buffer readable after Convert() returns
    }
}

var captured = new Dictionary<string, MemoryStream>();
try
{
    var options = new WordProcessingConvertOptions { Format = WordProcessingFileType.Md };
    options.MarkdownOptions.ImageSavingCallback = new CaptureImagesCallback(captured);

    using var converter = new Converter("source.pdf");
    converter.Convert("output.md", options);
    // captured["image0"], captured["image1"], ... now hold the image bytes
}
finally
{
    foreach (var s in captured.Values) s.Dispose();   // caller owns the streams
}
```

The resulting Markdown references the placeholder ids:

```markdown
![](image0)
![](image1)
```

### Scenario 2 — persist images to disk alongside the `.md`

Write each image to a specific folder with a chosen naming scheme and let the converter close each file when it's done.

```csharp
class FileImagesCallback : IMarkdownImageSavingCallback
{
    private readonly string _outputFolder;
    private int _index;

    public FileImagesCallback(string outputFolder) => _outputFolder = outputFolder;

    public void ImageSaving(MarkdownImageSavingArgs args)
    {
        var fileName = $"image{_index++}.png";
        args.ImageStream = new FileStream(Path.Combine(_outputFolder, fileName), FileMode.Create);
        args.ImageFileName = fileName;        // written into the .md as ![](image0.png)
        // KeepImageStreamOpen left at default (false) → the converter flushes and closes the file.
    }
}

var options = new WordProcessingConvertOptions { Format = WordProcessingFileType.Md };
options.MarkdownOptions.ImageSavingCallback = new FileImagesCallback("./out");

using var converter = new Converter("source.pdf");
converter.Convert("./out/output.md", options);
// ./out/image0.png, ./out/image1.png, ... are written and closed by the converter.
```

## More Resources

- [API Reference: MarkdownOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/markdownoptions)
- [API Reference: IMarkdownImageSavingCallback](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/imarkdownimagesavingcallback)
- [API Reference: MarkdownImageSavingArgs](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/markdownimagesavingargs)
- [Convert to WordProcessing with advanced options]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-to-wordprocessing-with-advanced-options.md" >}})
