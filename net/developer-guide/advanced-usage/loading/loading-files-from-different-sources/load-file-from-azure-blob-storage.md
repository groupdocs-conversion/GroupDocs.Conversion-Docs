---
id: load-file-from-azure-blob-storage
url: conversion/net/load-file-from-azure-blob-storage
title: Load file from Azure blob storage
weight: 6
description: "This article demonstrates how to convert file stored in Azure Blob storage using GroupDocs.Conversion for .NET API."
keywords: Convert file from Azure Blob storage, Convert file
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
The following code snippet shows how to convert a file from Azure Blob Storage. It uses the [Azure.Storage.Blobs](https://www.nuget.org/packages/Azure.Storage.Blobs) NuGet package:

```csharp
public static void Run()
{
    string blobName = "sample.docx";
    string outputFile = Path.Combine(@"c:\output", "converted.pdf");
    using (Converter converter = new Converter(() => DownloadFile(blobName)))
    {
        PdfConvertOptions options = new PdfConvertOptions();
        converter.Convert(outputFile, options);
    }
}
        
public static Stream DownloadFile(string blobName)
{
    BlobContainerClient container = GetContainer();
    BlobClient blob = container.GetBlobClient(blobName);
    MemoryStream memoryStream = new MemoryStream();
    blob.DownloadTo(memoryStream);
    memoryStream.Position = 0;
    return memoryStream;
}

private static BlobContainerClient GetContainer()
{
    string accountName = "***";
    string accountKey = "***";
    string containerName = "***";
    Uri containerUri = new Uri($"https://{accountName}.blob.core.windows.net/{containerName}");
    StorageSharedKeyCredential credential = new StorageSharedKeyCredential(accountName, accountKey);
    return new BlobContainerClient(containerUri, credential);
}
```
