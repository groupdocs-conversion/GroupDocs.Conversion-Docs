---
id: load-password-protected-file
url: conversion/python-net/developer-guide/loading-documents/load-password-protected-file
title: Load Password-Protected File
weight: 4
description: "Learn how to load and convert password-protected documents using the GroupDocs.Conversion for Python via .NET API, enabling seamless handling of secured files."
keywords: password-protected document, load and convert protected documents, convert document with password, secure document conversion
productName: GroupDocs.Conversion for Python via .NET
hideChildren: False
---

With *GroupDocs.Conversion for Python via .NET* you to load and convert documents that are protected with a password. This feature is useful when you need to handle documents that require authentication to access their contents. 

To load and convert a password-protected document, follow the steps outlined in the code example below:

{{< tabs "code-example">}}
{{< tab "load_password_protected_file.py" >}}  
```python
from groupdocs.conversion import Converter
from groupdocs.conversion.options.convert import PdfConvertOptions
from groupdocs.conversion.options.load import WordProcessingLoadOptions

def load_password_protected_file():
    # Set file path
    file_path = "./password-protected.docx"
    
    # Instantiate load options and set password
    wp_load_options = WordProcessingLoadOptions()
    wp_load_options.password = "12345"

    # Specify source file stream and load options
    converter = Converter(file_path, wp_load_options)
    
    # Specify output file location and convert options
    output_path = "./password-protected.pdf"
    pdf_convert_options = PdfConvertOptions()
    pdf_convert_options.password = "67890"

    # Convert and save to output path
    converter.convert(output_path, pdf_convert_options)

if __name__ == "__main__":
    load_password_protected_file()

```
{{< /tab >}}
{{< tab "password-protected.docx" >}}  
{{< tab-text >}}
`password-protected.docx` is sample file used in this example. Click [here](/conversion/python-net/_sample_files/developer-guide/loading-documents/load-password-protected-file/password-protected.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "password-protected.pdf" >}}  
{{< tab-text >}}
`password-protected.pdf` is converted PDF document. Click [here](/conversion/python-net/_sample_files/developer-guide/loading-documents/load-password-protected-file/password-protected.pdf) to download it. The file is password-protected. Password is `67890`.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

In case the provided password is incorrect, a runtime error will be thrown. The expected error and error message are as follows:

```bash
RuntimeError: Proxy error(CorruptOrDamagedFileException): Cannot convert. The file is corrupt or damaged. The document password is incorrect. ---> IncorrectPasswordException: The document password is incorrect.
```

### Explanation

1. **File Path Setup**: The file path for the password-protected document is specified. In this example, it assumes that the document is named `password-protected.docx`.

2. **Load Options**: An instance of `WordProcessingLoadOptions` is created, and the password required to open the document is set.

3. **Converter Initialization**: A `Converter` instance is created using the file path and the load options that include the password.

4. **Convert Options**: An instance of `PdfConvertOptions` is created for the conversion process. You can also set the output password for the resulting PDF if required.

4. **Conversion Execution**: Finally, the `convert` method is called on the `Converter` instance to convert the password-protected document and save it as a PDF.

### Conclusion

This example demonstrates how to efficiently load and convert password-protected documents using the GroupDocs.Conversion for Python API. Make sure to replace the passwords and file paths with your actual values before executing the code.
