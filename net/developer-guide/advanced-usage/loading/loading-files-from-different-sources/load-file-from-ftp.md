---
id: load-file-from-ftp
url: conversion/net/load-file-from-ftp
title: Load file from FTP
weight: 4
description: "This article demonstrates how to convert file stored in FTP storage using GroupDocs.Conversion for .NET API."
keywords: Convert file from FTP storage, Convert file
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
The following code snippet shows how to convert a file from FTP:

```csharp
public static void Run()
{
    string outputFile = Path.Combine("c:\output", "converted.pdf");
    string filePath = "ftp://localhost/sample.doc";
    using (Converter converter = new Converter(() => GetFileFromFtp(filePath)))
    {
        PdfConvertOptions options = new PdfConvertOptions();
        converter.Convert(outputFile, options);
    }
}

private static Stream GetFileFromFtp(string filePath)
{
    Uri uri = new Uri(filePath);
    FtpWebRequest request = CreateRequest(uri);
    using (WebResponse response = request.GetResponse())
        return GetFileStream(response);
}

private static FtpWebRequest CreateRequest(Uri uri)
{
    FtpWebRequest request = (FtpWebRequest)WebRequest.Create(uri);
    request.Method = WebRequestMethods.Ftp.DownloadFile;
    return request;
}

private static Stream GetFileStream(WebResponse response)
{
    MemoryStream fileStream = new MemoryStream();
    using (Stream responseStream = response.GetResponseStream())
        responseStream.CopyTo(fileStream);
    fileStream.Position = 0;
    return fileStream;
}
```
