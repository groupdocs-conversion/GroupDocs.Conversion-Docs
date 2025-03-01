---
id: convert-image-with-ocr
url: conversion/net/convert/image-with-ocr
title: Convert images with optical character recognition
linkTitle: Images OCR
weight: 55
description: "In this article, you will learn how to convert an image file to text or PDF using OCR with GroupDocs.Conversion for .NET."
keywords: Convert JPG to DOCX, Convert PNG to PDF, OCR image, Image ocr, 
productName: GroupDocs.Conversion for .NET
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert Image with OCR in C#    
        description: Convert JPG to DOCX natively with high performance using C# language and GroupDocs.Conversion for .NET APIs
        productCode: conversion
        productPlatform: net 
    showVideo: True
    howTo:
        name: How to convert JPG to DOCX in C# 
        description: Learn how to convert JPG to DOCX in C# step by step
        steps:
        - name: Load source JPG file 
          text: Create an instance of Converter class and pass source JPG file path as a constructor parameter. You may specify absolute or relative file paths as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of WordProcessingConvertOptions class.
        - name: Convert to DOCX and save result 
          text: Call Converter class Convert method and pass the filename for the converted DOCX file and the WordConvertOptions object from the previous step as parameters.
---

## About image file formats

An image file format is a standard method for organizing and storing images on devices like computers, tablets and smartphones. Digital images store image data in a 2-dimensional grid of pixels where each pixel is a representation of color in terms of a number of bits. Image file types are classified into vector image formats and raster image formats. 3D Images are another type of vector image file format that is used for managing 3D images.

### Raster formats

**Raster Graphics** are digital images that comprise of pixels data for the representation of colors. These are the most common image types for graphics used for the web as well as digital photos. Some of the raster images can be compressed to reduce image file size. Common raster image file extensions and their file formats include **BMP** (Bitmap image file), **PNG** (Portable Network Graphics) and **GIF** (Graphics Interchange File).

### Vector formats

**Vector images** are defined by 2D points, instead of pixels, which are connected to give a geometric shape to the image. The points have properties that define the direction of paths, color, shape, curve, thickness, and fill. Common vector image file extensions and their file formats include **SVG** (Scalable Vector Graphics), **EPS** (Encapsulated PostScript language) and **PDF** (Portable Document Format).

## Convert from an image using OCR

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your image files using OCR.  

To allow OCR conversions [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) provides an extension point to offload the actual OCR process to the OCR processing library, but at the same time gives you the simplicity of conversion setup. The extension point is the [IOcrConnector](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.integration.ocr/iocrconnector) interface. 

First, you must decide which OCR processing library will use. Different libraries have different setup processes.

