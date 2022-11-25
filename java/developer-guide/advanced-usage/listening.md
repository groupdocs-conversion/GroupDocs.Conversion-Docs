---
id: listening
url: conversion/java/listening
title: Listening to conversion process events
linkTitle: Listening to events
weight: 4
description: "Follow this guide and learn how to track conversion process by subscribing to specific events of GroupDocs.Conversion for Java API."
keywords: Track conversion process, Subscribe to conversion process events
productName: GroupDocs.Conversion for Java
hideChildren: False
---
In some cases there is the need to monitor conversion process and to receive update for start, progress and completion of a conversion. For such situations [**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) expose extension point where the client application may hook up and receive updates.

To enable listening you have to:

*   Implement you own implementation of [IConverterListener](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.reporting/IConverterListener) interface.
*   Instantiate [ConverterSettings](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/ConverterSettings) class and pass an instance of the class created in first step
*   Pass [ConverterSettings](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/ConverterSettings) object factory to constructor of a [Converter](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/Converter) class.
*   Call [Convert](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter#convert(java.lang.String,%20com.groupdocs.conversion.options.convert.ConvertOptions))method of [Converter](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/Converter) class.

Here is a code that demonstrates how to enable listening for GroupDocs.Conversion.

```java
public class ConverterListener implements IConverterListener
{
    public void started()
    {
        System.out.println("Conversion started...");
    }
    public void progress(byte current)
    {
        System.out.println($"... " + current + "% ...");
    }
    public void completed()
    {
        System.out.println("... conversion completed");
    }
}
```

```java
IConverterListener listener = new ConverterListener();
ConverterSettings settingsFactory = new ConverterSettings
{
    Listener = listener
};
try(Converter converter = new Converter("sample.docx", settingsFactory))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.convert("converted.pdf", options);
}
```
