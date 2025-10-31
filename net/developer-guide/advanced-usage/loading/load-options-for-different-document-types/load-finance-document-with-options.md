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

The following options are available:

| Option | Description |
|--------|-------------|
|**[Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/financeloadoptions/format)** | The document type is auto-detected during loading, but you can explicitly specify the source format. Available options are: *Xbrl, IXbrl* |

## Load XBRL document

The following code snippet shows how to load an XBRL document with explicit format specification:

With v24.10 and later:

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

Before v24.10:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadOptions> getLoadOptions = () => new FinanceLoadOptions
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

With v24.10 and later:

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

Before v24.10:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadOptions> getLoadOptions = () => new FinanceLoadOptions
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

With v24.10 and later:

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

Before v24.10:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadOptions> getLoadOptions = () => new FinanceLoadOptions
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

With v24.10 and later:

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

Before v24.10:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadOptions> getLoadOptions = () => new FinanceLoadOptions
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
