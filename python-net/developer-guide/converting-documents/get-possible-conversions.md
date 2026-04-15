---
id: get-possible-conversions
url: conversion/python-net/developer-guide/converting-documents/get-possible-conversions
title: Get Possible Conversions
linkTitle: Get Possible Conversions
weight: 1
description: "Query GroupDocs.Conversion for Python via .NET for the set of target formats a given source supports — library-wide, by extension, or for the document currently loaded — via get_all_possible_conversions, get_possible_conversions_by_extension, and get_possible_conversions."
keywords: possible conversions, get_all_possible_conversions, get_possible_conversions_by_extension, get_possible_conversions, primary conversion, secondary conversion, target format, conversion discovery, GroupDocs.Conversion, python
productName: GroupDocs.Conversion for Python via .NET
hideChildren: False
toc: True
---

GroupDocs.Conversion offers several methods to retrieve possible conversions:

- **`Converter.get_all_possible_conversions()`**: Retrieves all available primary and secondary conversions for every supported file type.
- **`Converter.get_possible_conversions_by_extension(extension: str)`**: Retrieves possible conversions for a specific file extension, e.g., `"docx"`.
- **`converter.get_possible_conversions()`**: Retrieves possible conversions for the currently loaded file.

### Types of Conversions
* **Primary Conversion**: A direct conversion from one format to another, providing higher quality and better performance.
* **Secondary Conversion**: An indirect conversion that requires the source file to be first converted to an intermediate format before reaching the final format.

## Example 1: Get All Possible Conversions

The following example demonstrates how to retrieve and display all primary and secondary conversions for every supported file type.

{{< tabs "example-1">}}
{{< tab "get_all_possible_conversions.py" >}}  
```python
from groupdocs.conversion import Converter

def get_all_possible_conversions():
    # Get all possible conversions
    all_possible_conversions = Converter.get_all_possible_conversions()

    for possible_conversion in all_possible_conversions:
        # Filter primary conversions (use .extension for a clean string)
        primary_conversions = [conversion.format.extension for conversion in possible_conversion.all if conversion.is_primary]
        # Filter secondary conversions
        secondary_conversions = [conversion.format.extension for conversion in possible_conversion.all if not conversion.is_primary]

        # Print out the source format and its conversions
        print(f" **Source format** : {possible_conversion.source.description}")
        print(f"  - **Primary conversions**: {primary_conversions}")
        print(f"  - **Secondary conversions**: {secondary_conversions}")
        print()

if __name__ == "__main__":
    get_all_possible_conversions()
```
{{< /tab >}}
{{< tab "get-all-possible-conversions.txt" >}}  
```text
**Source format** : MP3 Audio File (mp3)
  - **Primary conversions**: ['mp3', 'aac', 'aiff', 'flac', 'm4a', 'wma', 'ac3', 'ogg', 'wav']
  - **Secondary conversions**: []

 **Source format** : Advanced Audio Coding File (aac)
  - **Primary conversions**: ['mp3', 'aac', 'aiff', 'flac', 'm4a', 'wma', 'ac3', 'ogg', 'wav']
  - **Secondary conversions**: []

 **Source format** : Audio Interchange File Format (aiff)
  - **Primary conversions**: ['mp3', 'aac', 'aiff', 'flac', 'm4a', 'wma', 'ac3', 'ogg',
[TRUNCATED]
```
[Download full output](/conversion/python-net/_output_files/developer-guide/converting-documents/get-possible-conversions/get_all_possible_conversions/get-all-possible-conversions.txt)
{{< /tab >}}
{{< /tabs >}}

## Example 2: Get Possible Conversions by File Extension

The following example demonstrates how to retrieve and display possible conversions for the "docx" extension, which corresponds to a Microsoft Word Open XML Document.

