---
id: load-presentation-document-with-options
url: conversion/net/load-presentation-document-with-options
title: Load Presentation document with options
weight: 8
description: "Learn this article and check how to load and convert Microsoft PowerPoint documents with advanced options using GroupDocs.Conversion for .NET API."
keywords: Load document, Load and convert PowerPoint document, Load and convert PPTX presentation, Load and convert PPT
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) provides [PresentationLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/presentationloadoptions) to give you control over how Microsoft PowerPoint or Open Document presentation will be converted into target format. The following options could be set:

*   **[Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/presentationloadoptions/format)** - the document type is auto detected during loading, however you can specify explicitly the type of the source presentation document. Available options are: *Ppt, Pps, Pptx, Ppsx, Odp, Otp, Potx, Pot, Potm, Pptm, Ppsm*
*   **[DefaultFont](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/presentationloadoptions/defaultfont)** - default font for rendering the presentation. The following font will be used if a presentation font is missing.  
*   **[FontSubstitutes](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/presentationloadoptions/fontsubstitutes)** - substitute specific fonts from the source presentation document
*   **[Password](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/presentationloadoptions/password)** -  password to unlock protected document
*   **[HideComments](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/presentationloadoptions/hidecomments)** - specifies that comments from source presentation must be hidden during conversion
*   **[ShowHiddenSlides](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/presentationloadoptions/showhiddenslides)** - specifies that hidden slides should be included in converted document

## Hide comments

Like many other Microsoft Office applications PowerPoint provides "Comments" feature to simplify the presentation review. By default Comments pane will be present in a converted document. In case you want to hide comments set [HideComments](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/presentationloadoptions/hidecomments) to *true *as shown in a code sample below:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new PresentationLoadOptions
{
    HideComments = true
};
using (Converter converter = new Converter("sample.pptx", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

## Specify font substitutions

Original PowerPoint presentations may use some specific and non-standard fonts for text formatting that are not available at the time of conversion. GroupDocs.Conversion for .NET allows you to provide substitutions for missing fonts by setting [FontSubstitues](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/presentationloadoptions/fontsubstitutes) collection with original/substitute font pairs.

The following code sample shows how to convert PPTX presentation and specify substitutions for missing fonts:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new PresentationLoadOptions
{
    DefaultFont = "Helvetica",
    FontSubstitutes = new List<FontSubstitute>
    {
       FontSubstitute.Create("Tahoma", "Arial"),
       FontSubstitute.Create("Times New Roman", "Arial"),
    }
};
using (Converter converter = new Converter("sample.pptx", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

## Include hidden slides

Just like you are able to show or hide slides in a Microsoft PowerPoint presentation manually, GroupDocs.Conversion for .NET allows to display hidden slides in a converted document programmatically (by default all hidden slides are excluded from converted document). You just have to set [ShowHiddenSlides](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/presentationloadoptions/showhiddenslides) property to *true*.

The following code sample shows how to convert PPTX presentation including the hidden slides:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new PresentationLoadOptions
{
    ShowHiddenSlides = true
};
using (Converter converter = new Converter("sample.pptx", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```