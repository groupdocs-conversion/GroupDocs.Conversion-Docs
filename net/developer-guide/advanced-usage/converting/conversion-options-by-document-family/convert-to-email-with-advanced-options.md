---
id: convert-to-email-with-advanced-options
url: conversion/net/convert-to-email-with-advanced-options
title: Convert to Email with advanced options
weight: 17
description: "Follow this guide and learn how to convert between email formats (MSG, EML, EMLX) and customize attachment processing using GroupDocs.Conversion for .NET."
keywords: Convert to Email, Convert to MSG, Convert to EML, Convert to EMLX, Email conversion, Email format conversion
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

## Introduction

GroupDocs.Conversion provides [EmailConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/emailconvertoptions) for converting between email formats. **Important**: EmailConvertOptions is specifically for email-to-email format conversions (e.g., MSG to EML), not for converting general documents to email formats.

## Properties

| Property | Type | Description |
|----------|------|-------------|
| [Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions-1/format/) | `EmailFileType` | Specifies the desired email format. Available options are: *Eml, Emlx, Msg, Vcf, Mbox, Pst, Ost, Olm* |
| [AttachmentContentHandler](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/emailconvertoptions/attachmentcontenthandler) | `Delegate` | A delegate to handle custom processing of email attachments during conversion |

## Basic Usage

Convert MSG files to EML format with default options:

```csharp
using (var converter = new Converter("message.msg"))
{
    var options = new EmailConvertOptions();
    converter.Convert("message.eml", options);
}
```

## Converting Between Email Formats

### Convert MSG to EML

The most common email format conversion - from Outlook MSG to standard EML:

```csharp
using (var converter = new Converter("newsletter.msg"))
{
    var options = new EmailConvertOptions
    {
        Format = EmailFileType.Eml
    };
    converter.Convert("newsletter.eml", options);
}
```

### Convert MSG to EMLX

Convert Outlook messages to Apple Mail format:

```csharp
using (var converter = new Converter("meeting-invite.msg"))
{
    var options = new EmailConvertOptions
    {
        Format = EmailFileType.Emlx
    };
    converter.Convert("meeting-invite.emlx", options);
}
```

### Convert EML to MSG

Convert standard EML files to Outlook MSG format:

```csharp
using (var converter = new Converter("customer-inquiry.eml"))
{
    var options = new EmailConvertOptions
    {
        Format = EmailFileType.Msg
    };
    converter.Convert("customer-inquiry.msg", options);
}
```

## Supported Email Formats

EmailConvertOptions works with the following email formats:

- **EML** - RFC-822 standard email format (most email clients)
- **EMLX** - Apple Mail email format (macOS Mail app)
- **MSG** - Microsoft Outlook and Exchange format
- **VCF** - Virtual Card Format (contact information)
- **MBOX** - Container format for email collections
- **PST** - Outlook Personal Storage Files
- **OST** - Outlook Offline Storage Files
- **OLM** - Microsoft Outlook for macOS format

**Note**: Not all format combinations are supported. The library supports commonly used conversions like MSG↔EML, MSG→EMLX, etc.

## Email Format Details

### MSG (Microsoft Outlook Message)

MSG is the proprietary format used by Microsoft Outlook:
- **Advantages**: Preserves Outlook-specific formatting, supports rich metadata
- **Platform**: Windows Outlook, Exchange Server
- **Use Case**: Enterprise email systems, Outlook integration

### EML (Electronic Mail Format)

EML is the standard RFC-822 email format:
- **Advantages**: Universal compatibility, plain text based
- **Platform**: Cross-platform (Thunderbird, Windows Mail, macOS Mail, webmail)
- **Use Case**: Email archival, cross-platform compatibility, email backups

### EMLX (Apple Mail Format)

EMLX is Apple's implementation of the EML standard:
- **Advantages**: Optimized for macOS Mail, includes additional metadata
- **Platform**: macOS Mail application
- **Use Case**: Mac-specific email workflows, Apple ecosystem integration

## Common Use Cases

### 1. Email Migration

Migrate email archives between different email clients:

