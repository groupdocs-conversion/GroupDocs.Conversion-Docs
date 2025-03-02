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
In some scenarios, it is necessary to track the conversion process and receive updates about the start, progress, and completion of the conversion. To address such requirements, [GroupDocs.Conversion](https://products.groupdocs.com/conversion/java/) provides an extension point that allows client applications to subscribe to these events and receive real-time updates.

To enable event listening during the conversion process, follow these steps:

1.   Implement the [IConverterListener](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.reporting/iconverterlistener/) interface to define custom event handling logic.
2.   Create an instance of the [ConverterSettings](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/convertersettings/) class and configure it with the custom implementation of [IConverterListener](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.reporting/iconverterlistener/).
3.   Pass the configured [ConverterSettings](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/convertersettings/) instance to the [Converter](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/) class constructor.
4.   Call the convert method on the [Converter](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/) class to start the conversion process.

Below is a code example demonstrating how to implement and enable event listening using

{{< tabs "code-example">}}
{{< tab "ConverterListener.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.ConverterSettings;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.reporting.IConverterListener;

public class ConverterListener implements IConverterListener {
    @Override
    public void started() {
        System.out.println("Conversion started...");
    }

    @Override
    public void progress(byte current) {
        System.out.println("... " + current + "% completed...");
    }

    @Override
    public void completed() {
        System.out.println("... Conversion completed!");
    }

    public static void convert() {
        IConverterListener listener = new ConverterListener();
        ConverterSettings settingsFactory = new ConverterSettings();
        settingsFactory.setListener(listener);

        try (Converter converter = new Converter("formatting.docx", () -> settingsFactory)) {
            PdfConvertOptions options = new PdfConvertOptions();
            converter.convert("converted.pdf", options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "Console output" >}}  
{{< tab-text >}}
```
... 7% completed...
... 14% completed...
... 21% completed...
... 28% completed...
... 35% completed...
... 42% completed...
... 50% completed...
... 57% completed...
... 64% completed...
... 71% completed...
... 78% completed...
... 85% completed...
... 92% completed...
... 100% completed...
... Conversion completed!
```
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

## Key Points:
- **Event Methods**: The `started`, `progress`, and `completed` methods provide hooks for monitoring different stages of the conversion process.
- **Thread Safety**: Ensure thread-safe implementation if the conversion process is run in a multi-threaded environment.
- **Clean Resource Management**: Use try-with-resources to ensure the `Converter` instance is properly closed after the operation.