In our example, we will use Aspose.OCR. Install the [Aspose.OCR](https://www.nuget.org/packages/Aspose.OCR) nuget package in your project. Then implement [IOcrConnector](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.integration.ocr/iocrconnector). The following code snippet provides a sample implementation:

```csharp
public class OcrConnector : IOcrConnector
{
    public RecognizedImage Recognize(Stream imageStream)
    {
        try
        {
            var api = new AsposeOcr();
            var ocrInput = new OcrInput(InputType.SingleImage);

            using (MemoryStream ms = new MemoryStream())
            {
                imageStream.Position = 0;
                imageStream.CopyTo(ms);
                ms.Position = 0;
                ocrInput.Add(ms);

                var detectedRectangles = api.DetectRectangles(ocrInput, AreasType.LINES, false).First();
                var result = api.Recognize(ocrInput, new RecognitionSettings
                    {
                        DetectAreasMode = DetectAreasMode.COMBINE,
                        RecognitionAreas = detectedRectangles.Rectangles
                    })
                    .First();
                return CreateRecognizedImageFromResult(result);
            }
        }
        catch (System.Exception ex)
        {
            Console.WriteLine("Aspose.OCR Recognition failed: {0}", ex);
        }

        return RecognizedImage.Empty;
    }

    private RecognizedImage CreateRecognizedImageFromResult(RecognitionResult result)
    {
        var lines = new List<TextLine>();


        for (var i = 0; i < result.RecognitionAreasText.Count; i++)
        {
            var rectangle = result.RecognitionAreasRectangles[i];
            var s = result.RecognitionAreasText[i].Trim('\r', '\n');
            var fragments = SplitToFragments(s, rectangle.X, rectangle.Y, rectangle.Width, rectangle.Height);
            lines.Add(new TextLine(fragments));
        }

        return new RecognizedImage(lines);
    }

    private static List<TextFragment> SplitToFragments(string lineText, int rectangleX, int rectangleY,
        int rectangleWidth, int rectangleHeight)
    {
        var fragments = new List<TextFragment>();
        if (!string.IsNullOrEmpty(lineText))
        {
            int index = 0, fragIndex = 0;
            bool isWhitespace = false;
            List<char> frag = new List<char>();
            int previousWidth = 0;
            float fixWidthChar = rectangleWidth / GetEquivalentLength(lineText);
            while (index < lineText.Length)
            {
                if (frag.Count == 0)
                {
                    isWhitespace = (lineText[index] == ' ');
                }
                else
                {
                    bool altIsWhitespace = (lineText[index] == ' ');
                    if (index == lineText.Length - 1) frag.Add(lineText[index]);
                    if (altIsWhitespace != isWhitespace || (index == lineText.Length - 1))
                    {
                        string fragment = new string(frag.ToArray());
                        int fragWidth = (int)Math.Round(GetEquivalentLength(fragment) * fixWidthChar);
                        int actualLength = (index == lineText.Length - 1) ? lineText.Length : index;
                        previousWidth =
                            (int)Math.Round(GetEquivalentLength(lineText.Substring(0, actualLength - frag.Count)) *
                                            fixWidthChar);
                        fragments.Add(new TextFragment(fragment, new System.Drawing.Rectangle(
                            rectangleX + previousWidth,
                            rectangleY, fragWidth, rectangleHeight)));
                        fragIndex += fragment.Length;
                        frag.Clear();
                        isWhitespace = altIsWhitespace;
                    }
                }

                frag.Add(lineText[index]);
                index++;
            }
        }

        return fragments;
    }

    private static readonly List<char> NarrowChars = new List<char>(new char[]
    {
        ',', '.', ':', ';', '!', '|', '(', ')', '{', '}',
        'l', 'i', 'I', '-', '+', 'f', 't', 'r'
    });

    private static readonly List<char> WideChars = new List<char>(new char[] { '\t', 'm', 'w', 'M', 'W' });

    private static float GetEquivalentLength(string lineText)
    {
        var length = 0F;
        foreach (var c in lineText)
        {
            if (c == ' ')
                length += 0.6F;
            else if (NarrowChars.Contains(c))
                length += 0.5F;
            else if (WideChars.Contains(c) || char.IsUpper(c))
                length += 1.5F;
            else
                length += 1F;
        }

        return length;
    }
}
```

Once the `IOcrConnector` interface is implemented, the JPG to DOCX conversion code snippet looks like this:

With v24.10 and later:

```csharp
// Load the source JPG file
RasterImageLoadOptions loadOptions = new RasterImageLoadOptions();
loadOptions.SetOcrConnector(new OcrConnector());

using (Converter converter = new Converter("sample.jpg", (LoadContext loadContext) => loadOptions))
{
    // Set the convert options for DOCX format
    WordProcessingConvertOptions options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```


Before v24.10:

```csharp
// Load the source JPG file
ImageLoadOptions loadOptions = new ImageLoadOptions();
loadOptions.SetOcrConnector(new OcrConnector());
using (Converter converter = new Converter("sample.jpg", () => loadOptions))
{
    // Set the convert options for DOCX format
    WordProcessingConvertOptions options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

Put it simply - you install an OCR processing library, implement the `IOcrConnector` interface, load an image file into the `Converter` class providing the `IOcrConnector` instance, select the desired output format and **GroupDocs.Conversion** does all the rest.  

{{< alert style="info" >}}
Refer to the [API reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}
