---
id: convert-to-presentation-with-advanced-options
url: conversion/net/convert-to-presentation-with-advanced-options
title: Convert to Presentation with advanced options
weight: 6
description: "Follow this guide and learn how documents convert to powerpoint presentations of PPT, PPTX formats with height, width, DPI, margins and other customizations using GroupDocs.Conversion for .NET."
keywords: Convert to Presentation, Convert Presentation, convert to powerpoint
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
GroupDocs.Conversion provides [PresentationConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/presentationconvertoptions) to give you control over conversion result when convert to powerpoint presentation format. Along with [common convert options]({{< ref "conversion/net/developer-guide/advanced-usage/converting/common-conversion-options/_index.md" >}}) from base class [PresentationConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/presentationconvertoptions) has the following additional options:

*   ********[Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/presentationconvertoptions/zoom)******** - desired result document type. Available options are: *Ppt, Pps, Pptx, Ppsx, Odp, Otp, Potx, Pot, Potm, Pptm, Ppsm*
*   **[Password](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/presentationconvertoptions/password)** - if set, the converted document will be password protected with the specified password
*   **[Zoom](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/presentationconvertoptions/zoom)** - specifies the zoom level in percentage

Following code snippet shows how to convert to Presentation with advanced options.

```csharp
using (Converter converter = new Converter("sample.docx"))
{
    PresentationConvertOptions options = new PresentationConvertOptions
    {
        PageNumber = 2,
        PagesCount = 1,
        Format = PresentationFileType.Ppt
    };
    converter.Convert("converted.ppt", options);
}
```
