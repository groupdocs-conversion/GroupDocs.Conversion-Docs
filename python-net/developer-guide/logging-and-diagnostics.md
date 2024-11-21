---
id: logging-and-diagnostics
url: conversion/python-net/developer-guide/logging-and-diagnostics
title: Logging and Diagnostics
weight: 5
description: "Enable and configure logging for document conversions with GroupDocs.Conversion for Python via .NET."
keywords: log conversion process, logging, diagnostics, document conversion
productName: GroupDocs.Conversion for Python via .NET
hideChildren: true
toc: true
---

To enable logging, use either the `ConsoleLogger` or `FileLogger` class. There are three types of log messages:

- **Error**: for critical exceptions that prevent execution.
- **Warning**: for recoverable or expected issues.
- **Trace**: for general informational messages.

## Example 1: Write Logs to Console

To enable logging to sconsole, use the `ConsoleLogger` class as shown below:

{{< tabs "code-example-1">}}
{{< tab "write_logs_to_console.py" >}}  
```python
from groupdocs.conversion import Converter, ConverterSettings
from groupdocs.conversion.logging import ConsoleLogger
from groupdocs.conversion.options.convert import PdfConvertOptions

def write_logs_to_console():
    # Create a console logger
    console_logger = ConsoleLogger()

    # Create converter settings and pass logger 
    converter_settings = ConverterSettings()
    converter_settings.logger = console_logger

    # Load DOCX document and convert it to PDF
    with Converter("./business-plan.docx", converter_settings) as converter:
        pdf_convert_options = PdfConvertOptions()
        converter.convert("./business-plan.pdf", pdf_convert_options)    

if __name__ == "__main__":
    write_logs_to_console()
```
{{< /tab >}}
{{< tab "Expected Output" >}}  
```yaml
[TRACE] Attempting to read the 'GROUPDOCS_LIC_PATH' environment variable for license file location.
[TRACE] GroupDocs license has been set successfully.
[TRACE] Determine loader for source document business-plan.docx ...
[TRACE] ... loader selected.
[TRACE] Loading source document business-plan.docx ...
[TRACE] ... document loaded.
[TRACE] Main document will be converted.
[TRACE] Starting conversion of business-plan.docx...
[TRACE]  ... converter selected ... 
[TRACE]  ... conversion completed.
```
{{< /tab >}}
{{< tab "business-plan.docx" >}}  
{{< tab-text >}}
`business-plan.docx` is the sample file used in this example. Click [here](/conversion/python-net/_sample_files/developer-guide/logging-and-diagnostics/business-plan.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "business-plan.pdf" >}}  
{{< tab-text >}}
`business-plan.pdf` is converted file. Click [here](/conversion/python-net/_sample_files/developer-guide/logging-and-diagnostics/business-plan.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

### Explanation

1. `console_logger` is created to facilitate logging. This logger sends log messages to the console.
2. `converter_settings` is instantiated, with its `logger` attribute set to the previously created `console_logger`.
3. A `Converter` object is instantiated with the configured `converter_settings`.
4. The `convert` method is called and the conversion occurs, log messages are generated and displayed in the console.

## Example 2: Write Logs to File

The following code demonstrates how to use `FileLogger` class and write logs to a text file:

{{< tabs "code-example-2">}}
{{< tab "write_logs_to_console.py" >}}  
```python
from groupdocs.conversion import Converter, ConverterSettings
from groupdocs.conversion.logging import FileLogger
from groupdocs.conversion.options.convert import PdfConvertOptions

def write_logs_to_file():
    # Set log file path and create logger
    log_file_path = "./log.txt"
    file_logger = FileLogger(log_file_path)

    # Create converter settings and pass logger 
    converter_settings = ConverterSettings()
    converter_settings.logger = file_logger

    # Load DOCX document and convert it to PDF
    with Converter("./business-plan.docx", converter_settings) as converter:
        pdf_convert_options = PdfConvertOptions()
        converter.convert("./business-plan.pdf", pdf_convert_options)    

if __name__ == "__main__":
    write_logs_to_file()
```
{{< /tab >}}
{{< tab "log.txt" >}}  
```
2024-11-04 12:15:05 [TRACE] Attempting to read the 'GROUPDOCS_LIC_PATH' environment variable for license file location.
2024-11-04 12:15:05 [TRACE] GroupDocs license has been set successfully.
2024-11-04 12:15:05 [TRACE] Determine loader for source document business-plan.docx ...
2024-11-04 12:15:05 [TRACE] ... loader selected.
2024-11-04 12:15:05 [TRACE] Loading source document business-plan.docx ...
2024-11-04 12:15:06 [TRACE] ... document loaded.
2024-11-04 12:15:06 [TRACE] Main document will be converted.
2024-11-04 12:15:06 [TRACE] Starting conversion of business-plan.docx...
2024-11-04 12:15:06 [TRACE]  ... converter selected ... 
2024-11-04 12:15:09 [TRACE]  ... conversion completed.
```
{{< /tab >}}
{{< tab "business-plan.docx" >}}  
{{< tab-text >}}
`business-plan.docx` is the sample file used in this example. Click [here](/conversion/python-net/_sample_files/developer-guide/logging-and-diagnostics/business-plan.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "business-plan.pdf" >}}  
{{< tab-text >}}
`business-plan.pdf` is converted file. Click [here](/conversion/python-net/_sample_files/developer-guide/logging-and-diagnostics/business-plan.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

### Explanation

1. `file_logger` is created to facilitate logging. This logger writes log messages to the `log.txt` file.
2. `converter_settings` is instantiated, with its `logger` attribute set to the previously created `file_logger`.
3. A `Converter` object is instantiated with the configured `converter_settings`.
4. The `convert` method is called and the conversion occurs, log messages are generated and written to the text file.