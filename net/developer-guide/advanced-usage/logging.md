---
id: logging
url: conversion/net/logging
title: Logging
weight: 6
description: "Logging when converting documents with GroupDocs.Conversion for .NET"
keywords: Log conversion process, Logging
productName: GroupDocs.Conversion for .NET
hideChildren: true
toc: True
---
To enable logging you can use the `ConsoleLogger` class or implement a custom logger via the `ILogger` interface.

* The [ILogger](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.logging/ilogger/) interface declares the methods used to perform logging.
* The [ConsoleLogger](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.logging/consolelogger/) class implements the methods that output log messages to a standard console.

The log contains the following types of messages:

* Error - for unrecoverable exceptions
* Warning - for recoverable/expected exceptions
* Trace - for general information

## Logging to the console
To log to a standard console, use the [ConsoleLogger](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.logging/consolelogger/) class implementation:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Logging;
using GroupDocs.Conversion.Options.Convert;

string documentPath = @"sample.docx"; // NOTE: Put here actual path to your document
string outputPath = @"converted.pdf";

// Create console logger
ConsoleLogger logger = new ConsoleLogger();

// Create ConverterSettings and specify logger.
Func<ConverterSettings> settingsFactory = () => new ConverterSettings
{
    Logger = logger
};

using (Converter converter = new Converter(documentPath, settingsFactory))
{
    PdfConvertOptions convertOptions = new PdfConvertOptions();
    converter.Convert(outputPath, convertOptions);
}
```

Console output would be as follows:

```console
[TRACE] Determine loaded for source document sample.docx ...
[TRACE] ... loader selected.
[TRACE] Loading source document sample.docx ...
[TRACE] ... document loaded.
[TRACE] Main document will be converted.
[TRACE] Starting conversion of sample.docx...
[TRACE]  ... pipeline selected ...
[TRACE]  ... conversion completed.
```

## Implementing custom logger

To log to a file, a stream or any other custom location, implement the [ILogger](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.logging/ilogger/) interface:

* For trace messages, implement the `public void Trace(string message)` method.
* For warning messages, implement the `public void Warning(string message)` method.
* For error messages, implement the `public void Error(string message)` method.

The following code snippet shows how to implement a simple file logger:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Logging;
using GroupDocs.Conversion.Options.Convert;

string documentPath = @"sample.docx"; // NOTE: Put here actual path to your document
string outputPath = @"converted.pdf";

// Create logger and specify the output file
ILogger logger = new CustomFileLogger("log.txt");

// Create ConverterSettings and specify logger.
Func<ConverterSettings> settingsFactory = () => new ConverterSettings
{
    Logger = logger
};

using (Converter converter = new Converter(documentPath, settingsFactory))
{
    PdfConvertOptions convertOptions = new PdfConvertOptions();
    converter.Convert(outputPath, convertOptions);
}

public class CustomFileLogger : ILogger
{
    private readonly string _fileName;

    /// <summary>
    /// Create logger to file.
    /// </summary>
    /// <param name="fileName">Full file name with path</param>
    public CustomFileLogger(string fileName)
    {
        _fileName = fileName;
    }

    /// <summary>
    /// Writes trace message to file.
    /// Trace log messages provide generally useful information about application flow.
    /// </summary>
    /// <param name="message">The trace message.</param>
    /// <exception cref="System.ArgumentNullException">Thrown when <paramref name="message"/> is null.</exception>
    public void Trace(string message)
    {
        File.AppendAllText(_fileName, $"[TRACE] {message}{Environment.NewLine}");
    }

    /// <summary>
    /// Writes warning message to file.
    /// Warning log messages provide information about the unexpected and recoverable event in application flow.
    /// </summary>
    /// <param name="message">The warning message.</param>
    /// <exception cref="System.ArgumentNullException">Thrown when <paramref name="message"/> is null.</exception>
    public void Warning(string message)
    {
        File.AppendAllText(_fileName, $"[WARN] {message}{Environment.NewLine}");
    }

    /// <summary>
    /// Writes an error message to file.
    /// Error log messages provide information about unrecoverable events in application flow.
    /// </summary>
    /// <param name="message">The error message.</param>
    /// <param name="exception">The exception.</param>
    /// <exception cref="System.ArgumentNullException">Thrown when <paramref name="message"/> is null.</exception>
    /// <exception cref="System.ArgumentNullException">Thrown when <paramref name="exception"/> is null.</exception>
    public void Error(string message, Exception exception)
    {
        File.AppendAllText(_fileName, $"[ERROR] {message}, exception: {exception}{Environment.NewLine}");
    }
}
```

The content of the `log.txt` file would be as follows:

```console
[TRACE] Determine loaded for source document sample.docx ...
[TRACE] ... loader selected.
[TRACE] Loading source document sample.docx ...
[TRACE] ... document loaded.
[TRACE] Main document will be converted.
[TRACE] Starting conversion of sample.docx...
[TRACE]  ... pipeline selected ... 
[TRACE]  ... conversion completed.
```