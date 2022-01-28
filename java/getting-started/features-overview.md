---
id: features-overview
url: conversion/java/features-overview
title: Features Overview
weight: 1
description: "This is an overview of GroupDocs.Conversion for Java library features and capabilities"
keywords: 
productName: GroupDocs.Conversion for Java
hideChildren: False
toc: True
---
## Document conversion

GroupDocs.Conversion main feature is an ability to convert any document from wide list of supported source document formats into any supported target format (check full list of supported conversions [here]({{< ref "conversion/java/getting-started/supported-document-formats.md" >}})). All these conversions are possible without any additional software installed (like MS Office, Apache Open Office, Adobe Acrobat Reader and others).
GroupDocs.Conversion provides flexible set of settings to customize conversion process to fulfill your needs:

### Convert specific document page(s)

Along with the whole document conversion to desired target format it may be useful to convert specific document pages or page range. To such partial document conversion you should specify desired pages numbers to convert using `Pages` property of ConvertOptions class.

### Auto-detect source document format

In some cases the source file could be presented in a form of bytes stream, so the file extension is unknown.
Luckily GroupDocs.Conversion for Java is smart enough to detect source document format on the fly.

### Load source document with extended options

There are lots of modifications that are possible during file conversion process:

- specify password for password-protected documents;
- show/hide document comments and annotations;
- show/hide markup and track changes for Word documents;
- show hidden sheets when converting Excel files or not;
- set the text file encoding and many more;

### Obtain all supported conversion formats list

You can programmatically obtain the complete list of possible conversions that are supported by GroupDocs.Conversion for Java library.
Also it's possible to get allowed conversions for specific file format.

### Fonts replacement

It is a common use case when a source document references to some specific fonts that are not present in the environment where you launch your application. GroupDocs.Conversion for Java provides a solution - you can substitute missing fonts with fonts of your choice that will preserve your document appearance.

### Watermarking converted document

You can add a text or an image watermarks to any page of converted document and choose its desired size, color and font size.

## Caching results

GroupDocs.Conversion supports conversion result caching to local disk by default. However any type of cache storage can be supported by implementing appropriate interfaces – Amazon S3, Dropbox, Google Drive, Windows Azure, Reddis or any other.

## Document information extraction

GroupDocs.Conversion allows to obtain basic information about source document - file type, pages count etc. Dependent on source file type some format specific information can be extracted, for example:

- CAD - list of layers and layouts in a CAD document;
- Email – list of folders contained in an Outlook data file document;
- PDF – information about document printing restrictions;
- Project Management – project start and end dates.
