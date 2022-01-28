---
id: load-document-from-azure-blob-storage
url: conversion/java/load-document-from-azure-blob-storage
title: Load document from Azure Blob Storage
weight: 2
description: "This article demonstrates how to convert document stored in Azure Blob storage using GroupDocs.Conversion for Java API."
keywords: Convert document from Azure Blob storage, Convert file
productName: GroupDocs.Conversion for Java
hideChildren: False
---
Following code snippet shows how to convert a document from Azure Blob Storage:

```java
  package com.groupdocs.conversion.examples.advanced_usage.loading.loading_documents_from_different_sources;

import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.examples.Constants;

import com.groupdocs.conversion.exceptions.GroupDocsConversionException;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.microsoft.azure.storage.CloudStorageAccount;
import com.microsoft.azure.storage.blob.CloudBlob;
import com.microsoft.azure.storage.blob.CloudBlobClient;
import com.microsoft.azure.storage.blob.CloudBlobContainer;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
import java.io.File;


/**
* This example demonstrates how to download document from Azure Blob storage and convert document.
*/
public class LoadDocumentFromAzureBlobStorage {
    public static void run()
    {
        String blobName = "sample.docx";
        String convertedFile = "C:\\output\\converted.pdf"; 
        
        try {
        Converter converter = new Converter(new ByteArrayInputStream(DownloadFile(blobName).toByteArray()));
        PdfConvertOptions options = new PdfConvertOptions();
        converter.convert(convertedFile, options);
        }
        catch(Exception e){
            throw new GroupDocsConversionException(e.getMessage());
        }

        System.out.print("\nSource document converted successfully.\nCheck output in "+ convertedFile);
    }
    
    public static final String STORAGE_CONNECTION_STRING
            = "DefaultEndpointsProtocol=https;"
            + "AccountName=Ram;" //Your account name.
            + "AccountKey=key"; //your account key.

    public static ByteArrayOutputStream DownloadFile(String blobName) throws Exception
    {
        CloudBlobContainer container = GetContainer();

        CloudBlob blob = container.getBlockBlobReference(blobName);
        ByteArrayOutputStream memoryStream = new ByteArrayOutputStream();
        blob.download(memoryStream);
        //memoryStream.Position = 0;
        return memoryStream;
    }

    private static CloudBlobContainer GetContainer() throws Exception
    {
        String containerName = "***";

        CloudStorageAccount cloudStorageAccount = CloudStorageAccount.parse(STORAGE_CONNECTION_STRING);
        CloudBlobClient cloudBlobClient = cloudStorageAccount.createCloudBlobClient();
        CloudBlobContainer container = cloudBlobClient.getContainerReference(containerName);
        container.createIfNotExists();

        return container;
    }
}

```
