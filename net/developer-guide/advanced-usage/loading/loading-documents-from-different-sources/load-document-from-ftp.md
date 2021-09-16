---
id: load-document-from-ftp
url: conversion/net/load-document-from-ftp
title: Load document from FTP
weight: 3
description: "This article demonstrates how to convert document stored in FTP storage using GroupDocs.Conversion for .NET API."
keywords: Convert document from FTP storage, Convert file
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
Following code snippet shows how to convert a document from FTP:

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

## More resources

### Examples and Demos

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!