---
id: logging
url: conversion/java/logging
title: Logging
weight: 6
description: "Logging when converting documents with GroupDocs.Conversion for Java"
keywords: Log conversion process, Logging
productName: GroupDocs.Conversion for Java
hideChildren: true
toc: True
---
To enable logging, use the `ConsoleLogger` class or implement a custom logger via the `ILogger` interface.

* The [ILogger](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.logging/ilogger/) interface declares the methods used to perform logging.
* The [ConsoleLogger](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.logging/consolelogger/) class implements the methods that output log messages to a standard console.

The log contains the following types of messages:

* Error - for unrecoverable exceptions
* Warning - for recoverable/expected exceptions
* Trace - for general information

## Logging to the console
To log to a standard console, use the [ConsoleLogger](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.logging/consolelogger/) class implementation:

```java

String documentPath = "sample.docx"; // NOTE: Put here actual path to your document
String outputPath = "converted.pdf";

// Create console logger
ConsoleLogger logger = new ConsoleLogger();

// Create ConverterSettings and specify logger.
ConverterSettings settingsFactory = new ConverterSettings();
settingsFactory.setLogger(logger);

Converter converter = new Converter(documentPath, settingsFactory);

PdfConvertOptions options = new PdfConvertOptions();
converter.convert(outputPath, options);

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

To log to a file, a stream or any other custom location, implement the [ILogger](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.logging/ilogger/) interface:

* For trace messages, implement the `public void Trace(string message)` method.
* For warning messages, implement the `public void Warning(string message)` method.
* For error messages, implement the `public void Error(string message)` method.

The following code snippet shows how to implement a simple file logger:

```java

String documentPath = "sample.docx"; // NOTE: Put here actual path to your document
String outputPath = "converted.pdf";

// Create logger and specify the output file
ILogger logger = new CustomFileLogger("log.txt");

// Create ConverterSettings and specify logger.
ConverterSettings settingsFactory = new ConverterSettings();
settingsFactory.setLogger(logger);

Converter converter = new Converter(documentPath, settingsFactory);

PdfConvertOptions options = new PdfConvertOptions();
converter.convert(outputPath, options);


public class CustomFileLogger : ILogger
{
	private String _fileName;

	/**
	 * Create logger to file.
	 * @param fileName Full file name with path
	 */
	public CustomFileLogger(String fileName)
	{
		_fileName = fileName;
	}

	/**
	 * Writes trace message to file.
	 * Trace log messages provide generally useful information about application flow.
	 * @param message The trace message.
	 */
	public void trace(String message)
	{
		String contentToAppend = "[TRACE] " + message + System.lineSeparator();
		writer(contentToAppend);
	}

	/**
	 * Writes warning message to file.
	 * Warning log messages provide information about the unexpected and recoverable event in application flow.
	 * @param message The warning message.
	 */
	public void warning(String message)
	{
		String contentToAppend = "[WARN] " + message + System.lineSeparator();
		writer(contentToAppend);
	}

	/**
	 * Writes an error message to file.
	 * Error log messages provide information about unrecoverable events in application flow.
	 * @param message The error message.
	 * @param exception The exception.
	 */
	public void error(String message, com.groupdocs.conversion.internal.c.a.ms.System.Exception exception)
	{
		String contentToAppend = "[ERROR] " + message + ", exception: " + exception+System.lineSeparator();
		writer(contentToAppend);
	}

	public void writer(String message)
	{
		FileWriter fw = null; //the true will append the new data
		try {
			fw = new FileWriter(_fileName,true);
			fw.write(message);//appends the string to the file
			fw.close();
		} catch (IOException e) {
			throw new RuntimeException(e);
		}
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