---
id: get-possible-conversions
url: conversion/java/get-possible-conversions
title: Getting Possible Conversions
weight: 1
description: "This article explains how to obtain supported conversions when converting documents with GroupDocs.Conversion within your Java applications"
keywords: obtain supported conversions
productName: GroupDocs.Conversion for Java
hideChildren: False
toc: True
---

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/java) supports a wide range of target formats for document conversion. While you can refer to the [supported file formats]({{< ref "conversion/java/supported-document-formats.md" >}}) documentation, the API also provides ways to programmatically retrieve possible conversions. This feature is useful for dynamically presenting conversion options to end-users or for system integrations.

## Get Possible Conversions for a Specific Document

To determine the possible conversion formats for a specific source document, follow these steps:

- **Initialize the Converter**: Create an instance of the `Converter` class by passing the source document path to its constructor.
- **Retrieve Conversions**: Call the `getPossibleConversions` method of the Converter object.
- **Process Results**: The method returns a `PossibleConversions` collection containing all the target formats supported for the given source document.

**Example Code**:

{{< tabs "code-example">}}
{{< tab "SpecificDocumentConversions.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.contracts.PossibleConversions;
import com.groupdocs.conversion.contracts.TargetConversion;
import java.util.List;
import java.util.stream.Collectors;
import java.util.stream.StreamSupport;

public class SpecificDocumentConversions {
    public static void convert() {
        String sourceFile = "cost-analysis.xlsx";
        // Initialize the converter with the source document
        try(Converter converter = new Converter(sourceFile)){
            // Get possible conversions for the document
            PossibleConversions conversions = converter.getPossibleConversions();

            // Filter primary conversions
            List<String> primaryConversions = StreamSupport.stream(conversions.getAll().spliterator(), false)
                    .filter(TargetConversion::isPrimary)
                    .map(conversion -> conversion.getFormat().getExtension())
                    .collect(Collectors.toList());

            // Filter secondary conversions
            List<String> secondaryConversions = StreamSupport.stream(conversions.getAll().spliterator(), false)
                    .filter(conversion -> !conversion.isPrimary())
                    .map(conversion -> conversion.getFormat().getExtension())
                    .collect(Collectors.toList());

            // Print out the source format and its conversions
            System.out.println(" **Source format**: " + conversions.getSource().getDescription());
            System.out.println("  - **Primary conversions**: " + primaryConversions);
            System.out.println("  - **Secondary conversions**: " + secondaryConversions);

        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "Console Output" >}}  
{{< tab-text >}}
 **Source format**: Microsoft Excel Open XML Spreadsheet (xlsx)
  - **Primary conversions**: [epub, mobi, azw3, eps, xps, tex, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, json, xml]
  - **Secondary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, emz, wmz, svgz, tga, psb, ppt, pps, pptx, ppsx, odp, otp, potx, potm, pptm, ppsm, fodp, svg, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md, ml]
{{< /tab-text >}}
{{< /tab >}}
{{< tab "cost-analysis.xlsx" >}}  
{{< tab-text >}}
`cost-analysis.xlsx` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/get-possible-conversions/cost-analysis.xlsx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

## Get All Available Conversions

If you need to retrieve all supported conversions across different document types, you can do this by calling the `getAllPossibleConversions` method of the `Converter` class.

- **Initialize the Converter**: Create an instance of the `Converter` class without specifying a source document.
- **Retrieve All Conversions**: Call the `getAllPossibleConversions` method.
- **Process Results**: Iterate through the returned `PossibleConversions` collection to explore all source and target format combinations.

{{< tabs "code-example1">}}
{{< tab "AllAvailableConversions.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.contracts.PossibleConversions;
import com.groupdocs.conversion.contracts.TargetConversion;
import java.util.List;
import java.util.stream.Collectors;
import java.util.stream.StreamSupport;

public class AllAvailableConversions {
    public static void convert() {
 // Get all possible conversions
        List<PossibleConversions> allPossibleConversions = Converter.getAllPossibleConversions();

        for (PossibleConversions possibleConversions : allPossibleConversions) {
            // Filter primary conversions
            List<String> primaryConversions = StreamSupport.stream(possibleConversions.getAll().spliterator(), false)
                    .filter(TargetConversion::isPrimary)
                    .map(conversion -> conversion.getFormat().getExtension())
                    .collect(Collectors.toList());

            // Filter secondary conversions
            List<String> secondaryConversions = StreamSupport.stream(possibleConversions.getAll().spliterator(),false)
                    .filter(conversion -> !conversion.isPrimary())
                    .map(conversion -> conversion.getFormat().getExtension())
                    .collect(Collectors.toList());

            // Print out the source format and its conversions
            System.out.println(" **Source format** : " + possibleConversions.getSource().getDescription());
            System.out.println("  - **Primary conversions**: " + primaryConversions);
            System.out.println("  - **Secondary conversions**: " + secondaryConversions);
            System.out.println();
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "Console Output" >}}  
 **Source format**: Drawing Exchange Format File (dxf)
  - **Primary conversions**: [dxf, ifc, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, fbx, 3ds, obj, u3d, glb, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: AutoCAD Drawing Database File (dwg)
  - **Primary conversions**: [dxf, dwf, ifc, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, fbx, 3ds, obj, u3d, glb, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: MicroStation Design File (dgn)
  - **Primary conversions**: [dxf, dwf, ifc, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, fbx, 3ds, obj, u3d, glb, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

<details>
<summary>See Complete List</summary>

**Source format**: Design Web Format File (dwf)
  - **Primary conversions**: [dxf, ifc, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, fbx, 3ds, obj, u3d, glb, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Stereolithography File (stl)
  - **Primary conversions**: [dxf, dwf, ifc, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Industry Foundation Classes File (ifc)
  - **Primary conversions**: [dxf, ifc, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, fbx, 3ds, obj, u3d, glb, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Initial Graphics Exchange Specification (IGES) (igs)
  - **Primary conversions**: [dxf, ifc, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, fbx, 3ds, obj, u3d, glb, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: AutoCAD Drawing Template (dwt)
  - **Primary conversions**: [dxf, dwf, ifc, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, fbx, 3ds, obj, u3d, glb, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Design Web Format File (dwfx)
  - **Primary conversions**: [dxf, ifc, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, fbx, 3ds, obj, u3d, glb, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Common File Format File (cf2)
  - **Primary conversions**: [dxf, ifc, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, fbx, 3ds, obj, u3d, glb, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: ZIP Compressed File (zip)
  - **Primary conversions**: [zip, 7z, tar, cpio, iso, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, eps, xps, tex, ps, pcl, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: []

 **Source format**: RAR Compressed Archive (rar)
  - **Primary conversions**: [zip, 7z, tar, cpio, iso, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, eps, xps, tex, ps, pcl, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: []

 **Source format**: 7-Zip Compressed File (7z)
  - **Primary conversions**: [zip, 7z, tar, cpio, iso, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, eps, xps, tex, ps, pcl, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: []

 **Source format**: Consolidated Unix File Archive (tar)
  - **Primary conversions**: [zip, 7z, tar, cpio, iso, uue, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, eps, xps, tex, ps, pcl, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: []

 **Source format**: Gnu Zipped Archive (gz)
  - **Primary conversions**: [gz, gzip, bz2, lz, z, xz, lzma, zst, uue, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, eps, xps, tex, ps, pcl, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: []

 **Source format**: Gzip Compressed File (gzip)
  - **Primary conversions**: [zip, 7z, tar, gz, gzip, bz2, lz, z, xz, cpio, lzma, zst, iso, uue, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, eps, xps, tex, ps, pcl, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: []

 **Source format**: Bzip2 Compressed File (bz2)
  - **Primary conversions**: [gz, gzip, bz2, lz, z, xz, lzma, zst, uue, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, eps, xps, tex, ps, pcl, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: []

 **Source format**: Lzip Compressed File (lz)
  - **Primary conversions**: [gz, gzip, bz2, lz, z, xz, lzma, zst, uue, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, eps, xps, tex, ps, pcl, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: []

 **Source format**: Unix Compressed File (z)
  - **Primary conversions**: [gz, gzip, bz2, lz, z, xz, lzma, zst, uue, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, eps, xps, tex, ps, pcl, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: []

 **Source format**: Xz Compressed File (xz)
  - **Primary conversions**: [gz, gzip, bz2, lz, z, xz, lzma, zst, uue, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, eps, xps, tex, ps, pcl, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: []

 **Source format**: CPIO Compressed File (cpio)
  - **Primary conversions**: [zip, 7z, tar, cpio, iso, uue, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, eps, xps, tex, ps, pcl, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: []

 **Source format**: Windows Cabinet File (cab)
  - **Primary conversions**: [zip, 7z, tar, gz, gzip, bz2, lz, z, xz, cpio, iso, uue, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, eps, xps, tex, ps, pcl, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: []

 **Source format**: LZMA Compressed File (lzma)
  - **Primary conversions**: [gz, gzip, bz2, lz, z, xz, lzma, zst, uue, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, eps, xps, tex, ps, pcl, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: []

 **Source format**: Zstandard (Zstd) Compressed File (zst)
  - **Primary conversions**: [gz, gzip, bz2, lz, z, xz, lzma, zst, uue, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, eps, xps, tex, ps, pcl, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: []

 **Source format**: ISO File Format (iso)
  - **Primary conversions**: [zip, 7z, tar, cpio, iso, uue, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, eps, xps, tex, ps, pcl, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: []

 **Source format**: Uuencoded archive (uue)
  - **Primary conversions**: [gz, gzip, bz2, lz, z, xz, lzma, zst, uue, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, eps, xps, tex, ps, pcl, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: []

 **Source format**: Visio Drawing File (vsd)
  - **Primary conversions**: [vsd, vsdx, vsx, vtx, vdx, vssx, vstx, vsdm, vssm, vstm, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Visio Drawing File (vsdx)
  - **Primary conversions**: [vsd, vsdx, vsx, vtx, vdx, vssx, vstx, vsdm, vssm, vstm, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Visio Stencil File (vss)
  - **Primary conversions**: [vsd, vsdx, vsx, vtx, vdx, vssx, vstx, vsdm, vssm, vstm, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Visio Drawing Template (vst)
  - **Primary conversions**: [vsd, vsdx, vsx, vtx, vdx, vssx, vstx, vsdm, vssm, vstm, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Visio Stencil XML File (vsx)
  - **Primary conversions**: [vsd, vsdx, vsx, vtx, vdx, vssx, vstx, vsdm, vssm, vstm, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Visio Template XML File (vtx)
  - **Primary conversions**: [vsd, vsdx, vsx, vtx, vdx, vssx, vstx, vsdm, vssm, vstm, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Visio Web Drawing (vdw)
  - **Primary conversions**: [vsd, vsdx, vsx, vtx, vdx, vssx, vstx, vsdm, vssm, vstm, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Visio Drawing XML File (vdx)
  - **Primary conversions**: [vsd, vsdx, vsx, vtx, vdx, vssx, vstx, vsdm, vssm, vstm, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Visio Stencil File (vssx)
  - **Primary conversions**: [vsd, vsdx, vsx, vtx, vdx, vssx, vstx, vsdm, vssm, vstm, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Visio Drawing Template (vstx)
  - **Primary conversions**: [vsd, vsdx, vsx, vtx, vdx, vssx, vstx, vsdm, vssm, vstm, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Visio Macro-Enabled Drawing (vsdm)
  - **Primary conversions**: [vsd, vsdx, vsx, vtx, vdx, vssx, vstx, vsdm, vssm, vstm, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Visio Macro-Enabled Stencil File (vssm)
  - **Primary conversions**: [vsd, vsdx, vsx, vtx, vdx, vssx, vstx, vsdm, vssm, vstm, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Visio Macro-Enabled Drawing Template (vstm)
  - **Primary conversions**: [vsd, vsdx, vsx, vtx, vdx, vssx, vstx, vsdm, vssm, vstm, epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: PLT (HPGL) (plt)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, fbx, 3ds, obj, u3d, glb, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Open eBook File (epub)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Mobipocket eBook (mobi)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Amazon Kindle�s proprietary e-book file format (azw3)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Outlook Mail Message (msg)
  - **Primary conversions**: [epub, mobi, azw3, eml, emlx, msg, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: E-Mail Message (eml)
  - **Primary conversions**: [epub, mobi, azw3, eml, emlx, msg, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Apple Mail Message (emlx)
  - **Primary conversions**: [epub, mobi, azw3, eml, emlx, msg, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Vcf document format (vcf)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Mbox document format (mbox)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: JSON based Geographic File Format (geojson)
  - **Primary conversions**: [geojson, kml, gpx, topojson, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Geography Markup Language File Format (gml)
  - **Primary conversions**: [geojson, kml, gpx, topojson, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Keyhole Markup Language (kml)
  - **Primary conversions**: [geojson, kml, gpx, topojson, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: GPS Exchange File Format (gpx)
  - **Primary conversions**: [geojson, kml, gpx, topojson, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: JSON based Topology File Format (topojson)
  - **Primary conversions**: [geojson, kml, gpx, topojson, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: OpenStreetMap File Format (osm)
  - **Primary conversions**: [geojson, kml, gpx, topojson, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Tagged Image File Format (tiff)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Tagged Image File Format (tif)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: JPEG Image (jpg)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: JPEG Image (jpeg)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Portable Network Graphic (png)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Graphical Interchange Format File (gif)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Bitmap Image File (bmp)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Icon File (ico)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Adobe Photoshop Document (psd)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Windows Metafile (wmf)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Enhanced Windows Metafile (emf)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: DICOM Image (dcm)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: DICOM Image (dicom)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: WebP Image (webp)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Digital Negative Specification (dng)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: JPEG 2000 Core Image File (jp2)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: OpenDocument Graphic File (odg)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: JPEG 2000 Code Stream (j2c)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: JPEG 2000 Code Stream (j2k)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: JPEG 2000 Image File (jpx)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: JPEG 2000 Image File (jpf)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: JPEG 2000 Image File (jpm)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: CorelDraw Vector Graphic Drawing (cdr)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Corel Metafile Exchange (cmx)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Device Independent Bitmap File (dib)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: JPEG 2000 Code Stream (jpc)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: DjVu Image (djvu)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: OpenDocument Graphic Template (otg)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Adobe Illustrator Artwork (ai)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Windows Compressed Enhanced Metafile (emz)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Compressed Windows Metafile (wmz)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Compressed Scalable Vector Graphics File (svgz)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Truevision TGA (TARGA) (tga)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Adobe Photoshop Big (psb)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Flat XML ODF Template (fodg)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: JPEG File Interchange Format (jfif)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: HEIC File Format (heic)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: OneNote Document (one)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Scalable Vector Graphics File (svg)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Encapsulated PostScript File (eps)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Computer Graphics Metafile (cgm)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]
  - **Secondary conversions**: [eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: XML Paper Specification File (xps)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: LaTeX Source Document (tex)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: PostScript File (ps)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Printer Command Language Document (pcl)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: XML Paper Specification File (oxps)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Portable Document Format File (pdf)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: PowerPoint Presentation (ppt)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: PowerPoint Slide Show (pps)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: PowerPoint Open XML Presentation (pptx)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: PowerPoint Open XML Slide Show (ppsx)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: OpenDocument Flat XML Presentation (odp)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: OpenDocument Presentation Template (otp)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: PowerPoint Open XML Presentation Template (potx)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: PowerPoint Template (pot)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: PowerPoint Open XML Macro-Enabled Presentation Template (potm)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: PowerPoint Open XML Macro-Enabled Presentation (pptm)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: PowerPoint Open XML Macro-Enabled Slide (ppsm)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: OpenDocument Flat XML Presentation (fodp)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Microsoft Project Template (mpt)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, mpp, mpx, xer, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Microsoft Project File (mpp)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, mpp, mpx, xer, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Microsoft Project Exchange File (mpx)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, mpp, mpx, xer, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Primavera XER format (xer)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, mpp, mpx, xer, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Outlook Personal Information Store File (pst)
  - **Primary conversions**: [epub, mobi, azw3, eml, emlx, msg, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Outlook Offline Data File (ost)
  - **Primary conversions**: [epub, mobi, azw3, eml, emlx, msg, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Lotus Notes Storage Format (nsf)
  - **Primary conversions**: [epub, mobi, azw3, eml, emlx, msg, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Microsoft Outlook file for Mac Operating System. (olm)
  - **Primary conversions**: [epub, mobi, azw3, eml, emlx, msg, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Excel Spreadsheet (xls)
  - **Primary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, json, xml]
  - **Secondary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Microsoft Excel Open XML Spreadsheet (xlsx)
  - **Primary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, json, xml]
  - **Secondary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Excel Open XML Macro-Enabled Spreadsheet (xlsm)
  - **Primary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, json, xml]
  - **Secondary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Excel Binary Spreadsheet (xlsb)
  - **Primary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, json, xml]
  - **Secondary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: OpenDocument Spreadsheet (ods)
  - **Primary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, json, xml]
  - **Secondary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: OpenDocument Spreadsheet Template (ots)
  - **Primary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, json, xml]
  - **Secondary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Excel Open XML Spreadsheet Template (xltx)
  - **Primary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, json, xml]
  - **Secondary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Microsoft Excel Macro-Enabled Template (xlt)
  - **Primary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, json, xml]
  - **Secondary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Microsoft Excel Macro-Enabled Template (xltm)
  - **Primary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, json, xml]
  - **Secondary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Tab Separated Values File (tsv)
  - **Primary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, json, xml]
  - **Secondary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Microsoft Excel Add-in (xlam)
  - **Primary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, json, xml]
  - **Secondary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Csv document format (csv)
  - **Primary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, json, xml]
  - **Secondary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: OpenDocument Flat XML Spreadsheet (fods)
  - **Primary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, json, xml]
  - **Secondary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: StarOffice Calc Spreadsheet (sxc)
  - **Primary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, json, xml]
  - **Secondary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: Apple iWork Numbers (numbers)
  - **Primary conversions**: [epub, mobi, azw3, eps, xps, tex, ps, pcl, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, htm, html, mhtml, mht, json, xml]
  - **Secondary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]

 **Source format**: CHM File (chm)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Hypertext Markup Language File (htm)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Hypertext Markup Language File (html)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: MIME HTML File (mhtml)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: MHTML Web Archive (mht)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Microsoft Word Document (doc)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Word Open XML Macro-Enabled Document (docm)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Microsoft Word Open XML Document (docx)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Word Document Template (dot)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Word Open XML Macro-Enabled Document Template (dotm)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Word Open XML Document Template (dotx)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Rich Text Format File (rtf)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: OpenDocument Text Document (odt)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: OpenDocument Document Template (ott)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Plain Text File (txt)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Markdown Documentation File (md)
  - **Primary conversions**: [epub, mobi, azw3, tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: XML File (xml)
  - **Primary conversions**: [epub, mobi, azw3, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, json, xml, htm, html, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]

 **Source format**: Json File (json)
  - **Primary conversions**: [epub, mobi, azw3, pdf, xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc, json, xml, htm, html, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp]

 **Source format**: Extensible Business Reporting Language. (xbrl)
  - **Primary conversions**: [xbrl, ixbrl]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Inline XBRL. (ixbrl)
  - **Primary conversions**: [xbrl, ixbrl]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: TrueType Font (Ttf)
  - **Primary conversions**: [Ttf, woff, woff2]
  - **Secondary conversions**: []

 **Source format**: Embedded OpenType Font Format (eot)
  - **Primary conversions**: [Ttf, woff, woff2]
  - **Secondary conversions**: []

 **Source format**: OpenType font (otf)
  - **Primary conversions**: [Ttf, woff, woff2]
  - **Secondary conversions**: []

 **Source format**: Compact Font Format (cff)
  - **Primary conversions**: [Ttf, woff, woff2]
  - **Secondary conversions**: []

 **Source format**: PostScript Fonts (pfb)
  - **Primary conversions**: [Ttf, woff, woff2]
  - **Secondary conversions**: []

 **Source format**: Web Open Font Format (woff)
  - **Primary conversions**: [Ttf, woff, woff2]
  - **Secondary conversions**: []

 **Source format**: Web Open Font Format 2 (woff2)
  - **Primary conversions**: [Ttf, woff, woff2]
  - **Secondary conversions**: []

 **Source format**: Log File (log)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Sql File (sql)
  - **Primary conversions**: [tiff, tif, jpg, jpeg, png, gif, bmp, ico, psd, wmf, emf, dcm, dicom, webp, jp2, j2k, emz, wmz, svgz, tga, psb, jfif, eps, xps, tex, ps, pcl, svg, pdf, ppt, pps, pptx, ppsx, odp, otp, potx, pot, potm, pptm, ppsm, fodp, htm, html, mhtml, mht, doc, docm, docx, dot, dotm, dotx, rtf, odt, ott, txt, md]
  - **Secondary conversions**: [xls, xlsx, xlsm, xlsb, ods, xltx, xlt, xltm, tsv, xlam, csv, fods, dif, sxc]

 **Source format**: Microsoft Publisher format (pub)
  - **Primary conversions**: [pdf]
  - **Secondary conversions**: []

 **Source format**: FilmBox format (fbx)
  - **Primary conversions**: [pdf, fbx, 3ds, amf, rvm, dae, drc, gltf, obj, ply, u3d, usd, usdz, glb]
  - **Secondary conversions**: []

 **Source format**: 3D Studio (3ds)
  - **Primary conversions**: [pdf, fbx, 3ds, amf, rvm, dae, drc, gltf, obj, ply, u3d, usd, usdz, glb]
  - **Secondary conversions**: []

 **Source format**: Microsoft 3D Manufacturing Format (3mf)
  - **Primary conversions**: [pdf, fbx, 3ds, amf, rvm, dae, drc, gltf, obj, ply, u3d, usd, usdz, glb]
  - **Secondary conversions**: []

 **Source format**: Additive manufacturing file format (amf)
  - **Primary conversions**: [pdf, fbx, 3ds, amf, rvm, dae, drc, gltf, obj, ply, u3d, usd, usdz, glb]
  - **Secondary conversions**: []

 **Source format**: 3D Studio Max�s ASCII Scene Exporter format (ase)
  - **Primary conversions**: [pdf, fbx, 3ds, amf, rvm, dae, drc, gltf, obj, ply, u3d, usd, usdz, glb]
  - **Secondary conversions**: []

 **Source format**: AVEVA Plant Design Management System Model (rvm)
  - **Primary conversions**: [pdf, fbx, 3ds, amf, rvm, dae, drc, gltf, obj, ply, u3d, usd, usdz, glb]
  - **Secondary conversions**: []

 **Source format**: Collada (dae)
  - **Primary conversions**: [pdf, fbx, 3ds, amf, rvm, dae, drc, gltf, obj, ply, u3d, usd, usdz, glb]
  - **Secondary conversions**: []

 **Source format**: Google Draco (drc)
  - **Primary conversions**: [pdf, fbx, 3ds, amf, rvm, dae, drc, gltf, obj, ply, u3d, usd, usdz, glb]
  - **Secondary conversions**: []

 **Source format**: Khronos Group�s glTF (gltf)
  - **Primary conversions**: [pdf, fbx, 3ds, amf, rvm, dae, drc, gltf, obj, ply, u3d, usd, usdz, glb]
  - **Secondary conversions**: []

 **Source format**: Wavefront Obj (obj)
  - **Primary conversions**: [pdf, fbx, 3ds, amf, rvm, dae, drc, gltf, obj, ply, u3d, usd, usdz, glb]
  - **Secondary conversions**: []

 **Source format**: Polygon File Format or Stanford Triangle Format (ply)
  - **Primary conversions**: [pdf, fbx, 3ds, amf, rvm, dae, drc, gltf, obj, ply, u3d, usd, usdz, glb]
  - **Secondary conversions**: []

 **Source format**: Siemens JT File (jt)
  - **Primary conversions**: [pdf, fbx, 3ds, amf, rvm, dae, drc, gltf, obj, ply, u3d, usd, usdz, glb]
  - **Secondary conversions**: []

 **Source format**: Universal3D (u3d)
  - **Primary conversions**: [pdf, fbx, 3ds, amf, rvm, dae, drc, gltf, obj, ply, u3d, usd, usdz, glb]
  - **Secondary conversions**: []

 **Source format**: Universal Scene Description (usd)
  - **Primary conversions**: [pdf, fbx, 3ds, amf, rvm, dae, drc, gltf, obj, ply, u3d, usd, usdz, glb]
  - **Secondary conversions**: []

 **Source format**: Universal Scene Description Archive (usdz)
  - **Primary conversions**: [pdf, fbx, 3ds, amf, rvm, dae, drc, gltf, obj, ply, u3d, usd, usdz, glb]
  - **Secondary conversions**: []

 **Source format**: The Virtual Reality Modeling Language (vrml)
  - **Primary conversions**: [pdf, fbx, 3ds, amf, rvm, dae, drc, gltf, obj, ply, u3d, usd, usdz, glb]
  - **Secondary conversions**: []

 **Source format**: DirectX's X file (x)
  - **Primary conversions**: [pdf, fbx, 3ds, amf, rvm, dae, drc, gltf, obj, ply, u3d, usd, usdz, glb]
  - **Secondary conversions**: []

 **Source format**: GLB file (glb)
  - **Primary conversions**: [pdf, fbx, 3ds, amf, rvm, dae, drc, gltf, obj, ply, u3d, usd, usdz, glb]
  - **Secondary conversions**: []

 **Source format**: Autodesk Maya ASCII (ma)
  - **Primary conversions**: [pdf, fbx, 3ds, amf, rvm, dae, drc, gltf, obj, ply, u3d, usd, usdz, glb]
  - **Secondary conversions**: []

 **Source format**: Autodesk Maya Binary (mb)
  - **Primary conversions**: [pdf, fbx, 3ds, amf, rvm, dae, drc, gltf, obj, ply, u3d, usd, usdz, glb]
  - **Secondary conversions**: []

</details>
{{< /tab >}}
{{< /tabs >}}

By utilizing these API features, you can provide dynamic, user-friendly document conversion capabilities tailored to your application's needs.