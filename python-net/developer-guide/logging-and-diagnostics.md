---
id: logging-and-diagnostics
url: conversion/python-net/developer-guide/logging-and-diagnostics
title: Logging and Diagnostics
weight: 5
description: "Capture trace, warning, and error messages from document conversion using the built-in ConsoleLogger and GroupDocs.Conversion for Python via .NET."
keywords: log conversion process, logging, diagnostics, ConsoleLogger, trace, warning, error, document conversion, python
productName: GroupDocs.Conversion for Python via .NET
hideChildren: true
toc: true
---

To enable logging, wire the built-in `ConsoleLogger` class through `ConverterSettings` when constructing the `Converter`. The logger emits three types of messages:

- **Error**: for critical exceptions that prevent execution.
- **Warning**: for recoverable or expected issues.
- **Trace**: for general informational messages.

## Example 1: Write Logs to Console

To stream log messages to standard output, instantiate `ConsoleLogger`, assign it to `ConverterSettings.logger`, and pass the settings to the `Converter` constructor:

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
{{< tab "business-plan.docx" >}}  
{{< tab-text >}}
`business-plan.docx` is the sample file used in this example. Click [here](/conversion/python-net/_sample_files/developer-guide/logging-and-diagnostics/business-plan.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "business-plan.pdf" >}}  
```text
Binary file (PDF, 283 KB)
```
[Download full output](/conversion/python-net/_output_files/developer-guide/logging-and-diagnostics/write_logs_to_console/business-plan.pdf)
{{< /tab >}}
{{< /tabs >}}

### Explanation

1. `console_logger` is created to facilitate logging. This logger sends log messages to the console.
2. `converter_settings` is instantiated, with its `logger` attribute set to the previously created `console_logger`.
3. A `Converter` object is instantiated with the configured `converter_settings`.
4. The `convert` method is called and the conversion occurs, log messages are generated and displayed in the console.

## Example 2: Redirect Logs to a File

The Python binding ships a single `ConsoleLogger` that writes to standard output. To persist the log stream to a text file, redirect `sys.stdout` for the duration of the conversion — the logger will then write its messages into the file handle:

{{< tabs "code-example-2">}}
{{< tab "write_logs_to_file.py" >}}  
```python
import sys
from groupdocs.conversion import Converter, ConverterSettings
from groupdocs.conversion.logging import ConsoleLogger
from groupdocs.conversion.options.convert import PdfConvertOptions

def write_logs_to_file():
    log_file_path = "./log.txt"

    # Redirect standard output to a file so ConsoleLogger writes into it
    original_stdout = sys.stdout
    with open(log_file_path, "w", encoding="utf-8") as log_file:
        sys.stdout = log_file
        try:
            # Create converter settings and attach the console logger
            converter_settings = ConverterSettings()
            converter_settings.logger = ConsoleLogger()

            # Load DOCX document and convert it to PDF
            with Converter("./business-plan.docx", converter_settings) as converter:
                pdf_convert_options = PdfConvertOptions()
                converter.convert("./business-plan.pdf", pdf_convert_options)
        finally:
            sys.stdout = original_stdout

if __name__ == "__main__":
    write_logs_to_file()
```
{{< /tab >}}
{{< tab "log.txt" >}}  
```
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
```text
Binary file (PDF, 283 KB)
```
[Download full output](/conversion/python-net/_output_files/developer-guide/logging-and-diagnostics/write_logs_to_file/business-plan.pdf)
{{< /tab >}}
{{< /tabs >}}

### Explanation

1. `sys.stdout` is redirected to a `log.txt` file so any `print`-style writes (including the ones emitted by `ConsoleLogger`) land in the file.
2. `ConverterSettings` is instantiated with `logger` set to a fresh `ConsoleLogger` instance.
3. A `Converter` object is created with the configured settings and performs the conversion — trace messages are captured in the file instead of the terminal.
4. `sys.stdout` is restored in the `finally` block so subsequent `print` calls continue to go to the terminal.