---
id: how-to-use-custom-cache-implementation
url: conversion/java/how-to-use-custom-cache-implementation
title: How to use custom cache implementation
weight: 1
description: "Follow this guide and learn how to implement custom cache implementation when document with GroupDocs.Conversion for Java API."
keywords: Custom cache for GroupDocs.Conversion
productName: GroupDocs.Conversion for Java
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) implements caching to local drive out of the box. For flexibility GroupDocs.Conversion provides and extension point which allows you to cache conversion result in your own way. You can do this by using [ICache](https://reference.groupdocs.com/annotation/java/com.groupdocs.annotation.cache/ICache) interface implementation.  
Let's see how to implement some custom cache implementation using this extension point.

## Using Redis cache

The following steps should be followed.

*   Create *RedisCache* class which implements [ICache](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.caching/ICache) interface.
*   Instantiate the *RedisCache* class.
*   Declare a delegate which will be used from [Converter](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter) class as factory of [ConverterSettings](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion/ConverterSettings). In the body of this delegate, instantiate [ConverterSettings](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion/ConverterSettings) class and set property [setCache](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion/ConverterSettings#setCache(com.groupdocs.conversion.caching.ICache)) with the *RedisCache* class instance from previous step.
*   Instantiate [Converter](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter) class with path to source document and the delegate from the previous step as constructor's parameters.
*   Create instance of [PdfConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfConvertOptions) class.
*   Call [Convert](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter#convert(java.lang.String,%20com.groupdocs.conversion.options.convert.ConvertOptions)) method of [Converter](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter) instance.

Below is the code that demonstrates how to use custom caching for GroupDocs.Conversion:

```java
package com.groupdocs.conversion.examples.advanced_usage.caching;

import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.ConverterSettings;
import com.groupdocs.conversion.examples.Constants;
import com.groupdocs.conversion.internal.c.a.ms.System.Diagnostics.Stopwatch;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;

public class HowToUseCustomCacheImplementation {
    /**
    * This example demonstrates how to implement custom cache when rendering document.
    */
    public static void run()
    {
        String outputDirectory = Constants.getOutputDirectoryPath(null);

        RedisCache cache = new RedisCache(/*"sample_"*/);
        ConverterSettings settingsFactory = new ConverterSettings();
        settingsFactory.setCache(cache);

        Converter converter = new Converter(Constants.SAMPLE_DOCX, settingsFactory);
        PdfConvertOptions options = new PdfConvertOptions();

        Stopwatch stopWatch = Stopwatch.startNew();
        converter.convert("converted.pdf", options);
        stopWatch.stop();

        System.out.print(String.format("Time taken on first call to Convert method %d (ms).", stopWatch.getElapsedMilliseconds()));

        stopWatch.restart();
        converter.convert("converted-1.pdf", options);
        stopWatch.stop();

        System.out.print(String.format("Time taken on second call to Convert method %d (ms).", stopWatch.getElapsedMilliseconds()));
    }
}
```
