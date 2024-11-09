---
id: loading-documents
url: conversion/python-net/developer-guide/loading-documents
title: Loading Documents
weight: 1
description: "Following this guide, you will learn how to load PDF, Word, Excel, and PowerPoint documents by local file path and stream with GroupDocs.Conversion for Python via .NET API."
keywords: Get default load options, Load document from local path, Load document from stream, Load password-protected documents
productName: GroupDocs.Conversion for Python via .NET
hideChildren: true
---

*GroupDocs.Conversion for Python via .NET* provides two primary ways to load a document: by file path or from a stream. This flexibility allows you to load documents from various storage sources. The `Converter` class provides specific constructors to handle each of these loading methods.

## Converter Class Constructors

The following constructors can be used to load files from a **file path**:

- **`Converter(file_path)`**: Initializes a converter with the specified file path.
- **`Converter(file_path, load_options)`**: Initializes a converter with file path and load options.
- **`Converter(file_path, converter_settings)`**: Initializes a converter with file path and converter settings.
- **`Converter(file_path, load_options, converter_settings)`**: Initializes a converter with file path, load options, and converter settings.

To load files from a **stream**, use one of the following constructors:

- **`Converter(file_stream)`**: Initializes a converter with the specified file stream.
- **`Converter(file_stream, load_options)`**: Initializes a converter with file stream and load options.
- **`Converter(file_stream, converter_settings)`**: Initializes a converter with file stream and converter settings.
- **`Converter(file_stream, load_options, converter_settings)`**: Initializes a converter with file stream, load options, and converter settings.

## Load Options

The `LoadOptions` classes specify the type of document to be loaded and include optional parameters, such as `password`. Below, we have categorized the available `LoadOptions` into two groups: options for a **format-family** and options for a **specific file type**.

### Load Options for Format-Family

- `CadLoadOptions`: Options for loading CAD documents (e.g., DWG, DWF).
- `CompressionLoadOptions`: Options for loading compressed files (e.g., ZIP, RAR).
- `DatabaseLoadOptions`: Options for loading database files (e.g., NSF, LOG, SQL).
- `DiagramLoadOptions`: Options for loading diagram files (e.g., VSD, VSDX).
- `EBookLoadOptions`: Options for loading eBook files (e.g., EPUB, MOBI).
- `EmailLoadOptions`: Options for loading email files (e.g., EML, MSG).
- `FinanceLoadOptions`: Options for loading finance documents (e.g., XBRL, OFX).
- `FontLoadOptions`: Options for loading font files (e.g., TTF, EOT).
- `GisLoadOptions`: Options for loading GIS documents (e.g., SHP, GDB).
- `PageDescriptionLanguageLoadOptions`: Options for loading page description files (e.g., SVG, EPS).
- `PersonalStorageLoadOptions`: Options for loading personal storage files (e.g., OST, PST).
- `PresentationLoadOptions`: Options for loading presentation files (e.g., PPT, PPTX).
- `SpreadsheetLoadOptions`: Options for loading spreadsheet files (e.g., XLS, XLSX).
- `ThreeDLoadOptions`: Options for loading 3D files (e.g., FBX, THREEDS).
- `WebLoadOptions`: Options for loading web documents (e.g., XML, JSON).
- `WordProcessingLoadOptions`: Options for loading word processing files (e.g., DOC, DOCX).

### Load Options for Specific File Types

- `EpubLoadOptions`: Options specifically for loading EPUB files.
- `MboxLoadOptions`: Options specifically for loading MBOX files.
- `NoteLoadOptions`: Options specifically for loading ONE files.
- `NsfLoadOptions`: Options specifically for loading NSF files.
- `OlmLoadOptions`: Options specifically for loading OLM files.
- `PdfLoadOptions`: Options specifically for loading PDF documents.
- `PublisherLoadOptions`: Options specifically for loading PUB files.
- `TxtLoadOptions`: Options specifically for loading TXT files.
- `VcfLoadOptions`: Options specifically for loading VCF files.

## Converter Settings

The `ConverterSettings` class provides several settings to control document loading behavior:

- `cache`: Specifies caching options with `MemoryCache` or `FileCache`.
- `logger`: Specifies logging options with `ConsoleLogger` or `FileLogger`.
- `font_directories`: An array of directory paths with custom fonts.
- `temp_folder`: Specifies a folder for temporary files during conversion. Defaults to a user-specific temporary folder.
