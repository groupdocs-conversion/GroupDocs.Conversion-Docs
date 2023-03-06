---
id: load-document-from-amazon-s3-storage
url: conversion/net/load-document-from-amazon-s3-storage
title: Load document from Amazon S3 storage
linkTitle: From Amazon S3 storage
weight: 5
description: " This article demonstrates how to convert document stored in Amazon S3 storage using GroupDocs.Conversion for .NET API."
keywords: Convert document from Amazon S3 storage, Convert file
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
The following code snippet shows how to convert a document from Amazon S3 Storage:

```csharp
public static void Run()
{
    string key = "sample.docx";
    string outputFile = Path.Combine("c:\output" , "converted.pdf");
    using (Converter converter = new Converter(() => DownloadFile(key)))
    {
        PdfConvertOptions options = new PdfConvertOptions();
        converter.Convert(outputFile, options);
    }
}
        
public static Stream DownloadFile(string key)
{
    AmazonS3Client client = new AmazonS3Client();
    string bucketName = "my-bucket";
    GetObjectRequest request = new GetObjectRequest
    {
        Key = key,
        BucketName = bucketName
    };
    using (GetObjectResponse response = client.GetObject(request))
    {
        MemoryStream stream = new MemoryStream();
        response.ResponseStream.CopyTo(stream);
        stream.Position = 0;
        return stream;
    }
}
```
