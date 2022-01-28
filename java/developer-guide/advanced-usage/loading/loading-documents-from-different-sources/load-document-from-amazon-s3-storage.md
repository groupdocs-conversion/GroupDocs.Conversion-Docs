---
id: load-document-from-amazon-s3-storage
url: conversion/java/load-document-from-amazon-s3-storage
title: Load document from Amazon S3 Storage
weight: 1
description: "This article demonstrates how to convert document stored in Amazon S3 storage using GroupDocs.Conversion for Java API."
keywords: Convert document from Amazon S3 storage, Convert file
productName: GroupDocs.Conversion for Java
hideChildren: False
---
Following code snippet shows how to convert a document from Amazon S3 Storage:

```java
 package com.groupdocs.conversion.examples.advanced_usage.loading.loading_documents_from_different_sources;

import com.amazonaws.auth.AWSCredentials;
import com.amazonaws.auth.AWSStaticCredentialsProvider;
import com.amazonaws.auth.BasicAWSCredentials;
import com.amazonaws.regions.Regions;
import com.amazonaws.services.s3.AmazonS3;
import com.amazonaws.services.s3.AmazonS3ClientBuilder;
import com.amazonaws.services.s3.model.S3Object;
import com.amazonaws.services.s3.model.S3ObjectInputStream;
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.examples.Constants;

import java.io.File;
import java.io.InputStream;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;

/**
* This example demonstrates how to download document from Amazon S3 storage and convert document.
*/
public class LoadDocumentFromAmazonS3 {

    public static void run()
    {
        String key = "sample.docx";
        String convertedFile = "C:\\output\\converted.pdf"; 
        Converter converter = new Converter(downloadFile(key));
        PdfConvertOptions options = new PdfConvertOptions();
        converter.convert(convertedFile, options);

        System.out.print("\nSource document converted successfully.\nCheck output in " + convertedFile);
    }

    public static InputStream downloadFile(String key)
    {
        AWSCredentials credentials = new BasicAWSCredentials(
                "<AWS accesskey>",
                "<AWS secretkey>"
        );
        AmazonS3 s3client = AmazonS3ClientBuilder.standard()
                .withCredentials(new AWSStaticCredentialsProvider(credentials))
                .withRegion(Regions.US_EAST_2)
                .build();
        String bucketName = "my-bucket";

        S3Object s3object = s3client.getObject(bucketName, key);
        S3ObjectInputStream inputStream = s3object.getObjectContent();
        return inputStream;
    }
}
```
