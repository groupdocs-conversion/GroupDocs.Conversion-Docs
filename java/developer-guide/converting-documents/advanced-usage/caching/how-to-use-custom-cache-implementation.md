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

[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) provides built-in caching to the local drive for improved performance. However, for greater flexibility, the library allows developers to implement custom caching mechanisms by extending the [ICache](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.caching/icache/) interface. This approach enables storing conversion results in alternate storage systems, such as memory caches, distributed caches, or databases.

This guide demonstrates how to implement a custom caching mechanism using **Redis**, a popular distributed in-memory cache, with [**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java).

## Steps to Implement a Redis-Based Custom Cache

1.   Implement the [ICache](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.caching/icache/) interface to define the caching logic using **Redis** as the backend.
2.   Create an instance of the **Redis-based** implementation.
3.   Use a delegate to instantiate the [ConverterSettings](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/convertersettings/) class. Configure the cache for [ConverterSettings](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/convertersettings/) using the `setCache` method and pass the custom cache instance.
4.   Create a [Converter](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/) instance, providing the path to the source document and the custom [ConverterSettings](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/convertersettings/) delegate as parameters.
5.   Instantiate the desired [ConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/convertoptions/) class (e.g., [PdfConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfconvertoptions/) for PDF conversion).
6.   Call the [convert](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/#convert-java.lang.String-com.groupdocs.conversion.options.convert.ConvertOptions-) method of the [Converter](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/) class to process the document.

The following code demonstrates how to implement a custom **Redis-based** caching mechanism for GroupDocs.Conversion:

{{< tabs "code-example">}}
{{< tab "CustomCacheImplementation.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.ConverterSettings;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import java.time.Duration;
import java.time.Instant;

public class CustomCacheImplementation {
    public static void convert() {

        // Define cache key prefix
        String cacheKeyPrefix = "myPrefix:";

        // Create an instance of the Redis-based custom cache
        RedisCache cache = new RedisCache(cacheKeyPrefix);

        // Configure the ConverterSettings with custom cache
        ConverterSettings settingsFactory = new ConverterSettings();
        settingsFactory.setCache(cache);

        // Initialize the Converter with the source document and settings
        try(Converter converter = new Converter("professional-services.pdf", ()-> settingsFactory)) {
            // Define conversion options for PDF
            PdfConvertOptions options = new PdfConvertOptions();

            // Measure time taken for the first conversion
            Instant start = Instant.now();
            converter.convert("converted.pdf", options);
            Instant end = Instant.now();
            System.out.println(String.format("Time taken on first Convert call: %d ms", Duration.between(start, end).toMillis()));

            // Measure time taken for the second conversion (cached result)
            start = Instant.now();
            converter.convert("converted-1.pdf", options);
            end = Instant.now();
            System.out.println(String.format("Time taken on second Convert call: %d ms", Duration.between(start, end).toMillis()));
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "RedisCache.java" >}}  
{{< tab-text >}}
```java
import com.groupdocs.conversion.caching.ICache;
import redis.clients.jedis.Jedis;
import redis.clients.jedis.JedisPool;
import redis.clients.jedis.JedisPoolConfig;
import redis.clients.jedis.util.Pool;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
import java.io.InputStream;
import java.util.List;
import java.util.Set;
import java.util.stream.Collectors;

public class RedisCache implements ICache, AutoCloseable {
    private final String cacheKeyPrefix;
    private final Pool<Jedis> jedisPool;

    public RedisCache(String cacheKeyPrefix) {
        this.cacheKeyPrefix = cacheKeyPrefix;
        String host = "192.168.222.4";
        this.jedisPool = new JedisPool(new JedisPoolConfig(), host);
    }

    public void set(String key, Object data) {
        if (data == null) {
            return;
        }

        String prefixedKey = getPrefixedKey(key);
        try (ByteArrayOutputStream outputStream = new ByteArrayOutputStream()) {

            byte[] buf = new byte[8192];
            int length;
            while ((length = ((InputStream)data).read(buf)) != -1) {
                outputStream.write(buf, 0, length);
            }

            try (Jedis jedis = jedisPool.getResource()) {
                jedis.set(prefixedKey.getBytes(), outputStream.toByteArray());
            }
        } catch (Exception e) {
            throw new RuntimeException("Error setting data to Redis", e);
        }
    }

    public Object tryGetValue(String key) {
        String prefixedKey = getPrefixedKey(key);
        try (Jedis jedis = jedisPool.getResource()) {
            byte[] data = jedis.get(prefixedKey.getBytes());
            if (data != null) {
                return new ByteArrayInputStream(data);
            }
        } catch (Exception e) {
            throw new RuntimeException("Error getting data from Redis", e);
        }
        return null;
    }

    public List<String> getKeys(String filter) {
        try (Jedis jedis = jedisPool.getResource()) {
            Set<String> keys = jedis.keys("*" + filter + "*");
            return keys.stream()
                    .map(key -> key.replace(cacheKeyPrefix, ""))
                    .filter(key -> key.toLowerCase().startsWith(filter.toLowerCase()))
                    .collect(Collectors.toList());
        }
    }

    private String getPrefixedKey(String key) {
        return cacheKeyPrefix + key;
    }

    @Override
    public void close() {
        jedisPool.close();
    }
}
```
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

This approach provides a robust solution for integrating a custom caching layer, optimizing document conversion workflows in both performance and scalability.