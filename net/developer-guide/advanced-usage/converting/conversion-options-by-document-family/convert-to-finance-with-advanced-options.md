---
id: convert-to-finance-with-advanced-options
url: conversion/net/convert-to-finance-with-advanced-options
title: Convert to Finance formats with advanced options
weight: 18
description: "Learn about FinanceConvertOptions class for financial data formats (XBRL, iXBRL, OFX) in GroupDocs.Conversion for .NET."
keywords: Convert to XBRL, Convert to iXBRL, Convert to OFX, Financial reporting conversion, XBRL conversion
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

GroupDocs.Conversion provides the [FinanceConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/financeconvertoptions) class to specify financial data format conversion settings. This class implements [IPagedConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/ipagedconvertoptions) for page selection support.

## Supported Finance Formats

The following financial data formats are recognized:

| Format | Extension | Description | Use Case |
|--------|-----------|-------------|----------|
| **XBRL** | .xbrl | eXtensible Business Reporting Language | Financial reporting, regulatory compliance |
| **iXBRL** | .ixbrl | Inline XBRL (HTML + XBRL) | Human-readable and machine-readable financial reports |
| **OFX** | .ofx | Open Financial Exchange | Banking data, financial transactions |

## Properties

**[Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions-1/format/)** - Specifies the desired financial file format. Available options are: *Xbrl, IXbrl, Ofx*.

**[PageNumber](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/ipagedconvertoptions/pagenumber)** - Specifies the starting page number for conversion.

**[PagesCount](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/ipagedconvertoptions/pagescount)** - Specifies the number of pages to convert.

## API Structure

The following example shows the API structure for FinanceConvertOptions:

```csharp
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;

// Create options object
FinanceConvertOptions options = new FinanceConvertOptions
{
    Format = FinanceFileType.Xbrl,
    PageNumber = 1,      // Starting page (for multi-page sources)
    PagesCount = 10      // Number of pages to process
};
```

## Converting Between Finance Formats

You can convert between XBRL and iXBRL formats. This allows you to transform between human-readable inline XBRL and standard XBRL format.

### Convert XBRL to iXBRL

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;

// Load the source XBRL file
using (Converter converter = new Converter("financial-report.xbrl"))
{
    // Configure iXBRL convert options
    FinanceConvertOptions options = new FinanceConvertOptions
    {
        Format = FinanceFileType.IXbrl
    };

    // Convert and save
    converter.Convert("financial-report.ixbrl", options);
}
```

### Convert iXBRL to XBRL

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;

// Load the source iXBRL file
using (Converter converter = new Converter("inline-report.ixbrl"))
{
    // Configure XBRL convert options
    FinanceConvertOptions options = new FinanceConvertOptions
    {
        Format = FinanceFileType.Xbrl
    };

    // Convert and save
    converter.Convert("inline-report.xbrl", options);
}
```

## Format Selection

You can specify different financial formats using the Format property:

### XBRL Format

XBRL (eXtensible Business Reporting Language) is the international standard for digital business reporting:

```csharp
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;

FinanceConvertOptions xbrlOptions = new FinanceConvertOptions
{
    Format = FinanceFileType.Xbrl
};
```

### iXBRL Format

iXBRL (Inline XBRL) combines human-readable HTML with machine-readable XBRL data:

```csharp
FinanceConvertOptions ixbrlOptions = new FinanceConvertOptions
{
    Format = FinanceFileType.IXbrl
};
```

### OFX Format

OFX (Open Financial Exchange) is used for financial data exchange between institutions and applications:

```csharp
FinanceConvertOptions ofxOptions = new FinanceConvertOptions
{
    Format = FinanceFileType.Ofx
};
```

## Format Support Notes

**Supported conversions:**
- XBRL ↔ iXBRL (bidirectional conversion between standard and inline XBRL)

**Not supported:**
- Conversion from standard document formats (PDF, Word, Excel) to financial formats
- Conversion from financial formats to other formats (PDF, images, etc.)
- OFX conversions to/from XBRL or iXBRL

Financial formats like XBRL require highly specific data structures, taxonomies, and metadata that are not present in general documents.

## More Resources

- [API Reference: FinanceConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/financeconvertoptions)
- [API Reference: FinanceFileType](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/financefiletype)
- [Supported File Formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}})
- [Common Conversion Options]({{< ref "conversion/net/developer-guide/advanced-usage/converting/common-conversion-options/_index.md" >}})
