---
id: convert-to-presentation
url: conversion/net/convert-to-presentation
title: Convert to Presentation
weight: 4
description: "This article demonstrates how to convert documents to PowerPoint presentation of PPT, PPTX, ODP and may other formats with couple C# code lines and GroupDocs.Conversion for .NET."
keywords: Convert to Presentation, Convert to PPT, Convert to PPTX
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) can convert any source document to the following presentation formats: *Ppt, Pps, Pptx, Ppsx, Odp, Otp, Potx,  Pot, Potm, Pptm, Ppsm*. When just instantiate the [PresentationConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/presentationconvertoptions) class without specifying the target format explicitly, *Pptx* will be used as a default format.

Conversion to presentation format could be triggered by following below steps:

*   Create new instance of [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class and pass source document path as a constructor parameter
*   Instantiate [PresentationConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/presentationconvertoptions) class
*   Call [Convert](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter/methods/convert/2) method of [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class instance and pass filename for the converted document and the instance of [PresentationConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/presentationconvertoptions) from the previous step

The following code show how to convert any document to presentation. 

```csharp
using (Converter converter = new Converter("sample.docx"))
{
    PresentationConvertOptions options = new PresentationConvertOptions();
    converter.Convert("converted.pptx", options);
}
```

## More resources

### Advanced Usage Topics

To learn more about convert file features, please refer to the [advanced usage section]({{< ref "conversion/net/developer-guide/advanced-usage/_index.md" >}}).

### Examples and Demos

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!