---
id: features-overview
url: conversion/net/features-overview
title: Features overview
weight: 1
description: "Salient features of file conversion API using c# are described in this article"
keywords: file conversion
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

## File conversion
This article describes the salient features of file conversion API using C#.

GroupDocs.Conversion main feature is the ability to convert any document from a wide list of supported source document formats into any supported target format (check the full list of [supported formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}})). All these conversions are possible without any additional software installed (like Microsoft Office, Apache Open Office, Adobe Acrobat Reader and others).
GroupDocs.Conversion provides a flexible set of settings to customize the conversion process to fulfill your needs:

### Convert specific document page(s)

Along with the whole document conversion to the desired target format, it could be useful to convert specific document pages or page ranges. For such partial document conversion, you should specify desired page numbers to convert using the [Pages](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/commonconvertoptions-1/pages) property of the `ConvertOptions` class.

### Auto-detect source document format

In some cases the source file could be presented in a form of a byte stream, so the file extension is unknown.
Luckily GroupDocs.Conversion for .NET is smart enough to detect source document format on the fly.

### Load source document with extended options

There are lots of modifications that are possible during the file conversion process:

- specify password for [password-protected documents]({{< ref "conversion/net/developer-guide/advanced-usage/loading/load-password-protected-document.md" >}});
- show/hide document [comments]({{< ref "conversion/net/developer-guide/advanced-usage/loading/load-options-for-different-document-types/load-wordprocessing-document-with-options.md" >}}) and [annotations]({{< ref "conversion/net/developer-guide/advanced-usage/loading/load-options-for-different-document-types/load-pdf-document-with-options.md" >}});
- [show/hide markup and track changes]({{< ref "conversion/net/developer-guide/advanced-usage/loading/load-options-for-different-document-types/load-wordprocessing-document-with-options.md" >}}) for Word documents;
- [show hidden sheets]({{< ref "conversion/net/developer-guide/advanced-usage/loading/load-options-for-different-document-types/load-spreadsheet-document-with-options.md" >}}) when converting Excel files or not;
- set the [text file encoding]({{< ref "conversion/net/developer-guide/advanced-usage/loading/load-options-for-different-document-types/load-txt-document-with-options.md" >}}) and many more;

### Obtain all supported conversion formats list

You can programmatically obtain the [complete list of possible conversions]({{< ref "conversion/net/developer-guide/advanced-usage/loading/get-default-load-options-for-source-document.md" >}}) that are supported by GroupDocs.Conversion for .NET library. Also, it's possible to get [allowed conversions]({{< ref "conversion/net/developer-guide/advanced-usage/converting/common-conversion-options/get-default-convert-options-for-target-format.md" >}}) for the specific file format.

### Fonts replacement

It is a common use case when a source document references some specific fonts that are not present in the environment where you launch your application. GroupDocs.Conversion for .NET provides a solution - you can [substitute missing fonts]({{< ref "conversion/net/developer-guide/advanced-usage/loading/load-options-for-different-document-types/load-wordprocessing-document-with-options#specify-font-substitution" >}}) with fonts of your choice that will preserve your document appearance.

### Watermarking converted document

You can [add a text or an image watermark]({{< ref "conversion/net/developer-guide/advanced-usage/converting/common-conversion-options/add-watermark.md" >}}) to any page of the converted document and choose its desired dimensions, color and font size.

## Document information extraction

GroupDocs.Conversion allows to obtain basic [information about source document]({{< ref "conversion/net/developer-guide/basic-usage/get-document-info.md" >}}) - file type, pages count etc. Dependent on the source file type some format-specific information can be extracted, for example:

- [CAD]({{< ref "conversion/net/developer-guide/basic-usage/get-document-info.md#cad-drawings" >}}) - list of layers and layouts in a CAD document;
- [Email]({{< ref "conversion/net/developer-guide/basic-usage/get-document-info.md#emails" >}}) – list of attachments;
- [PDF]({{< ref "conversion/net/developer-guide/basic-usage/get-document-info.md#pdf-documents" >}}) – title, author, table of contents and more;
- [Project Management]({{< ref "conversion/net/developer-guide/basic-usage/get-document-info.md#project-management-documents" >}}) – project start and end dates.

## Load documents from different sources

With GroupDocs.Conversion you are not limited to [local files]({{< ref "conversion/net/developer-guide/advanced-usage/loading/loading-files-from-different-sources/load-file-from-local-disk.md" >}}) only. It also supports loading documents from [stream]({{< ref "conversion/net/developer-guide/advanced-usage/loading/loading-files-from-different-sources/load-file-from-stream.md" >}}), [FTP]({{< ref "conversion/net/developer-guide/advanced-usage/loading/loading-files-from-different-sources/load-file-from-ftp.md" >}}), [remote URLs]({{< ref "conversion/net/developer-guide/advanced-usage/loading/loading-files-from-different-sources/load-file-from-url.md" >}}), as wel as from [Amazon S3]({{< ref "conversion/net/developer-guide/advanced-usage/loading/loading-files-from-different-sources/load-file-from-amazon-s3-storage.md" >}}) and [Azure]({{< ref "conversion/net/developer-guide/advanced-usage/loading/loading-files-from-different-sources/load-file-from-azure-blob-storage.md" >}}) clouds.

## Caching results

GroupDocs.Conversion supports [conversion result caching]({{< ref "conversion/net/developer-guide/advanced-usage/caching/" >}}) to local disk by default. However, any type of cache storage can be supported by implementing appropriate interfaces – Amazon S3, Dropbox, Google Drive, Windows Azure, Reddis or any other.

