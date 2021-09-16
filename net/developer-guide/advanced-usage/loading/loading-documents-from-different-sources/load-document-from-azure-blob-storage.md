---
id: load-document-from-azure-blob-storage
url: conversion/net/load-document-from-azure-blob-storage
title: Load document from Azure Blob Storage
weight: 2
description: "This article demonstrates how to convert document stored in Azure Blob storage using GroupDocs.Conversion for .NET API."
keywords: Convert document from Azure Blob storage, Convert file
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
Following code snippet shows how to convert a document from Azure Blob Storage:

```csharp
public static void Run()
{
    string blobName = "sample.docx";
    string outputFile = Path.Combine("c:\output", "converted.pdf");
    using (Converter converter = new Converter(() => DownloadFile(blobName)))
    {
        PdfConvertOptions options = new PdfConvertOptions();
        converter.Convert(outputFile, options);
    }
}
        
public static Stream DownloadFile(string blobName)
{
    CloudBlobContainer container = GetContainer();
    CloudBlob blob = container.GetBlobReference(blobName);
    MemoryStream memoryStream = new MemoryStream();
    blob.DownloadToStream(memoryStream);
    memoryStream.Position = 0;
    return memoryStream;
}
private static CloudBlobContainer GetContainer()
{
    string accountName = "***";
    string accountKey = "***";
    string endpoint = $"https://{accountName}.blob.core.windows.net/";
    string containerName = "***";
    StorageCredentials storageCredentials = new StorageCredentials(accountName, accountKey);
    CloudStorageAccount cloudStorageAccount = new CloudStorageAccount(
        storageCredentials, new Uri(endpoint), null, null, null);
    CloudBlobClient cloudBlobClient = cloudStorageAccount.CreateCloudBlobClient();
    CloudBlobContainer container = cloudBlobClient.GetContainerReference(containerName);
    container.CreateIfNotExists();
    return container;
}
```

## More resources

### Examples and Demos

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!
