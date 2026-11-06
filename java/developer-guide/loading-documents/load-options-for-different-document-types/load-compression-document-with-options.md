---
id: load-compression-document-with-options
url: conversion/java/load-compression-document-with-options
title: Load compression document with options
weight: 20
description: "Configure archive loading with CompressionLoadOptions in GroupDocs.Conversion for Java, including ISO and UUE."
keywords: CompressionLoadOptions, archive loading, ZIP, ISO, UUE, archive password
productName: GroupDocs.Conversion for Java
hideChildren: False
toc: True
---

Use `CompressionLoadOptions` to specify the source archive format, provide a password, or control how deeply nested contents are processed. Pass the options through a load-options provider when constructing `Converter`.

## Available options

| Option | Description |
|--------|-------------|
| `setFormat(CompressionFileType)` | Explicitly specifies the source format. Leave it unset to use format detection. |
| `setPassword(String)` | Supplies the password for a protected source archive. |
| `setDepth(int)` | Sets the recursion depth for processing nested documents. The default is `3`. |
| `isConvertOwned()` | Returns `true`: contained documents are processed. This property is read-only. |
| `isConvertOwner()` | Returns `false`: the archive itself is not rendered as a document. This property is read-only. |

The Java 26.10 compression file types include ZIP, RAR, 7Z, TAR, CPIO, CAB, GZ/GZIP, BZ2, LZ, LZMA, XZ, Z, ZST, ISO, and UUE. Available output formats depend on the source format. Use [Getting Possible Conversions]({{< ref "conversion/java/developer-guide/converting-documents/basic-usage/get-possible-conversions.md" >}}) to inspect them.

## Specify the source format

This example loads an ISO image explicitly and converts it to a ZIP archive. Specifying the format is useful when loading a stream or a file with an ambiguous extension.

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.filetypes.CompressionFileType;
import com.groupdocs.conversion.options.convert.CompressionConvertOptions;
import com.groupdocs.conversion.options.load.CompressionLoadOptions;

public class LoadIsoWithOptions {
    public static void main(String[] args) {
        CompressionLoadOptions loadOptions = new CompressionLoadOptions();
        loadOptions.setFormat(CompressionFileType.Iso);

        CompressionConvertOptions convertOptions = new CompressionConvertOptions();
        convertOptions.setFormat(CompressionFileType.Zip);

        try (Converter converter = new Converter("sample.iso", () -> loadOptions)) {
            converter.convert("converted.zip", convertOptions);
        }
    }
}
```

## Load a password-protected archive

Use the load-options password for the source archive. A password assigned to `CompressionConvertOptions`, where supported, controls the output archive instead.

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.filetypes.CompressionFileType;
import com.groupdocs.conversion.options.convert.CompressionConvertOptions;
import com.groupdocs.conversion.options.load.CompressionLoadOptions;

public class LoadProtectedZip {
    public static void main(String[] args) {
        CompressionLoadOptions loadOptions = new CompressionLoadOptions();
        loadOptions.setFormat(CompressionFileType.Zip);
        loadOptions.setPassword("archive-password");

        CompressionConvertOptions convertOptions = new CompressionConvertOptions();
        convertOptions.setFormat(CompressionFileType.SevenZ);

        try (Converter converter = new Converter("protected.zip", () -> loadOptions)) {
            converter.convert("converted.7z", convertOptions);
        }
    }
}
```

## Convert the contents of an archive

Loading an archive and converting its contained documents to PDF is a different operation from changing the archive format. Set the nesting depth in `CompressionLoadOptions` and supply a separate output stream for each converted item, as shown in [Convert compression files]({{< ref "conversion/java/developer-guide/converting-documents/basic-usage/convert/compression.md" >}}).

For archive-to-archive examples, including ISO and UUE, see [Convert archive formats]({{< ref "conversion/java/developer-guide/converting-documents/advanced-usage/converting/conversion-options-by-document-family/convert-to-compression-with-advanced-options.md" >}}).
