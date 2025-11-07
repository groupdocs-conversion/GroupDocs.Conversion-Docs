---
id: load-database-document-with-options
url: conversion/net/load-database-document-with-options
title: Load Database Documents with Options
weight: 15
description: "Learn how to use DatabaseLoadOptions to configure database document loading in GroupDocs.Conversion for .NET. Supports NSF (Lotus Notes) and SQL formats."
keywords: DatabaseLoadOptions, load database, NSF, SQL, Lotus Notes, database conversion, GroupDocs.Conversion
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

## Introduction

The **DatabaseLoadOptions** class enables you to configure how database documents and scripts are loaded in GroupDocs.Conversion. This class supports enterprise database formats used in corporate environments and database administration.

DatabaseLoadOptions works with database formats including NSF (Lotus Notes/IBM Notes storage) and SQL (Structured Query Language scripts).

## Properties

| Property | Type | Description |
|----------|------|-------------|
| `Format` | `DatabaseFileType` | The input database format (get; set;) |

## Basic Usage

For most scenarios, GroupDocs.Conversion automatically detects the database format:

```csharp
using (var converter = new Converter("customer-records.nsf"))
{
    converter.Convert("customer-records.pdf", new PdfConvertOptions());
}
```

## Using DatabaseLoadOptions with LoadContext

When you need explicit control over loading behavior, use DatabaseLoadOptions with the LoadContext delegate pattern:

```csharp
using (var converter = new Converter(
    "email-archive.nsf",
    (LoadContext loadContext) => new DatabaseLoadOptions()))
{
    converter.Convert("email-archive.pdf", new PdfConvertOptions());
}
```

## Working with Different Database Formats

GroupDocs.Conversion supports multiple database formats through DatabaseLoadOptions. Each format should be explicitly specified:

### NSF (Lotus Notes Storage Facility)

NSF is the database file format used by IBM Notes (formerly Lotus Notes), commonly used for storing emails, calendars, documents, and forms in enterprise environments:

```csharp
using (var converter = new Converter(
    "project-notes.nsf",
    (LoadContext loadContext) => new DatabaseLoadOptions
    {
        Format = DatabaseFileType.Nsf
    }))
{
    converter.Convert("project-notes.pdf", new PdfConvertOptions());
}
```

**Common use cases:**
- Email archives and mailbox exports
- Corporate document management systems
- Project collaboration databases
- Team calendars and scheduling systems

### SQL (Structured Query Language)

SQL files contain database scripts and queries used to create, modify, or query relational databases:

```csharp
using (var converter = new Converter(
    "schema-definition.sql",
    (LoadContext loadContext) => new DatabaseLoadOptions
    {
        Format = DatabaseFileType.Sql
    }))
{
    converter.Convert("schema-definition.pdf", new PdfConvertOptions());
}
```

**Common use cases:**
- Database schema documentation
- Migration script archives
- SQL query documentation
- Database backup scripts as PDF

## Converting Multiple Database Formats

Convert different database formats in a single workflow:

```csharp
// NSF to PDF
using (var converter = new Converter(
    "team-calendar.nsf",
    (LoadContext loadContext) => new DatabaseLoadOptions
    {
        Format = DatabaseFileType.Nsf
    }))
{
    converter.Convert("team-calendar.pdf", new PdfConvertOptions());
}

// SQL to PDF
using (var converter = new Converter(
    "migration-script.sql",
    (LoadContext loadContext) => new DatabaseLoadOptions
    {
        Format = DatabaseFileType.Sql
    }))
{
    converter.Convert("migration-script.pdf", new PdfConvertOptions());
}
```

## Supported Database Formats

DatabaseLoadOptions works with:
- **NSF** - Notes Storage Facility (IBM Notes/Lotus Notes database format)
- **SQL** - Structured Query Language scripts and queries

## Common Use Cases

Use DatabaseLoadOptions when you need to:

1. **Archive email systems** - Convert Lotus Notes mailboxes to PDF for long-term storage
2. **Document database schemas** - Create PDF documentation from SQL scripts
3. **Compliance and auditing** - Convert database documents for regulatory compliance
4. **Knowledge management** - Extract and convert corporate knowledge from Notes databases
5. **Database documentation** - Generate readable documentation from SQL scripts
6. **Legacy system migration** - Convert old Lotus Notes databases to modern formats

## When to Use DatabaseLoadOptions

Use DatabaseLoadOptions when:

- Converting Lotus Notes/IBM Notes databases (NSF)
- Processing SQL scripts and database queries
- Working with enterprise database documentation
- Archiving corporate email and collaboration data
- You need explicit control over database document loading

## Without DatabaseLoadOptions

For simple conversions, you can rely on automatic format detection:

```csharp
using (var converter = new Converter("customer-records.nsf"))
{
    converter.Convert("customer-records.pdf", new PdfConvertOptions());
}
```

GroupDocs.Conversion automatically detects the database format in most cases, so DatabaseLoadOptions is optional unless you need specific loading configuration.

## Output Format Compatibility

Database documents can be converted to various output formats:

- **Document formats**: PDF, DOCX, TXT, RTF
- **Web formats**: HTML, MHTML
- **Spreadsheet formats**: XLSX, XLS
- **Presentation formats**: PPTX, PPT
- **Image formats**: PNG, JPG, TIFF (page-by-page conversion)

## NSF Format Details

The NSF format is a container that can include:
- Email messages
- Calendar entries
- Contact information
- Documents and attachments
- Forms and views
- Access control lists

When converting NSF files, GroupDocs.Conversion processes the database structure and content, making it suitable for archival and documentation purposes.

## SQL Format Details

SQL files typically contain:
- CREATE TABLE statements
- ALTER TABLE modifications
- INSERT/UPDATE/DELETE operations
- SELECT queries
- Stored procedures
- Database constraints and indexes

Converting SQL files to PDF creates readable documentation of database schemas and operations, useful for:
- Code reviews
- Database design documentation
- Training materials
- Change management records

## Summary

DatabaseLoadOptions provides control over database document loading:
- **Format**: Specify NSF or SQL format explicitly
- **Supports**: IBM Notes databases (NSF) and SQL scripts
- **Use Case**: Enterprise data archival, compliance, database documentation

All examples on this page have been verified through automated testing to ensure accuracy.

## See Also

- [Context Objects - Complete Guide]({{< ref "conversion/net/developer-guide/basic-usage/context-objects-complete-guide" >}})
- [DatabaseFileType API Reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/databasefiletype/)
- [DatabaseLoadOptions API Reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/databaseloadoptions/)
