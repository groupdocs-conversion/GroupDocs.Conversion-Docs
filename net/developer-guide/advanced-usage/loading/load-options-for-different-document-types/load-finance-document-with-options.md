---
id: load-finance-document-with-options
url: conversion/net/load-finance-document-with-options
title: Load finance document with options
weight: 16
description: "Learn how to load and convert finance documents (XBRL, iXBRL) with advanced options using GroupDocs.Conversion for .NET API."
keywords: Load finance document, Load and convert XBRL document, Load and convert iXBRL document, Load financial reporting files
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) provides [FinanceLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/financeloadoptions) to control how source finance documents are processed. Finance documents include XBRL (eXtensible Business Reporting Language) and iXBRL (inline XBRL) files used for financial reporting.

{{< alert style="info" >}}
On .NET 6 and later, converting XBRL and iXBRL documents to spreadsheet formats requires the [System.Drawing.Common](https://www.nuget.org/packages/System.Drawing.Common/4.7.3) 4.7.3 package in your project; on Linux, libgdiplus must also be installed. Without it, the conversion throws a `MissingDependencyException` that names the missing package.
{{< /alert >}}

The following options are available:

| Option | Description |
|--------|-------------|
|**[Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/financeloadoptions/format)** | The document type is auto-detected during loading, but you can explicitly specify the source format. Available options are: *Xbrl, IXbrl* |
|**[ExternalResourceHandler](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/financeloadoptions/externalresourcehandler)** | A handler called for each taxonomy reference while `SkipExternalResources` is true. It can skip a reference but cannot allow one that is denied. Default: null. Available since version 26.10. |
|**[SkipExternalResources](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/financeloadoptions/skipexternalresources)** | Whether to deny taxonomy files outside the document's own folder. Default: true. Set it to `false` to convert a document that references a remote taxonomy. Available since version 26.10. |
|**[WhitelistedResources](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/financeloadoptions/whitelistedresources)** | Validated like on the other load options classes, but not consulted for XBRL: a whitelisted remote schema is still denied. Available since version 26.10. |

{{< alert style="warning" >}}
Since version 26.10, external resources are not loaded by default, and an XBRL or inline XBRL document loads only when every taxonomy file it references is inside the document's own folder and the document is converted from a file path. A document that references a remote taxonomy, as most filings do, fails to load with `InvalidLoadOptionsException`. To convert such a document, set `SkipExternalResources` to `false`. See [XBRL and inline XBRL]({{< ref "conversion/net/developer-guide/advanced-usage/loading/skip-external-resources.md#xbrl-and-inline-xbrl" >}}).
{{< /alert >}}

## Load XBRL document

The following code snippet shows how to load an XBRL document with explicit format specification:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new FinanceLoadOptions
{
    Format = FinanceFileType.Xbrl
};

using (Converter converter = new Converter("financial-report.xbrl", getLoadOptions))
{
    SpreadsheetConvertOptions options = new SpreadsheetConvertOptions();
    converter.Convert("financial-report.xlsx", options);
}
```

## Load iXBRL document

The following code snippet shows how to load an iXBRL (inline XBRL) document:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new FinanceLoadOptions
{
    Format = FinanceFileType.IXbrl
};

using (Converter converter = new Converter("financial-statement.ixbrl", getLoadOptions))
{
    SpreadsheetConvertOptions options = new SpreadsheetConvertOptions();
    converter.Convert("financial-statement.xlsx", options);
}
```

## Convert finance document to CSV

The following code snippet shows how to load an XBRL document and convert it to CSV format:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new FinanceLoadOptions
{
    Format = FinanceFileType.Xbrl
};

using (Converter converter = new Converter("quarterly-report.xbrl", getLoadOptions))
{
    SpreadsheetConvertOptions options = new SpreadsheetConvertOptions
    {
        Format = SpreadsheetFileType.Csv
    };
    converter.Convert("quarterly-report.csv", options);
}
```

## Convert between finance formats

The following code snippet shows how to convert from iXBRL to XBRL:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new FinanceLoadOptions
{
    Format = FinanceFileType.IXbrl
};

using (Converter converter = new Converter("annual-report.ixbrl", getLoadOptions))
{
    FinanceConvertOptions options = new FinanceConvertOptions
    {
        Format = FinanceFileType.Xbrl
    };
    converter.Convert("annual-report.xbrl", options);
}
```
