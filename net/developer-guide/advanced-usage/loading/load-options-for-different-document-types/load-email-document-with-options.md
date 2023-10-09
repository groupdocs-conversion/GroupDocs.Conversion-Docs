---
id: load-email-document-with-options
url: conversion/net/load-email-document-with-options
title: Load Email document with options
weight: 3
description: "Learn this article and check how to load and convert Email documents with advanced options using GroupDocs.Conversion for .NET API."
keywords: Load document, Load Email document
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) provides [EmailLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/emailloadoptions) to give you control over how the source email document will be processed. The following options could be set:
| Option | Description |
|--------|-------------|
|**[Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/emailloadoptions/format)** | The document type is auto-detected during loading, however, you can specify explicitly the type of the source email document. Available options are: Msg, Eml, Emlx, Pst, Ost, Vcf, Mht |
|**[ConvertOwned ](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/emailloadoptions/convertowned)** | Controls whether the owned documents in the documents container must be converted |
|**[ConvertOwner](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/emailloadoptions/convertowner)** | Controls whether the documents container itself must be converted If this property is true the documents container will be the first converted document |
|**[Depth](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/emailloadoptions/depth)** | Controls how many levels in depth to perform the conversion |
|**[DisplayBccEmailAddress](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/emailloadoptions/displaybccemailaddress)** | Option to display or hide "Bcc" email address |
|**[DisplayCcEmailAddress](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/emailloadoptions/displayccemailaddress)** | Option to display or hide "Cc" email address |
|**[DisplayEmailAddress](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/emailloadoptions/displayemailaddress)** | Option to display or hide email address |
|**[DisplayFromEmailAddress](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/emailloadoptions/displayfromemailaddress)** | Option to display or hide "from" email address |
|**[DisplayHeader](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/emailloadoptions/displayheader)** | Option to display or hide the email header |
|**[DisplayToEmailAddress](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/emailloadoptions/displaytoemailaddress)** | Option to display or hide "to" email address |
|**[FieldTextMap](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/emailloadoptions/fieldtextmap)** | The mapping between email message [EmailField](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/emailfield) and field text representation |
|**[PreserveOriginalDate](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/emailloadoptions/preserveoriginaldate)** | defines whether to keep the original date header string in the mail message when saving (Default value is true) |
|**[ResourceLoadingTimeout](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/emailloadoptions/resourceloadingtimeout/)** | Specifies the timeout of loading the external resources. |
|**[TimeZoneOffset](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/emailloadoptions/timezoneoffset)** | Gets or sets the Coordinated Universal Time (UTC) offset for the message dates. This property defines the time zone difference, between the local time and UTC. |

### Control fields visibility

The following code sample shows how to convert an Email document and control the visibility of the fields:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new EmailLoadOptions
{
    DisplayHeader = false,
    DisplayFromEmailAddress = false,
    DisplayToEmailAddress = false,
    DisplayEmailAddress = false,
    DisplayCcEmailAddress = false,
    DisplayBccEmailAddress = false
};
using (Converter converter = new Converter("sample.msg", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

### Converting email attachments

The following code sample shows how to convert an Email document and all attachments:

```csharp
var source = "sample-with-attachment.eml";
var loadOptions = new EmailLoadOptions {
                         ConvertOwner = true,
                         ConvertOwned = true,
                         // convert email itself and the attachments
                         Depth = 2
                      };
using (var converter = new Converter(source, () => loadOptions))
{
    var index = 1;
    var options = new PdfConvertOptions();
    // Note: index = 1 is the email itself, all following indexes are attachments
    converter.Convert(() => new FileStream($"converted-{index++}.pdf", FileMode.Create) , options);
}
```

{{< alert style="warning" >}}This functionality is introduced in v20.1{{< /alert >}}

### Localize email fields captions

The following code sample shows how to convert an Email document and localize the Email fields

```csharp
var source = "sample.eml";
var loadOptions = new EmailLoadOptions
{
    FieldTextMap = new Dictionary<EmailField, string>
    {
        { EmailField.Subject, "Gegenstand" },
        { EmailField.From, "Von" },
        { EmailField.Attachments, "Anhänge" }
    }
};
using (var converter = new Converter(source, () => loadOptions))
{
    var options = new PdfConvertOptions();
    converter.Convert("converted.pdf" , options);
}


```

{{< alert style="warning" >}}This functionality is introduced in v20.3{{< /alert >}}

### Control date/time format

The following code sample shows how to convert an Email document and modify the date/time format

```csharp
var source = "sample.eml";
CultureInfo.CurrentCulture = new CultureInfo("fr-FR");
using (var converter = new Converter(source))
{
    var options = new PdfConvertOptions();
    converter.Convert("converted.pdf" , options);
}
```

{{< alert style="warning" >}}This functionality is introduced in v20.3{{< /alert >}}
