---
id: get-default-load-options
url: conversion/python-net/developer-guide/loading-documents/get-default-load-options
linkTitle: Get Default Load Options
title: Get Default Load Options
weight: 1
description: "Learn how to retrieve default load options for a source format using GroupDocs.Conversion for Python via .NET."
keywords: Default load options, Load options, GroupDocs.Conversion for Python
productName: GroupDocs.Conversion for Python via .NET
hideChildren: False
---

*GroupDocs.Conversion for Python via .NET* enables you to retrieve default load options for specific document formats, useful for setting format-specific defaults at runtime.

To obtain default load options for a document format, use the `get_possible_conversions_by_extension` method, passing the source document’s file extension (e.g., `"docx"` for Word documents). This example demonstrates how to retrieve the default load options.

```python
from groupdocs.conversion import Converter
from groupdocs.conversion.options.load import WordProcessingLoadOptions

def get_default_load_options():
    # Step 1: Retrieve possible conversions for a DOCX extension
    possible_conversions = Converter.get_possible_conversions_by_extension("docx")

    # Step 2: Use the default load options 
    default_load_options = possible_conversions.load_options

    # You can also instantiate load options by yourself
    word_processing_load_options = WordProcessingLoadOptions()

if __name__ == "__main__":
    get_default_load_options()
```

### Explanation

- **Retrieve Default Load Options**: The `get_possible_conversions_by_extension` method returns possible conversions along with default load options for a specified format.
- **Using Default Load Options**: The `default_load_options` object holds settings that can be used directly for initializing conversions.
- **Manual Load Options Initialization**: Alternatively, you can create specific load options (e.g., `WordProcessingLoadOptions`) manually if customization is required.

By retrieving and using these default settings, you can streamline conversions while preserving format-specific options.

For further details, consult the [API Reference](https://reference.groupdocs.com/conversion/python-net/).
