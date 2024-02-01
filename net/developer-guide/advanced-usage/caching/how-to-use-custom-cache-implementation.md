---
id: how-to-use-custom-cache-implementation
url: conversion/net/how-to-use-custom-cache-implementation
title: How to use custom cache implementation
weight: 1
description: "Follow this guide and learn how to implement custom cache implementation when document with GroupDocs.Conversion for .NET API."
keywords: Custom cache for GroupDocs.Conversion, custom cache, cache conversion result, conversion result   
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
**[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net)** implements caching to local drive out of the box. For flexibility GroupDocs.Conversion provides and extension point which allows you to cache conversion result in your own way. You can do this by using [ICache](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.caching/icache) interface implementation.  
Let's see how to implement some custom cache implementation using this extension point.

## Using Redis cache

To implement the Redis cache, follow these steps:

1.   Create *RedisCache* class which implements [ICache](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.caching/icache) interface
2.   Instantiate the *RedisCache* class
3.   Declare a delegate which will be used from [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) classes factory of [ConverterSettings](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/convertersettings). In the body of this delegate, instantiate [ConverterSettings](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/convertersettings) class and set property [Cache](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/convertersettings/cache) with the *RedisCache* class instance from previous step
4.   Instantiate [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class with path to source document and the delegate from the previous step as constructor's parameters
5.   Create instance of [PdfConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions) class
6.   Call [Convert](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/convert/#convert_3) method of [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) instance

Below is the code that demonstrates how to use custom caching for GroupDocs.Conversion.

```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.IO;
using System.Linq;
using System.Reflection;
using System.Runtime.Serialization;
using System.Runtime.Serialization.Formatters.Binary;
using GroupDocs.Conversion.Caching;
using GroupDocs.Conversion.Options.Convert;
using StackExchange.Redis;
namespace GroupDocs.Conversion.Examples.CSharp.AdvancedUsage.Caching
{
    internal class HowToUseCustomCacheImplementation
    {
        /// <summary>
        /// This example demonstrates how to implement custom cache when rendering document.
        /// </summary>
        public static void Run()
        {
            string outputDirectory = Constants.GetOutputDirectoryPath();
            
            RedisCache cache = new RedisCache("sample_");
            Contracts.Func<ConverterSettings> settingsFactory = () => new ConverterSettings
            {
                Cache = cache
            };
            using (Converter converter = new Converter(Constants.SAMPLE_DOCX, settingsFactory))
            {
                PdfConvertOptions options = new PdfConvertOptions();
                Stopwatch stopWatch = Stopwatch.StartNew();
                converter.Convert("converted.pdf", options);
                stopWatch.Stop();
                Console.WriteLine("Time taken on first call to Convert method {0} (ms).", stopWatch.ElapsedMilliseconds);
                stopWatch.Restart();
                converter.Convert("converted-1.pdf", options);
                stopWatch.Stop();
                Console.WriteLine("Time taken on second call to Convert method {0} (ms).", stopWatch.ElapsedMilliseconds);
            }
            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }
    }
    public class RedisCache : ICache, IDisposable
    {
        private readonly string _cacheKeyPrefix;
        private readonly ConnectionMultiplexer _redis;
        private readonly IDatabase _db;
        private readonly string _host = "192.168.0.1:6379";
        public RedisCache(string cacheKeyPrefix)
        {
            _cacheKeyPrefix = cacheKeyPrefix;
            _redis = ConnectionMultiplexer.Connect(_host);
            _db = _redis.GetDatabase();
        }
        public void Set(string key, object data)
        {
            if (data == null)
                return;
            string prefixedKey = GetPrefixedKey(key);
            using (MemoryStream stream = GetStream(data))
            {
                _db.StringSet(prefixedKey, RedisValue.CreateFrom(stream));
            }
        }
        public bool TryGetValue(string key, out object value)
        {
            var prefixedKey = GetPrefixedKey(key);
            var redisValue = _db.StringGet(prefixedKey);
            if (redisValue.HasValue)
            {
                var data = Deserialize(redisValue);
                value = data;
                return true;
            }

            value = default;
            return false;
        }
        public IEnumerable<string> GetKeys(string filter)
        {
            return _redis.GetServer(_host).Keys(pattern: $"*{filter}*")
                .Select(x => x.ToString().Replace(_cacheKeyPrefix, string.Empty))
                .Where(x => x.StartsWith(filter, StringComparison.InvariantCultureIgnoreCase))
                .ToList();
        }
        private string GetPrefixedKey(string key)
            => $"{_cacheKeyPrefix}{key}";
        private object Deserialize(RedisValue redisValue)
        {
            object data;
            using (MemoryStream stream = new MemoryStream(redisValue))
            {
                BinaryFormatter formatter = new BinaryFormatter
                {
                    Binder = new IgnoreAssemblyVersionSerializationBinder()
                };
                try
                {
                    data = formatter.Deserialize(stream);
                }
                catch (SerializationException)
                {
                    data = null;
                }
            }
            return data;
        }
        private MemoryStream GetStream(object data)
        {
            MemoryStream result = new MemoryStream();
            if (data is Stream stream)
            {
                stream.Position = 0;
                stream.CopyTo(result);
            }
            else
            {
                BinaryFormatter formatter = new BinaryFormatter();
                formatter.Serialize(result, data);
            }
            return result;
        }
        public void Dispose()
        {
            _redis.Dispose();
        }
        private class IgnoreAssemblyVersionSerializationBinder : SerializationBinder
        {
            public override Type BindToType(string assemblyName, string typeName)
            {
                string assembly = Assembly.GetExecutingAssembly().FullName;
                Type type = Type.GetType($"{typeName}, {assembly}");
                return type;
            }
        }
    }
}

```
