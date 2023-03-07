---
id: load-file-from-url
url: conversion/net/load-file-from-url
title: Load file from URL
weight: 3
description: "This article explains how to load PDF, Word, Excel, PowerPoint documents from URL when using GroupDocs.Conversion for .NET."
keywords: Load file from URL, Load file by URL GroupDocs.Conversion
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
The following code snippet shows how to convert a file from the URL:

```csharp
public static void Run()
{
    string url = "https://github.com/groupdocs-conversion/GroupDocs.Conversion-for-.NET/blob/master/Examples/Resources/SampleFiles/sample.docx?raw=true";
    string outputFile = Path.Combine("c:\output", "converted.pdf");
    using (Converter converter = new Converter(() => GetRemoteFile(url)))
    {
        PdfConvertOptions options = new PdfConvertOptions();
        converter.Convert(outputFile, options);
    }
}
        
private static Stream GetRemoteFile(string url)
{
    WebRequest request = WebRequest.Create(url);
    using (WebResponse response = request.GetResponse())
        return GetFileStream(response);
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
