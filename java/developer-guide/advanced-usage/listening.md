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
In some cases, there is a need to monitor the conversion process and to receive updates upon a start, progress and completion of a conversion. For such situations, [**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) exposes an extension point where the client application may hook up and receive updates. 

To enable listening, follow these steps:

1.   Create your own implementation of the [IConverterListener](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.reporting/IConverterListener) interface.
2.   Instantiate the [ConverterSettings](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/ConverterSettings) class and pass an instance of the class created in the first step.
3.   Pass the [ConverterSettings](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/ConverterSettings) object factory to the constructor of a [Converter](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/Converter) class.
4.   Call the [Convert](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter#convert(java.lang.String,%20com.groupdocs.conversion.options.convert.ConvertOptions)) method of the [Converter](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/Converter) class.

The following code snippet shows how to enable listening for GroupDocs.Conversion:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.ConverterSettings;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.reporting.IConverterListener;
...
public class ConverterListener implements IConverterListener
	{
	    public void started()
	    {
	        System.out.println("Conversion started...");
	    }
	    public void progress(byte current)
	    {
	        System.out.println("... " + current + "% ...");
	    }
	    public void completed()
	    {
	        System.out.println("... conversion completed");
	    }
	
    public static void run()
    {              
        IConverterListener listener = new ConverterListener();        
        ConverterSettings settingsFactory = new ConverterSettings();
        settingsFactory.setListener(listener); 
                
        try(Converter converter = new Converter("sample.docx", settingsFactory))
        {
            PdfConvertOptions options = new PdfConvertOptions();
            converter.convert("converted.pdf", options);
        } 
    }
}
```