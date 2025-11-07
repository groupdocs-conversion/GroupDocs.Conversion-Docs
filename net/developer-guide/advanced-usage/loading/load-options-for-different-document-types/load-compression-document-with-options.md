---
id: load-compression-document-with-options
url: conversion/net/load-compression-document-with-options
title: Load compression document with options
weight: 20
description: "Learn how to load and convert compression files (ZIP, 7Z, RAR, TAR) with advanced options using GroupDocs.Conversion for .NET API."
keywords: Load compression file, Load and convert ZIP, Load and convert RAR, Load and convert 7Z, Archive file conversion
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) provides [CompressionLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/compressionloadoptions) to control how source compression files are processed. Compression files include formats like ZIP, 7Z, RAR, TAR, GZIP, and other archive formats.

The following options are available:

| Option | Description |
|--------|-------------|
|**[Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/compressionloadoptions/format)** | The document type is auto-detected during loading, but you can explicitly specify the source format. Available options include: *SevenZ, Bz2, Cab, Cpio, Gz, Gzip, Lz, Lzma, Rar, Tar, Xz, Z, Zip* |
|**[Password](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/compressionloadoptions/password)** | Set password to load protected archive |
|**[ConvertOwned](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/compressionloadoptions/convertowned)** | The owned documents will be converted (read-only, set to true by default) |
|**[ConvertOwner](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/compressionloadoptions/convertowner)** | The owner will not be converted (read-only, set to false by default) |
|**[Depth](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/compressionloadoptions/depth)** | Controls recursion depth for nested documents. Default value is 3. |

## Load ZIP archive

The following code snippet shows how to load a ZIP archive with explicit format specification:

With v24.10 and later:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new CompressionLoadOptions
{
    Format = CompressionFileType.Zip
};

using (Converter converter = new Converter("documents-archive.zip", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("documents-archive.pdf", options);
}
```

Before v24.10:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadOptions> getLoadOptions = () => new CompressionLoadOptions
{
    Format = CompressionFileType.Zip
};

using (Converter converter = new Converter("documents-archive.zip", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("documents-archive.pdf", options);
}
```

## Load RAR archive

The following code snippet shows how to load a RAR archive:

With v24.10 and later:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new CompressionLoadOptions
{
    Format = CompressionFileType.Rar
};

using (Converter converter = new Converter("backup-files.rar", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("backup-files.pdf", options);
}
```

Before v24.10:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadOptions> getLoadOptions = () => new CompressionLoadOptions
{
    Format = CompressionFileType.Rar
};

using (Converter converter = new Converter("backup-files.rar", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("backup-files.pdf", options);
}
```

## Load 7Z archive

The following code snippet shows how to load a 7Z archive:

With v24.10 and later:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new CompressionLoadOptions
{
    Format = CompressionFileType.SevenZ
};

using (Converter converter = new Converter("project-files.7z", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("project-files.pdf", options);
}
```

Before v24.10:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadOptions> getLoadOptions = () => new CompressionLoadOptions
{
    Format = CompressionFileType.SevenZ
};

using (Converter converter = new Converter("project-files.7z", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("project-files.pdf", options);
}
```

## Convert between compression formats

The following code snippet shows how to convert from ZIP to 7Z format:

With v24.10 and later:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new CompressionLoadOptions
{
    Format = CompressionFileType.Zip
};

using (Converter converter = new Converter("source-archive.zip", getLoadOptions))
{
    CompressionConvertOptions options = new CompressionConvertOptions
    {
        Format = CompressionFileType.SevenZ
    };
    converter.Convert("source-archive.7z", options);
}
```

Before v24.10:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadOptions> getLoadOptions = () => new CompressionLoadOptions
{
    Format = CompressionFileType.Zip
};

using (Converter converter = new Converter("source-archive.zip", getLoadOptions))
{
    CompressionConvertOptions options = new CompressionConvertOptions
    {
        Format = CompressionFileType.SevenZ
    };
    converter.Convert("source-archive.7z", options);
}
```

## Load password-protected archive

The following code snippet shows how to load a password-protected ZIP archive:

With v24.10 and later:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new CompressionLoadOptions
{
    Format = CompressionFileType.Zip,
    Password = "archive-password"
};

using (Converter converter = new Converter("protected-archive.zip", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("protected-archive.pdf", options);
}
```

Before v24.10:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadOptions> getLoadOptions = () => new CompressionLoadOptions
{
    Format = CompressionFileType.Zip,
    Password = "archive-password"
};

using (Converter converter = new Converter("protected-archive.zip", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("protected-archive.pdf", options);
}
```
