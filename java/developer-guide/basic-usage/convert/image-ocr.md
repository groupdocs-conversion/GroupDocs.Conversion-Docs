---
id: convert-image-with-ocr
url: conversion/java/convert/image-with-ocr
title: Convert images with optical character recognition
linkTitle: Images OCR
weight: 55
description: "In this article, you will learn how to convert an image file to text or PDF using OCR with GroupDocs.Conversion for Java."
keywords: Convert JPG to DOCX, Convert PNG to PDF, OCR image, Image ocr, 
productName: GroupDocs.Conversion for Java
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert Image with OCR in Java    
        description: Convert JPG to DOCX natively with high performance using C# language and GroupDocs.Conversion for .NET APIs
        productCode: conversion
        productPlatform: Java 
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

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/java) you can easily convert your image files using OCR.  

To allow OCR conversions [GroupDocs.Conversion](https://products.groupdocs.com/conversion/java) provides an extension point to offload the actual OCR process to the OCR processing library, but at the same time gives you the simplicity of conversion setup. The extension point is the [IOcrConnector](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.integration.ocr/iocrconnector/) interface. 

First, you must decide which OCR processing library will use. Different libraries have different setup processes.

In our example, we will use Aspose.OCR. Install the [Aspose.OCR](https://releases.aspose.com/java/repo/com/aspose/aspose-ocr/) nuget package in your project. Then implement [IOcrConnector](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.integration.ocr/iocrconnector/). The following code snippet provides a sample implementation:


{{< tabs "example-1">}}
{{< tab "ConvertImageUsingOcr.java" >}}  
```java
import com.aspose.ocr.*;
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.examples.Constants;
import com.groupdocs.conversion.integration.ocr.IOcrConnector;
import com.groupdocs.conversion.integration.ocr.RecognizedImage;
import com.groupdocs.conversion.integration.ocr.TextFragment;
import com.groupdocs.conversion.integration.ocr.TextLine;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.ImageLoadOptions;
import javax.imageio.ImageIO;
import java.awt.*;
import java.awt.image.BufferedImage;
import java.io.InputStream;
import java.lang.Character;
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;

/**
 * This example demonstrates how to convert image using ocr
 */
public class ConvertImageUsingOcr {
    public static void run() {
        String outputFile = Constants.getConvertedPath("converted.pdf");

        ImageLoadOptions imageLoadOptions = new ImageLoadOptions();
        imageLoadOptions.setOcrConnector(new OcrConnector());

        //Once the `IOcrConnector` interface is implemented, the JPG to PDF conversion code snippet looks like this:
        try (Converter converter = new Converter(Constants.SAMPLE_JPEG, () -> imageLoadOptions)) {
            PdfConvertOptions options = new PdfConvertOptions();
            converter.convert(outputFile, options);
        } catch (Exception e) {
            System.out.println("Conversion failed: " + e.getMessage());
        }

        System.out.printf("\nDocument converted successfully. \nCheck output in %s%n", outputFile);
    }

}
class OcrConnector implements IOcrConnector {
    @Override
    public RecognizedImage recognize(InputStream imageStream) {
        try {
            AsposeOCR api = new AsposeOCR();
            OcrInput ocrInput = new OcrInput(InputType.SingleImage);

            BufferedImage image = ImageIO.read(imageStream);
            ocrInput.add(image);

            RectangleOutput detectedRectangles = api.DetectRectangles(ocrInput, AreasType.LINES, false).get(0);

            RecognitionSettings recognitionSettings = new RecognitionSettings();
            recognitionSettings.setDetectAreasMode(DetectAreasMode.COMBINE);
            recognitionSettings.setRecognitionAreas(detectedRectangles.Rectangles);

            RecognitionResult result = api.Recognize(ocrInput, recognitionSettings).get(0);

            return createRecognizedImageFromResult(result);
        } catch (Exception ex) {
            System.out.println("OCR Recognition failed: " + ex.getMessage());
        }
        return RecognizedImage.EMPTY;
    }

    private RecognizedImage createRecognizedImageFromResult(RecognitionResult result) {
        List<TextLine> lines = new ArrayList<>();

        for (int i = 0; i < result.recognitionAreasText.size(); i++) {
            String text = result.recognitionAreasText.get(i).trim();
            Rectangle rectangle = result.recognitionAreasRectangles.get(i);
            List<TextFragment> fragments = splitToFragments(text, (int)rectangle.getX(), (int)rectangle.getY(), (int)rectangle.getWidth(), (int)rectangle.getHeight());
            lines.add(new TextLine(fragments));
        }
        return new RecognizedImage(lines);
    }

    private List<TextFragment> splitToFragments(String lineText, int rectangleX, int rectangleY, int rectangleWidth, int rectangleHeight) {
        List<TextFragment> fragments = new ArrayList<>();
        if (lineText != null && !lineText.isEmpty()) {
            List<Character> frag = new ArrayList<>();
            boolean isWhitespace = false;
            float fixWidthChar = rectangleWidth / getEquivalentLength(lineText);

            for (int i = 0; i < lineText.length(); i++) {
                if (frag.isEmpty()) {
                    isWhitespace = (lineText.charAt(i) == ' ');
                } else {
                    boolean currentIsWhitespace = (lineText.charAt(i) == ' ');
                    if (i == lineText.length() - 1) frag.add(lineText.charAt(i));
                    if (currentIsWhitespace != isWhitespace || i == lineText.length() - 1) {
                        String fragment = frag.stream().map(String::valueOf).reduce("", String::concat);
                        int fragWidth = Math.round(getEquivalentLength(fragment) * fixWidthChar);
                        fragments.add(new TextFragment(fragment, new Rectangle(rectangleX, rectangleY, fragWidth, rectangleHeight)));
                        frag.clear();
                        isWhitespace = currentIsWhitespace;
                    }
                }
                frag.add(lineText.charAt(i));
            }
        }
        return fragments;
    }

    private float getEquivalentLength(String lineText) {
        float length = 0;
        for (char c : lineText.toCharArray()) {
            if (c == ' ') {
                length += 0.6f;
            } else if (NARROW_CHARS.contains(c)) {
                length += 0.5f;
            } else if (WIDE_CHARS.contains(c) || Character.isUpperCase(c)) {
                length += 1.5f;
            } else {
                length += 1.0f;
            }
        }
        return length;
    }

    private final List<Character> NARROW_CHARS = Arrays.asList(',', '.', ':', ';', '!', '|', '(', ')', '{', '}', 'l', 'i', 'I', '-', '+', 'f', 't', 'r');
    private final List<Character> WIDE_CHARS = Arrays.asList('\t', 'm', 'w', 'M', 'W');
}
```
{{< /tab >}}
{{< tab "sample.jpeg" >}}  
{{< tab-text >}}
`sample.jpeg` is the sample file used in this example. Click [here](/conversion/java/images/sample.jpeg) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted.pdf" >}}  
{{< tab-text >}}
`converted.pdf` is the expected output PDF file. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/image-ocr/converted.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

Put it simply - you install an OCR processing library, implement the `IOcrConnector` interface, load an image file into the `Converter` class providing the `IOcrConnector` instance, select the desired output format and **GroupDocs.Conversion** does all the rest.  

{{< alert style="info" >}}
Refer to the [API reference](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/) for more conversion options and customizations.
{{< /alert >}}
