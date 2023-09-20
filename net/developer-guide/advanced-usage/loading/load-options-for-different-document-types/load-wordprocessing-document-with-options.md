---
id: load-wordprocessing-document-with-options
url: conversion/net/load-wordprocessing-document-with-options
title: Load WordProcessing document with options
weight: 11
description: "Learn this article and check how to convert Microsoft Word DOC/DOCX and Open Document ODT/OTT files hiding comments and tracked changes panel, setting default font and applying font substitution using features of GroupDocs.Conversion for .NET API."
keywords: Convert Word document in C#, Convert DOC in C#, Convert DOCX C#, Convert ODT file C#, Convert OTT file C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) provides [WordProcessingLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/wordprocessingloadoptions) to give you control over how the source Microsoft Word document will be converted. The following options could be set:
| Option | Description |
|--------|-------------|
|**[Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/wordprocessingloadoptions/format)** | The document type is auto-detected during loading, however, you can specify explicitly the type of the source WordProcessing document. Available options are: *Doc, Docm, Docx, Dot, Dotm, Dotx, Rtf, Odt, Ott, Mobi, Txt* |
|**[AutoFontSubstitution](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/wordprocessingloadoptions/autofontsubstitution)** | If false, GroupDocs.Conversion uses the DefaultFont for the substitution of missing fonts. If true, GroupDocs.Conversion evaluates all the related fields in FontInfo (Panose, Sig etc) for the missing font and finds the closest match among the available font sources.|
|**[DefaultFont](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/wordprocessingloadoptions/defaultfont)** | Specifies the font to use if a document font is missing. |
|**[FontSubstitutes](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/wordprocessingloadoptions/fontsubstitutes)** | Substitute specific fonts from the source document. |
|**[Password](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/wordprocessingloadoptions/password)** | A password to unlock the protected document. |
|**[HideWordTrackedChanges](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/wordprocessingloadoptions/hidewordtrackedchanges)** | Specifies that tracked changes should not be included in the converted document. |
|**[HideComments](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/wordprocessingloadoptions/hidecomments)** | Specifies that comments from the source document should be hidden in the converted document. |
|**[SkipExternalResources](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/wordprocessingloadoptions/skipexternalresources)** |  If enabled, the external resources (except for those listed in `WhitelistedResources`) will not be loaded during the conversion. |
|**[WhitelistedResources](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/wordprocessingloadoptions/whitelistedresources)** | Specifies which external resources will be loaded even when the loading of other external resources is restricted. |

    Note: that the font substitution mechanism will override the DefaultFont in cases when FontInfo for the missing font is available in the document.

## Hide comments

Microsoft Word provides the "Comment" feature that allows multiple authors or reviewers to discuss a document when they are not working with it simultaneously. All added comments are displayed in an area to the right of the document text. After the DOCX document with comments is converted to another format, the Comments pane is also present in a resultant document. If it's required to hide comments in a converted document programmatically, you can use the following code sample to do this with a couple of lines of C# code:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new WordProcessingLoadOptions
{
    HideComments = true
};
using (Converter converter = new Converter("sample.docx", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

## Hide tracked changes

Track Changes is another feature of Microsoft Word that provides a handy way to collaborate during document proofreading and review - it's like you're marking errors with a pen and making some notes in the margins. All changes made by coworkers are highlighted and may be rejected or accepted and become permanent. By default, the Track Changes panel will also be displayed when converting a DOCX document to another format, however, there is an option to hide it completely using GroupDocs.Conversion for .NET API. 

The following code sample shows how to convert a DOCX document to PDF and hide tracked changes pane:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new WordProcessingLoadOptions
{
    HideWordTrackedChanges = true
};
using (Converter converter = new Converter("sample.docx", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

## Specify font substitution

Microsoft Word document content is often formatted with different fonts like Arial, Calibri, Times New Roman etc., and these fonts are usually stored at the computer where the document is originally created or edited. Sometimes it happens that during DOCX document conversion to another format, some fonts used by a particular document are not present on the computer where conversion is performed. So the resulting converted document may look too different from the original file.

Of course GroupDocs.Conversion for .NET will try to select the most appropriate font substitution from available font sources and fonts embedded in the original document, but you can also specify font substitution explicitly. For doing this it is just needed to call the [Create](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.contracts/fontsubstitute/create) method of [FontSubstitute](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.contracts/fontsubstitute) class and provide names for original and substitute fonts.

The following code sample shows how to convert a DOCX document with font substitution for missing fonts:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new WordProcessingLoadOptions
{
    AutoFontSubstitution = false,
	DefaultFont = "Helvetica",
    FontSubstitutes = new List<FontSubstitute>
    {
        FontSubstitute.Create("Tahoma", "Arial"),
        FontSubstitute.Create("Times New Roman", "Arial"),
    }
};
using (Converter converter = new Converter("sample.docx", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```