{{< tabs "example-2">}}
{{< tab "get_all_possible_conversions_by_file_extension.py" >}}  
```python
from groupdocs.conversion import Converter

def get_all_possible_conversions_by_file_extension():
    # Get all possible conversions for a specific extension
    possible_conversion = Converter.get_possible_conversions_by_extension("docx")

    # Filter primary conversions (use .extension for a clean string)
    primary_conversions = [conversion.format.extension for conversion in possible_conversion.all if conversion.is_primary]
    # Filter secondary conversions
    secondary_conversions = [conversion.format.extension for conversion in possible_conversion.all if not conversion.is_primary]

    # Print out the source format and its conversions
    print(f" **Source format**: {possible_conversion.source.description}")
    print(f"  - **Primary conversions**: {primary_conversions}")
    print(f"  - **Secondary conversions**: {secondary_conversions}")
    print()

if __name__ == "__main__":
    get_all_possible_conversions_by_file_extension()
```
{{< /tab >}}
{{< tab "get-all-possible-conversions-by-file-extension.txt" >}}  
```text
**Source format**: Microsoft Word Open XML Document (docx)
  - **Primary conversions**: ['epub', 'mobi', 'azw3', 'tiff', 'tif', 'jpg', 'jpeg', 'png', 'gif', 'bmp', 'ico', 'psd', 'wmf', 'emf', 'dcm', 'dicom', 'webp', 'jp2', 'j2k', 'emz', 'wmz', 'tga', 'psb', 'jfif', 'eps', 'xps', 'tex', 'ps', 'pcl', 'svg', 'svgz', 'pdf', 'ppt', 'pps', 'pptx', 'ppsx', 'odp', 'otp', 'potx', 'pot', 'potm', 'pptm', 'ppsm', 'fodp', 'htm', 'html', 'mhtml', 'mht', 'doc', 'docm', 'docx', 'dot', 'dotm', 'dotx', 'rtf', 'od
[TRUNCATED]
```
[Download full output](/conversion/python-net/_output_files/developer-guide/converting-documents/get-possible-conversions/get_all_possible_conversions_by_file_extension/get-all-possible-conversions-by-file-extension.txt)
{{< /tab >}}
{{< /tabs >}}

## Example 3: Get Possible Conversions for Current File

The following example demonstrates how to retrieve and display possible conversions for a file passed to the `Converter` class constructor.

{{< tabs "example-3">}}
{{< tab "get_all_possible_conversions_for_current_file.py" >}}  
```python
from groupdocs.conversion import Converter

def get_all_possible_conversions_for_current_file():
    with Converter("./cost-analysis.xlsx") as converter:
        # Get possible conversions for the loaded document
        possible_conversion = converter.get_possible_conversions()

        # Filter primary conversions (use .extension for a clean string)
        primary_conversions = [conversion.format.extension for conversion in possible_conversion.all if conversion.is_primary]
        # Filter secondary conversions
        secondary_conversions = [conversion.format.extension for conversion in possible_conversion.all if not conversion.is_primary]

        # Print out the source format and its conversions
        print(f" **Source format**: {possible_conversion.source.description}")
        print(f"  - **Primary conversions**: {primary_conversions}")
        print(f"  - **Secondary conversions**: {secondary_conversions}")
        print()

if __name__ == "__main__":
    get_all_possible_conversions_for_current_file()
```
{{< /tab >}}
{{< tab "get-all-possible-conversions-current-file.txt" >}}  
```text
**Source format**: Microsoft Excel Open XML Spreadsheet (xlsx)
  - **Primary conversions**: ['epub', 'mobi', 'azw3', 'eps', 'xps', 'tex', 'ps', 'pcl', 'pdf', 'xls', 'xlsx', 'xlsm', 'xlsb', 'ods', 'xltx', 'xlt', 'xltm', 'tsv', 'xlam', 'csv', 'fods', 'dif', 'sxc', 'fopcs', 'htm', 'html', 'mhtml', 'mht', 'json', 'xml']
  - **Secondary conversions**: ['tiff', 'tif', 'jpg', 'jpeg', 'png', 'gif', 'bmp', 'ico', 'psd', 'wmf', 'emf', 'dcm', 'dicom', 'webp', 'jp2', 'j2k', 'emz', 'wmz', 'tga', 'psb', 'jfif
[TRUNCATED]
```
[Download full output](/conversion/python-net/_output_files/developer-guide/converting-documents/get-possible-conversions/get_all_possible_conversions_for_current_file/get-all-possible-conversions-current-file.txt)
{{< /tab >}}
{{< /tabs >}}
