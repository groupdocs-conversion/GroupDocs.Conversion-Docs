---
id: converting-documents
url: conversion/python-net/developer-guide/converting-documents
title: Converting Documents
linkTitle: Converting Documents
weight: 3
description: "Convert single documents, specific pages or page ranges, per-page output files, and files packed inside archives — with options for output format, watermarks, and metadata extraction — using GroupDocs.Conversion for Python via .NET."
keywords: convert document, convert to PDF, convert to DOCX, convert to XLSX, convert to PPTX, convert to HTML, convert to image, page selection, page range, watermark, archive, container, possible conversions, python, GroupDocs.Conversion
productName: GroupDocs.Conversion for Python via .NET
hideChildren: True
toc: True
---

Converting a document to another format is a core feature of *GroupDocs.Conversion for Python via .NET*, enabling seamless transformations between various document types. This documentation section focuses on common use cases for GroupDocs.Conversion and demonstrates how to apply the API effectively.

## Converter Class Methods

The `Converter` class exposes a single conversion entry point plus several helpers for inspecting the loaded document:

- **`convert(file_path, convert_options)`** — converts the loaded document to the target format specified by `convert_options` and saves the result to `file_path`. The same method handles single-document conversion, container / archive conversion (ZIP, RAR, 7Z, OST, PST), and per-page output when combined with `options.page_number` / `options.pages_count`. See [Convert a Document to Another Format]({{< ref "conversion/python-net/developer-guide/converting-documents/convert-document-to-another-format.md" >}}), [Convert a Document to Multiple Page Files]({{< ref "conversion/python-net/developer-guide/converting-documents/convert-document-to-multiple-page-files.md" >}}), and [Convert Files Within Document Containers]({{< ref "conversion/python-net/developer-guide/converting-documents/convert-files-within-document-containers.md" >}}).
- **`get_document_info()`** — returns a `DocumentInfo` object with format, page count, author, dimensions, and format-specific metadata without performing a conversion. See [Getting Document Information]({{< ref "conversion/python-net/developer-guide/getting-document-info.md" >}}).
- **`get_possible_conversions()`**, **`Converter.get_possible_conversions_by_extension(extension)`**, and **`Converter.get_all_possible_conversions()`** — discover the set of target formats a given source supports before running a pipeline. See [Get Possible Conversions]({{< ref "conversion/python-net/developer-guide/converting-documents/get-possible-conversions.md" >}}).
- **`is_document_password_protected()`** — quick check before attempting to open a file that may be encrypted.

{{< alert style="info" >}}
Per-page output is driven by the `page_number` + `pages_count` attributes on the `ConvertOptions` class, not by a dedicated method. Loop over pages and call `convert(file_path, options)` once per page to produce one output file per page.
{{< /alert >}}

## Convert Options

Each conversion method accepts a `ConvertOptions` class, which contains configuration parameters specific to the output format. These options allow you to control the conversion process and customize the results.

Below is a list of available `ConvertOptions` classes and their corresponding output types:

- **PdfConvertOptions** – Options for converting to [PDF]({{< ref "conversion/python-net/getting-started/supported-document-formats.md#pdf" >}}) format.
- **WordProcessingConvertOptions** – Options for converting to [Word Processing]({{< ref "conversion/python-net/getting-started/supported-document-formats.md#word-processing" >}}) formats.
- **SpreadsheetConvertOptions** – Options for converting to [Spreadsheet]({{< ref "conversion/python-net/getting-started/supported-document-formats.md#spreadsheet" >}}) formats.
- **PresentationConvertOptions** – Options for converting to [Presentation]({{< ref "conversion/python-net/getting-started/supported-document-formats.md#presentation" >}}) formats.
- **ImageConvertOptions** – Options for converting to [Image]({{< ref "conversion/python-net/getting-started/supported-document-formats.md#image" >}}) formats (e.g., PNG, JPEG).
- **WebConvertOptions** – Options for converting to [Web]({{< ref "conversion/python-net/getting-started/supported-document-formats.md#web" >}}) formats (e.g., HTML).
- **PageDescriptionLanguageConvertOptions** – Options for converting to [Page Description Language]({{< ref "conversion/python-net/getting-started/supported-document-formats.md#page-description-language" >}}) formats (e.g., PostScript).
- **EBookConvertOptions** – Options for converting to [EBook]({{< ref "conversion/python-net/getting-started/supported-document-formats.md#ebook" >}}) formats (e.g., EPUB, MOBI).
- **EmailConvertOptions** – Options for converting to [Email]({{< ref "conversion/python-net/getting-started/supported-document-formats.md#email-and-outlook" >}}) formats (e.g., EML, MSG).
- **DiagramConvertOptions** – Options for converting to [Diagram]({{< ref "conversion/python-net/getting-started/supported-document-formats.md#diagram" >}}) formats (e.g., VSDX).
- **CadConvertOptions** – Options for converting to [CAD]({{< ref "conversion/python-net/getting-started/supported-document-formats.md#cad" >}}) formats (e.g., DWG).
- **ThreeDConvertOptions** – Options for converting to [3D]({{< ref "conversion/python-net/getting-started/supported-document-formats.md#3d" >}}) formats.
- **ProjectManagementConvertOptions** – Options for converting to [Project Management]({{< ref "conversion/python-net/getting-started/supported-document-formats.md#project-management" >}}) formats (e.g., MPP).
- **GisConvertOptions** – Options for converting to [GIS]({{< ref "conversion/python-net/getting-started/supported-document-formats.md#gis" >}}) formats.
- **FontConvertOptions** – Options for converting to [Font]({{< ref "conversion/python-net/getting-started/supported-document-formats.md#font" >}}) formats (e.g., TTF, OTF).
- **FinanceConvertOptions** – Options for converting to [Finance]({{< ref "conversion/python-net/getting-started/supported-document-formats.md#finance" >}}) formats (e.g., XBRL).
- **CompressionConvertOptions** – Options for converting to [Compression]({{< ref "conversion/python-net/getting-started/supported-document-formats.md#compression" >}}) formats (e.g., ZIP).
- **NoConvertOptions** – A special option class that instructs the converter to copy the source document without any modifications.

Specify the appropriate `ConvertOptions` class as an argument in the `convert` method to meet your desired output requirements. Selecting the correct `ConvertOptions` class based on the target format ensures optimal conversion results.
