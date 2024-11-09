---
id: converting-documents
url: conversion/python-net/developer-guide/converting-documents
title: Converting Documents
weight: 3
description: "Learn how to convert PDF, Word, Excel, and PowerPoint documents with GroupDocs.Conversion for Python via .NET API."
keywords: Convert documents, Document conversion, PDF conversion, Word conversion, Excel conversion, PowerPoint conversion
productName: GroupDocs.Conversion for Python via .NET
hideChildren: True
---

Converting a document to another format is a core feature of *GroupDocs.Conversion for Python via .NET*, enabling seamless transformations between various document types. This documentation section focuses on common use cases for GroupDocs.Conversion and demonstrates how to apply the API effectively.

## Converter Class Methods

The `Converter` class offers two methods for converting documents to another format:

- **`convert(file_path, convert_options)`**: Converts a document to a specified output format and saves it to a file. For example, this can convert a DOCX file to PDF.
- **`convert(file_stream, convert_options)`**: Converts the document and writes it to a provided stream instead of saving it to a file path.

Three methods are available for converting documents into multiple-page files:

- **`convert_by_page(folder_path, convert_options)`**: Converts the document into individual pages, saving each page as a separate file in the specified directory.
- **`convert_by_page(page_path, page_number, convert_options)`**: Converts specific document pages and saves each page to a specified file path.
- **`convert_by_page(page_stream, page_number, convert_options)`**: Converts specific document pages and saves them to a specified stream.

Additionally, there is one method for converting files that contain other files:

- **`convert_multiple(folder_path, convert_options)`**: Converts files within a document container, such as compressed files, and writes the converted files to the specified directory.

## Convert Options

Each conversion method accepts a `ConvertOptions` class, which contains configuration parameters specific to the output format. These options allow you to control the conversion process and customize the results.

Below is a list of available `ConvertOptions` classes and their corresponding output types:

- **PdfConvertOptions** – Options for converting to [PDF]({{< ref "conversion/python-net/supported-file-formats#pdf" >}}) format.
- **WordProcessingConvertOptions** – Options for converting to [Word Processing]({{< ref "conversion/python-net/supported-file-formats#word-processing" >}}) formats.
- **SpreadsheetConvertOptions** – Options for converting to [Spreadsheet]({{< ref "conversion/python-net/supported-file-formats#spreadsheet" >}}) formats.
- **PresentationConvertOptions** – Options for converting to [Presentation]({{< ref "conversion/python-net/supported-file-formats#presentation" >}}) formats.
- **ImageConvertOptions** – Options for converting to [Image]({{< ref "conversion/python-net/supported-file-formats#image" >}}) formats (e.g., PNG, JPEG).
- **WebConvertOptions** – Options for converting to [Web]({{< ref "conversion/python-net/supported-file-formats#web" >}}) formats (e.g., HTML).
- **PageDescriptionLanguageConvertOptions** – Options for converting to [Page Description Language]({{< ref "conversion/python-net/supported-file-formats#page-description-language" >}}) formats (e.g., PostScript).
- **EBookConvertOptions** – Options for converting to [EBook]({{< ref "conversion/python-net/supported-file-formats#ebook" >}}) formats (e.g., EPUB, MOBI).
- **EmailConvertOptions** – Options for converting to [Email]({{< ref "conversion/python-net/supported-file-formats#email-and-outlook" >}}) formats (e.g., EML, MSG).
- **DiagramConvertOptions** – Options for converting to [Diagram]({{< ref "conversion/python-net/supported-file-formats#diagram" >}}) formats (e.g., VSDX).
- **CadConvertOptions** – Options for converting to [CAD]({{< ref "conversion/python-net/supported-file-formats#cad" >}}) formats (e.g., DWG).
- **ThreeDConvertOptions** – Options for converting to [3D]({{< ref "conversion/python-net/supported-file-formats#3d" >}}) formats.
- **ProjectManagementConvertOptions** – Options for converting to [Project Management]({{< ref "conversion/python-net/supported-file-formats#project-management" >}}) formats (e.g., MPP).
- **GisConvertOptions** – Options for converting to [GIS]({{< ref "conversion/python-net/supported-file-formats#gis" >}}) formats.
- **FontConvertOptions** – Options for converting to [Font]({{< ref "conversion/python-net/supported-file-formats#font" >}}) formats (e.g., TTF, OTF).
- **FinanceConvertOptions** – Options for converting to [Finance]({{< ref "conversion/python-net/supported-file-formats#finance" >}}) formats (e.g., XBRL).
- **CompressionConvertOptions** – Options for converting to [Compression]({{< ref "conversion/python-net/supported-file-formats#compression" >}}) formats (e.g., ZIP).
- **NoConvertOptions** – A special option class that instructs the converter to copy the source document without any modifications.

Specify the appropriate `ConvertOptions` class as an argument in the `convert` method to meet your desired output requirements. Selecting the correct `ConvertOptions` class based on the target format ensures optimal conversion results.
