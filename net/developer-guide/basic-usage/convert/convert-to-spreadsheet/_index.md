---
id: convert-to-spreadsheet
url: conversion/net/convert-to-spreadsheet
title: Convert to Spreadsheet
weight: 5
description: "Follow this guide and learn how to convert documents to spreadsheet of MS Excel formats - XLSX, XLS, XLSB or Open Document formats - ODS, OTS using GroupDocs.Conversion for .NET."
keywords: Convert to Excel, Convert to Spreadsheet, Convert to XLS, Convert to XLSX
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) can convert any source document to the following spreadsheet formats: *Xls, Xlsx, Xlsm, Xlsb, Ods, Ots, Xltx, Xlt, Xltm, Tsc, Xlam, Csv*. When just instantiate the [SpreadsheetConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/spreadsheetconvertoptions) class without specifying the target format explicitly, *Xlsx* will be used as a default format.

Conversion to spreadsheet format could be triggered by following below steps:

*   Create new instance of [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class and pass source document path as a constructor parameter
*   Instantiate [SpreadsheetConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/spreadsheetconvertoptions) class
*   Call [Convert](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter/methods/convert/2) method of [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class instance and pass filename for the converted document and the instance of [SpreadsheetConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/spreadsheetconvertoptions) from the previous step

The following code show how to convert any document to spreadsheet. 

```csharp
using (Converter converter = new Converter("sample.docx"))
{
    SpreadsheetConvertOptions options = new SpreadsheetConvertOptions();
    converter.Convert("converted.xlsx", options);
}
```

## More resources
### Advanced Usage Topics
To learn more about convert file features, please refer to the [advanced usage section]({{< ref "conversion/net/developer-guide/advanced-usage/_index.md" >}}).

### Examples and Demos

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!
