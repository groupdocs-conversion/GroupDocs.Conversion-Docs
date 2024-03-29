---
id: listening
url: conversion/net/listening
title: Listening to conversion process events
linkTitle: Listening to events
weight: 5
description: "Follow this guide and learn how to track conversion process by subscribing to specific events of GroupDocs.Conversion for .NET API."
keywords: Track conversion process, Subscribe to conversion process events, track conversion
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
In some cases, there is a need to monitor the conversion process and to receive updates upon a start, progress and completion of a conversion. For such situations, [**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) exposes an extension point where the client application may hook up and receive updates. 

To enable listening, follow these steps:

1.  Create your own implementation of the [IConverterListener](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.reporting/iconverterlistener) interface.
2.  Instantiate the [ConverterSettings](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/convertersettings) class and pass an instance of the class created in the first step.
3.  Pass the [ConverterSettings](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/convertersettings) object factory to the constructor of the [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class.
4.  Call the [Convert](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/convert/#convert_3) method of the [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class.

The following code snippet shows how to enable listening for GroupDocs.Conversion events:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Reporting;

IConverterListener listener = new ConverterListener();
Func<ConverterSettings> settingsFactory = () => new ConverterSettings
{
    Listener = listener
};
using (Converter converter = new Converter("sample.docx", settingsFactory))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}

public class ConverterListener : IConverterListener
{
    public void Started()
    {
        Console.WriteLine("Conversion started...");
    }
    public void Progress(byte current)
    {
        Console.WriteLine($"... {current} % ...");
    }
    public void Completed()
    {
        Console.WriteLine("... conversion completed");
    }
}
```

