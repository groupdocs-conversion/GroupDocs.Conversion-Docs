---
id: convert-image-using-ocr
url: conversion/net/convert-image-using-ocr
title: Convert Image using OCR
weight: 11
description: "To convert image using ocr, follow this guide to learn how to convert an image document with ocr processing using GroupDocs.Conversion for .NET."
keywords: OCR Image, Image OCR, Extract text from image
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
### Convert Image using OCR

GroupDocs.Conversion for .NET provide an extension point which allows convert images using OCR processing. To use this you have to implement **[IOcrConnector](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.integration.ocr/iocrconnector)** interface and provide instance of it in **[ImageLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/imageloadoptions)**.

The following code snippet shows how to convert image using OCR processing and extract text from image and convert it to PDF:

First create a class that implements [IOcrConnector](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.integration.ocr/iocrconnector)**
```csharp
internal class OcrConnector : IOcrConnector
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
                var rectangles = api.GetRectangles(ms, AreasType.LINES,false);
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
    private RecognizedImage CreateRecognizedImageFromResul(RecognitionResult result)
    {
        var lines = new List<TextLine>();
        for (var i = 0; i < result.RecognitionAreasText.Count; i++)
        {
            var fragments = SplitToFragments(result.RecognitionAreasText[i]Trim('\r', '\n'), result.RecognitionAreasRectangles[i]);
            lines.Add(new TextLine(fragments));
        }
        return new RecognizedImage(lines);
    }
    private static List<TextFragment> SplitToFragments(string lineText,Rectangle boundingRect)
    {
        var fragments = new List<TextFragment>();
        if (!string.IsNullOrEmpty(lineText))
        {
            int index = 0, fragIndex = 0;
            bool isWhitespace = false;
            List<char> frag = new List<char>();
            int previousWidth = 0;
            float fixWidthChar = boundingRect.Width / GetEquivalentLengt(lineText);
            while (index < lineText.Length)
            {
                if (frag.Count == 0)
                {
                    isWhitespace = (lineText[index] == ' ');
                }
                else
                {
                    bool altIsWhitespace = (lineText[index] == ' ');
                    if (index == lineText.Length - 1) frag.Add(lineTex[index]);
                    if (altIsWhitespace != isWhitespace || (index ==lineText.Length - 1))
                    {
                        string fragment = new string(frag.ToArray());
                        int fragWidth = (int)Math.Round(GetEquivalentLengt(fragment) * fixWidthChar);
                        int actualLength = (index == lineText.Length - 1) ?lineText.Length : index;
                        previousWidth = (int)Math.Round(GetEquivalentLengt(lineText.Substring(0, actualLength - frag.Count))* fixWidthChar);
                        fragments.Add(new TextFragment(fragment, newRectangle(boundingRect.X + previousWidth,
                            boundingRect.Y, fragWidth, boundingRect.Height));
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
    private static readonly List<char> NarrowChars = new List<char>(new cha[] { ',', '.', ':', ';', '!', '|', '(', ')', '{', '}',
        'l', 'i', 'I', '-', '+', 'f', 't', 'r'});
    private static readonly List<char> WideChars = new List<char>(new cha[] { '\t', 'm', 'w', 'M', 'W' });
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

Then provide **OcrConnector** instance in **[ImageLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/imageloadoptions)**:

```csharp
var imageLoadOptions = new ImageLoadOptions();
imageLoadOptions.SetOcrConnector(new OcrConnector());

using (Converter converter = new Converter("sample.jpeg", () => imageLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

{{< alert style="info" >}}The example uses Aspose.OCR but any OCR processing library could be used{{< /alert >}}

{{< alert style="warning" >}}This functionality is introduced in v22.4{{< /alert >}}