```csharp
// Convert Outlook MSG archive to standard EML for cross-platform use
using (var converter = new Converter("archive-2024.msg"))
{
    var options = new EmailConvertOptions
    {
        Format = EmailFileType.Eml
    };
    converter.Convert("archive-2024.eml", options);
}
```

### 2. Platform Migration

Move from Windows Outlook to macOS Mail:

```csharp
// Convert MSG emails to EMLX for Apple Mail
using (var converter = new Converter("important-emails.msg"))
{
    var options = new EmailConvertOptions
    {
        Format = EmailFileType.Emlx
    };
    converter.Convert("important-emails.emlx", options);
}
```

### 3. Email Standardization

Convert proprietary formats to standards-based formats:

```csharp
// Standardize various email formats to EML
using (var converter = new Converter("meeting-notes.msg"))
{
    var options = new EmailConvertOptions
    {
        Format = EmailFileType.Eml
    };
    converter.Convert("meeting-notes.eml", options);
}
```

### 4. Email Client Compatibility

Ensure emails can be opened in different email clients:

```csharp
// Convert EML to MSG for Outlook users
using (var converter = new Converter("customer-feedback.eml"))
{
    var options = new EmailConvertOptions
    {
        Format = EmailFileType.Msg
    };
    converter.Convert("customer-feedback.msg", options);
}
```

## When to Use EmailConvertOptions

Use EmailConvertOptions when you need to:

- **Migrate email systems** between different platforms (Outlook ↔ Apple Mail ↔ Thunderbird)
- **Archive emails** in standard formats for long-term storage
- **Ensure compatibility** across different email clients
- **Convert between formats** for workflow integration
- **Standardize email formats** within an organization
- **Support multi-platform** email access

## Limitations

### Email-to-Email Only

EmailConvertOptions is **not** for converting general documents to email formats:

```csharp
// ❌ This will NOT work - cannot convert PDF to email format
using (var converter = new Converter("document.pdf"))
{
    var options = new EmailConvertOptions { Format = EmailFileType.Msg };
    converter.Convert("document.msg", options); // ConversionNotSupportedException
}
```

### Supported Source Formats

EmailConvertOptions works with:
- Email formats converting to other email formats
- Some format combinations may not be supported (e.g., MSG to MBOX)

## Converting Emails to Other Formats

To convert email messages to documents (PDF, DOCX, etc.), use the appropriate ConvertOptions for the target format:

```csharp
// ✅ Convert email to PDF
using (var converter = new Converter("message.msg"))
{
    var options = new PdfConvertOptions();
    converter.Convert("message.pdf", options);
}

// ✅ Convert email to Word document
using (var converter = new Converter("newsletter.eml"))
{
    var options = new WordProcessingConvertOptions();
    converter.Convert("newsletter.docx", options);
}
```

## Best Practices

1. **Choose the right target format**:
   - Use EML for maximum cross-platform compatibility
   - Use MSG for Outlook-specific workflows
   - Use EMLX for macOS Mail integration

2. **Test format combinations**:
   - Not all email-to-email conversions are supported
   - Verify your specific conversion path works before batch processing

3. **Preserve email structure**:
   - Email formats preserve headers, attachments, and metadata differently
   - Test conversions to ensure critical information is retained

4. **Handle attachments appropriately**:
   - Email attachments are typically preserved during format conversion
   - Use AttachmentContentHandler for custom attachment processing needs

## Summary

EmailConvertOptions provides control over email format conversions:

- **Email-to-Email conversions**: Convert between MSG, EML, EMLX, and other email formats
- **Platform migration**: Move emails between different email clients and platforms
- **Format standardization**: Convert proprietary formats to standards-based formats
- **Important limitation**: Cannot convert general documents to email formats

All examples on this page have been verified through automated testing to ensure accuracy.

## See Also

- [Convert Email Formats - Basic Usage]({{< ref "conversion/net/developer-guide/basic-usage/convert/email" >}})
- [Load Email Documents with Options]({{< ref "conversion/net/developer-guide/advanced-usage/loading/load-options-for-different-document-types/load-email-document-with-options" >}})
- [Convert Email Attachments]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-each-email-attachment-to-different-format" >}})
- [EmailConvertOptions API Reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/emailconvertoptions/)
- [EmailFileType API Reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/emailfiletype/)
