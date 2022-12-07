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
Salient features of file conversion API using C# is described in this article.

GroupDocs.Conversion main feature is an ability to convert any document from wide list of supported source document formats into any supported target format (check full list of supported conversions [here]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}})). All these conversions are possible without any additional software installed (like Microsoft Office, Apache Open Office, Adobe Acrobat Reader and others).
GroupDocs.Conversion provides flexible set of settings to customize conversion process to fulfill your needs:

### Convert specific document page(s)

Along with the whole document conversion to desired target format it could be useful to convert specific document pages or page range. To such partial document conversion you should specify desired pages numbers to convert using [Pages](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/commonconvertoptions-1/pages) property of ConvertOptions class.

### Auto-detect source document format

In some cases the source file could be presented in a form of bytes stream, so the file extension is unknown.
Luckily GroupDocs.Conversion for .NET is smart enough to detect source document format on the fly.

### Load source document with extended options

There are lots of modifications that are possible during file conversion process:

- specify password for [password-protected documents]({{< ref "conversion/net/developer-guide/advanced-usage/loading/load-password-protected-document.md" >}});
- show/hide document [comments]({{< ref "conversion/net/developer-guide/advanced-usage/loading/load-options-for-different-document-types/load-wordprocessing-document-with-options.md" >}}) and [annotations]({{< ref "conversion/net/developer-guide/advanced-usage/loading/load-options-for-different-document-types/load-pdf-document-with-options.md" >}});
- [show/hide markup and track changes]({{< ref "conversion/net/developer-guide/advanced-usage/loading/load-options-for-different-document-types/load-wordprocessing-document-with-options.md" >}}) for Word documents;
- [show hidden sheets]({{< ref "conversion/net/developer-guide/advanced-usage/loading/load-options-for-different-document-types/load-spreadsheet-document-with-options.md" >}}) when converting Excel files or not;
- set the [text file encoding]({{< ref "conversion/net/developer-guide/advanced-usage/loading/load-options-for-different-document-types/load-txt-document-with-options.md" >}}) and many more;

### Obtain all supported conversion formats list

You can programmatically obtain the [complete list of possible conversions]({{< ref "conversion/net/developer-guide/advanced-usage/loading/get-default-load-options-for-source-document.md" >}}) that are supported by GroupDocs.Conversion for .NET library.
Also it's possible to get [allowed conversions]({{< ref "conversion/net/developer-guide/advanced-usage/converting/common-conversion-options/get-default-convert-options-for-target-format.md" >}}) for specific file format.

### Fonts replacement

It is a common use case when a source document references to some specific fonts that are not present in the environment where you launch your application. GroupDocs.Conversion for .NET provides a solution - you can [substitute missing fonts]({{< ref "conversion/net/developer-guide/advanced-usage/loading/load-options-for-different-document-types/load-wordprocessing-document-with-options#specify-font-substitution" >}}) with fonts of your choice that will preserve your document appearance.

### Watermarking converted document

You can [add a text or an image watermarks]({{< ref "conversion/net/developer-guide/advanced-usage/converting/common-conversion-options/add-watermark.md" >}}) to any page of converted document and choose its desired size, color and font size.

## Caching results

GroupDocs.Conversion supports [conversion result caching]({{< ref "conversion/net/developer-guide/advanced-usage/caching/" >}}) to local disk by default. However any type of cache storage can be supported by implementing appropriate interfaces – Amazon S3, Dropbox, Google Drive, Windows Azure, Reddis or any other.

## Document information extraction

GroupDocs.Conversion allows to obtain basic information about source document - file type, pages count etc. Dependent on source file type some format specific information can be extracted, for example:

- [CAD]({{< ref "conversion/net/developer-guide/advanced-usage/loading/load-options-for-different-document-types/load-cad-document-with-options.md" >}}) - list of layers and layouts in a CAD document;
- [Email]({{< ref "conversion/net/developer-guide/advanced-usage/loading/load-options-for-different-document-types/load-email-document-with-options.md" >}}) – list of folders contained in an Outlook data file document;
- [PDF]({{< ref "conversion/net/developer-guide/advanced-usage/loading/load-options-for-different-document-types/load-pdf-document-with-options.md" >}}) – information about document printing restrictions;
- Project Management – project start and end dates.


## Load documents from different sources

- [Local disc]({{< ref "conversion/net/developer-guide/advanced-usage/loading/loading-documents-from-different-sources/load-document-from-local-disk.md" >}})
- [Stream]({{< ref "conversion/net/developer-guide/advanced-usage/loading/loading-documents-from-different-sources/load-document-from-stream.md" >}})
- [FTP]({{< ref "conversion/net/developer-guide/advanced-usage/loading/loading-documents-from-different-sources/load-document-from-ftp.md" >}})
- [URL]({{< ref "conversion/net/developer-guide/advanced-usage/loading/loading-documents-from-different-sources/load-document-from-url.md" >}})
- Cloud: [Amazon S3]({{< ref "conversion/net/developer-guide/advanced-usage/loading/loading-documents-from-different-sources/load-document-from-amazon-s3-storage.md" >}}), [Azure]({{< ref "conversion/net/developer-guide/advanced-usage/loading/loading-documents-from-different-sources/load-document-from-azure-blob-storage.md" >}}).
