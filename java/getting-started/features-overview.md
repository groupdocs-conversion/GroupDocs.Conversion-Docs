---
id: features-overview
url: conversion/java/features-overview
title: Features overview
weight: 3
description: "Salient features of file conversion API using Java are described in this article"
keywords: file conversion
productName: GroupDocs.Conversion for Java
hideChildren: False
toc: True
---
## File conversion

GroupDocs.Conversion main feature is the ability to convert any document from any of supported source document formats into any supported target format (check the list of  [supported formats]({{< ref "conversion/java/supported-document-formats.md" >}})). All these conversions are possible without any additional software installed (like MS Office, Apache Open Office, Adobe Acrobat Reader and others).
GroupDocs.Conversion provides a flexible set of settings to customize the conversion process to fulfill your needs:

### Convert specific document page(s)

Along with the whole document conversion to the desired target format, it could be useful to convert specific document pages or page ranges. For such partial document conversion, you should specify desired page numbers to convert using the [setPages](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ConvertOptions#setPages%28java.util.List%29) property of the `ConvertOptions` class.

### Auto-detect source document format

In some cases, the source file could be presented in a form of a byte stream, so the file extension is unknown.
Luckily GroupDocs.Conversion for Java is smart enough to detect source document format on the fly.

### Load source document with extended options

There are lots of modifications that are possible during the file conversion process:

- specify a password for [password-protected documents]({{< ref "conversion/java/developer-guide/loading-documents/load-password-protected-document.md" >}});
- show/hide document [comments]({{< ref "conversion/java/developer-guide/loading-documents/load-options-for-different-document-types/load-wordprocessing-document-with-options.md" >}}) and [annotations]({{< ref "conversion/java/developer-guide/loading-documents/load-options-for-different-document-types/load-pdf-document-with-options.md" >}});
- [show/hide markup and track changes]({{< ref "conversion/java/developer-guide/loading-documents/load-options-for-different-document-types/load-wordprocessing-document-with-options.md" >}}) for Word documents;
- [show hidden sheets]({{< ref "conversion/java/developer-guide/loading-documents/load-options-for-different-document-types/load-spreadsheet-document-with-options.md" >}}) when converting Excel files or not;
- set the [text file encoding]({{< ref "conversion/java/developer-guide/loading-documents/load-options-for-different-document-types/load-txt-document-with-options.md" >}}) and many more;

### Obtain all supported conversion formats list

You can obtain the [complete list of possible conversions]({{< ref "conversion/java/developer-guide/converting-documents/basic-usage/get-possible-conversions.md" >}}) that are supported by GroupDocs.Conversion for Java library. Also, it is possible to get allowed conversions for the specific file format.

### Fonts replacement

It is a common use case when a source document references some specific fonts that are not present in the environment where you launch your application. GroupDocs.Conversion for Java provides a solution - you can [substitute missing fonts]({{< ref "conversion/java/developer-guide/loading-documents/load-options-for-different-document-types/load-wordprocessing-document-with-options#specify-font-substitution" >}}) with fonts of your choice that will preserve your document appearance.

### Watermarking converted document

You can [add a text or an image watermark]({{< ref "conversion/java/developer-guide/converting-documents/advanced-usage/converting/common-conversion-options/add-watermark.md" >}}) to any page of the converted document and choose its desired dimensions, color and font size.

## Document information extraction

GroupDocs.Conversion allows to obtain basic [information about source document]({{< ref "conversion/java/developer-guide/get-document-info.md" >}}) - file type, pages count etc. Dependent on the source file type some format-specific information can be extracted, for example:

- CAD - list of layers and layouts in a CAD document;
- Email – list of attachments;
- PDF – title, author, table of contents and more;
- Project Management – project start and end dates.

## Load documents from different sources

With GroupDocs.Conversion you are not limited to [local files]({{< ref "conversion/java/developer-guide/loading-documents/loading-documents-from-different-sources/load-document-from-local-disk.md" >}}) only. It also supports loading documents from [stream]({{< ref "conversion/java/developer-guide/loading-documents/loading-documents-from-different-sources/load-document-from-stream.md" >}}), [FTP]({{< ref "conversion/java/developer-guide/loading-documents/loading-documents-from-different-sources/load-document-from-ftp.md" >}}), [remote URLs]({{< ref "conversion/java/developer-guide/loading-documents/loading-documents-from-different-sources/load-document-from-url.md" >}}), as wel as from [Amazon S3]({{< ref "conversion/java/developer-guide/loading-documents/loading-documents-from-different-sources/load-document-from-amazon-s3-storage.md" >}}) and [Azure]({{< ref "conversion/java/developer-guide/loading-documents/loading-documents-from-different-sources/load-document-from-azure-blob-storage.md" >}}) clouds.

## Caching results

GroupDocs.Conversion supports [conversion result caching]({{< ref "conversion/java/developer-guide/converting-documents/advanced-usage/caching/" >}}) to local disk by default. However, any type of cache storage can be supported by implementing appropriate interfaces – Amazon S3, Dropbox, Google Drive, Windows Azure, Redis or any other.

## Work with archives
It is possible to convert archived files to all supported formats or just extract files. Also, you can archive the result of the conversion.