---
id: convert-to-compression-with-advanced-options
url: conversion/java/convert-to-compression-with-advanced-options
title: Convert archive formats
weight: 19
description: "Convert archive formats with CompressionConvertOptions in GroupDocs.Conversion for Java, including ZIP to ISO and GZIP to UUE."
keywords: CompressionConvertOptions, ZIP to ISO, ISO to ZIP, GZIP to UUE, UUE to GZIP
productName: GroupDocs.Conversion for Java
hideChildren: False
toc: True
---

Use `CompressionConvertOptions` to change the archive format while retaining its contained files. For example, convert a ZIP archive into an ISO image, or re-encode single-file compressed data from GZIP into UUE.

To convert the documents inside an archive to PDF instead, see [Convert compression files]({{< ref "conversion/java/developer-guide/converting-documents/basic-usage/convert/compression.md" >}}).

## Convert ZIP to ISO

Set `CompressionConvertOptions.setFormat` to the desired output format and pass the options to `Converter.convert`.

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.filetypes.CompressionFileType;
import com.groupdocs.conversion.options.convert.CompressionConvertOptions;

public class ConvertZipToIso {
    public static void main(String[] args) {
        CompressionConvertOptions options = new CompressionConvertOptions();
        options.setFormat(CompressionFileType.Iso);

        try (Converter converter = new Converter("sample.zip")) {
            converter.convert("converted.iso", options);
        }
    }
}
```

For the reverse conversion, load `sample.iso`, use `CompressionFileType.Zip`, and save to `converted.zip`. Java 26.10 also provides conversion between ISO and TAR, CPIO, or 7Z archives.

## Convert GZIP to UUE

UUE encodes a single file. This example changes a GZIP-compressed payload into UUE without converting the payload document itself.

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.filetypes.CompressionFileType;
import com.groupdocs.conversion.options.convert.CompressionConvertOptions;
import com.groupdocs.conversion.options.load.CompressionLoadOptions;

public class ConvertGzipToUue {
    public static void main(String[] args) {
        CompressionLoadOptions loadOptions = new CompressionLoadOptions();
        loadOptions.setFormat(CompressionFileType.Gzip);

        CompressionConvertOptions options = new CompressionConvertOptions();
        options.setFormat(CompressionFileType.Uue);

        try (Converter converter = new Converter("sample.gz", () -> loadOptions)) {
            converter.convert("converted.uue", options);
        }
    }
}
```

## Convert UUE to GZIP

Specify UUE as the source and GZIP as the target:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.filetypes.CompressionFileType;
import com.groupdocs.conversion.options.convert.CompressionConvertOptions;
import com.groupdocs.conversion.options.load.CompressionLoadOptions;

public class ConvertUueToGzip {
    public static void main(String[] args) {
        CompressionLoadOptions loadOptions = new CompressionLoadOptions();
        loadOptions.setFormat(CompressionFileType.Uue);

        CompressionConvertOptions options = new CompressionConvertOptions();
        options.setFormat(CompressionFileType.Gzip);

        try (Converter converter = new Converter("sample.uue", () -> loadOptions)) {
            converter.convert("converted.gz", options);
        }
    }
}
```

## Choose a supported target

Not every source archive can be converted to every target format. Check the source's available targets with [Getting Possible Conversions]({{< ref "conversion/java/developer-guide/converting-documents/basic-usage/get-possible-conversions.md" >}}) before choosing `CompressionFileType`.

Use a complete-document output path or stream for archive conversion. Page-by-page output is not supported for the ISO and UUE conversions shown here. Converting an ordinary PDF or Word document directly to an archive is also a different operation; these examples require an archive or single-file compression format as input.

For explicit source formats and source archive passwords, see [Load compression document with options]({{< ref "conversion/java/developer-guide/loading-documents/load-options-for-different-document-types/load-compression-document-with-options.md" >}}).
