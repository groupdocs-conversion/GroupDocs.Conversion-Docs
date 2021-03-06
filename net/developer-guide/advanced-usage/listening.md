---
id: listening
url: conversion/net/listening
title: Listening to conversion process events
linkTitle: Listening to events
weight: 4
description: "Follow this guide and learn how to track conversion process by subscribing to specific events of GroupDocs.Conversion for .NET API."
keywords: Track conversion process, Subscribe to conversion process events, track conversion
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
In some cases there is the need to monitor conversion process and to receive update for start, progress and completion of a conversion. For such situations [**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) expose extension point where the client application may hook up and receive updates.. 

To enable listening you have to:

*   Implement you own implementation of [IConverterListener](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.reporting/iconverterlistener) interface
*   Instantiate [ConverterSettings](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/convertersettings) class and pass an instance of the class created in first step
*   Pass [ConverterSettings](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/convertersettings) object factory to constructor of a [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class
*   Call [Convert](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter/methods/convert/2) method of [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class

Here is a code that demonstrates how to enable listening for GroupDocs.Conversion.

```csharp
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

```csharp
IConverterListener listener = new ConverterListener();
Contracts.Func<ConverterSettings> settingsFactory = () => new ConverterSettings
{
    Listener = listener
};
using (Converter converter = new Converter("sample.docx", settingsFactory))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

