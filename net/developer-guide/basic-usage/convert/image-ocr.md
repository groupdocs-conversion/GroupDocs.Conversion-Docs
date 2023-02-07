---
id: convert-image-with-ocr
url: conversion/net/convert/image-with-ocr
title: Convert images with optical character recognition
linkTitle: Images OCR
weight: 55
description: "Following this article you will learn how to convert an image file to word or pdf using OCR with couple C# code lines and GroupDocs.Conversion for .NET."
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
          text: Create an instance of Converter class and pass source JPG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of WordProcessingConvertOptions class.
        - name: Convert to DOCX and save result 
          text: Call Converter class Convert method and pass the filename for the converted DOCX file and the WordConvertOptions object from the previous step as parameters.
---

## About image file formats

An image file format is a standard method for organizing and storing images on devices like computers, tablets and smartphones. Digital images store image data in a 2-dimensional grid of pixels where each pixel is a representation of colour in terms of number of bits. Image file types are classified into vector image formats and raster image formats. 3D Images are another type of vector image file format that is used for managing 3D images.

### Raster formats

**Raster Graphics** are digital images that comprise of pixels data for representation of colours. These are the most common image types for graphics used for web as well as digital photos. Some of the raster images can be compressed to reduce image file size. Common raster image file extensions and their file formats include **BMP** (Bitmap image file), **PNG** (Portable Network Graphics) and **GIF** (Graphics Interchange File).

### Vector formats

**Vector images** are defined by 2D points, instead of pixels, which are connected to give a geometric shape to the image. The points have properties that define the direction of paths, color, shape, curve, thickness, and fill. Common vector image file extensions and their file formats include **SVG** (Scalable Vector Graphics), **EPS** (Encapsulated PostScript language) and **PDF** (Portable Document Format).

## Convert from image using OCR

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your image files using ocr.  

In order to allow OCR conversions [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) provides an extension point to offload actual OCR process to ocr processing library, but in the same time to give you the simplicity of conversion setup. The extension point is [IOcrConnector](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.integration.ocr/iocrconnector) interface. 

You first must decide which ocr processing library will use. Different libraries have different setup process.

In our example we will use Aspose.OCR. Install [Aspose.OCR](https://www.nuget.org/packages/Aspose.OCR) nuget package in your project. Then implement [IOcrConnector](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.integration.ocr/iocrconnector). The following snippet provides sample implementation:

```csharp
public class OcrConnector : IOcrConnector
{
    public RecognizedImage Recognize(Stream imageStream)
    {
        try
        {
            var api = new AsposeOcr();

            using (MemoryStream ms = new MemoryStream())
            {
                imageStream.Position = 0;
                imageStream.CopyTo(ms);
                var rectangles = api.GetRectangles(ms, AreasType.LINES, false);
                var result = api.RecognizeImage(ms, new RecognitionSettings
                {
                    DetectAreas = false,
                    RecognitionAreas = rectangles
                });
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
            var fragments = SplitToFragments(result.RecognitionAreasText[i].Trim('\r', '\n'),
                result.RecognitionAreasRectangles[i]);
            lines.Add(new TextLine(fragments));
        }

        return new RecognizedImage(lines);
    }

    private static List<TextFragment> SplitToFragments(string lineText, Rectangle boundingRect)
    {
        var fragments = new List<TextFragment>();
        if (!string.IsNullOrEmpty(lineText))
        {
            int index = 0, fragIndex = 0;
            bool isWhitespace = false;
            List<char> frag = new List<char>();
            int previousWidth = 0;
            float fixWidthChar = boundingRect.Width / GetEquivalentLength(lineText);
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
                        fragments.Add(new TextFragment(fragment, new Rectangle(boundingRect.X + previousWidth,
                            boundingRect.Y, fragWidth, boundingRect.Height)));
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

Once `IOcrConnector` is implemented JPG to DOCX conversion code snippet will look like this:

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

Put it simply - you install ocr processing library, implement `IOcrConnector`, load an image file into `Converter` providing the `IOcrConnector` instance, select desired output format and all the rest will be done by **GroupDocs.Conversion**.  

{{< alert style="info" >}}
Refer to [API reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}
