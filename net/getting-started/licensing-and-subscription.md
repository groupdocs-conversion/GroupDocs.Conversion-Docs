---
id: licensing-and-subscription
url: conversion/net/licensing-and-subscription
title: Licensing
weight: 5
description: free conversion API version is available to evaluate the API which will be similar to licensed version but with few limitations.
keywords: free conversion, license, conversion, API
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

Sometimes, to study the system better, you want to dive into the code as fast as possible. To make this easier, GroupDocs.Conversion offers a Free Trial and a 30-day Temporary License for evaluation and provides different purchase plans.

{{< alert style="info" >}}
Note that there are a number of general policies and practices that guide you on how to evaluate, properly license, and purchase our products. You can find them in the ["Purchase Policies and FAQ"](https://purchase.groupdocs.com/policies) section.
{{< /alert >}}

## Free Trial or Temporary License

You can try GroupDocs.Conversion without buying a license.

### Free Trial

The evaluation version is the same as the purchased one – the evaluation version simply becomes licensed when you set the license. You can set the license in a number of ways that are described in the next sections of this article.

The evaluation version comes with the limitations:

* Only the first 3 pages are processed.
* Documents with more than 3 pages are not supported.
* Trial badges are placed in the document on the top of each page.
  
### Temporary License

If you wish to test GroupDocs.Conversion without the limitations of the trial version, you can also request a 30-day Temporary License. For more details, see the ["Get a Temporary License"](https://purchase.groupdocs.com/temporary-license) page.

## How to set up a license

{{< alert style="info" >}}

You can find pricing information on the ["Pricing Information"](https://purchase.groupdocs.com/pricing/conversion/net) page.

{{< /alert >}}

After the license is obtained you need to set up the license. This section describes options of how this can be done and also comments on some common questions.

The license should be set:

- Only once per application domain,
- and before using any other GroupDocs.Conversion classes.

{{< alert style="info" >}}

The license can be set multiple times per app domain but we recommend doing it once since all calls to the `SetLicense` method except for the first one will just waste processor time.

{{< /alert >}}


### Set License from File

The following code sets a license from a file.

```csharp
string licensePath = "path to the .lic file";
License license = new License();
license.SetLicense(licensePath);
```

### Set License from Stream

The following example shows how to set a license from a stream.

```csharp
string licensePath = "path to the .lic file";
using (FileStream fileStream = File.OpenRead(licensePath))
{
    License license = new License();
    license.SetLicense(fileStream);
}
```
<!--
{{< alert style="info" >}}Calling [License](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/license).[SetLicense](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/license/setlicense/) multiple times is not harmful but simply wastes processor time. If you are developing a Windows Forms or console application, call License.SetLicense in your startup code, before using GroupDocs.conversion classes.  
When developing an ASP.NET application, you can call License.SetLicense from the Global.asax.cs (Global.asax.vb) file in the Application\_Start protected method. It is called once when the application starts.  
Do not call [License](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/license).[SetLicense](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/license/setlicense/) from within Page\_Load methods since it means the license will be loaded every time a web page is loaded.
{{< /alert >}}
-->

### Set Metered License

You can also set [Metered](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/metered) license as an alternative to the license file. It is a new licensing mechanism that will be used along with the existing licensing method. It is useful for customers who want to be billed based on the usage of the API features. For more details, please refer to [Metered Licensing FAQ](https://purchase.groupdocs.com/faqs/licensing/metered) section.

Following is the sample code demonstrating how to use `Metered` licensing.
<!--
Here are the simple steps to use the `Metered` class.

1. Create an instance of [Metered](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/metered) class.
2. Pass public & private keys to [SetMeteredKey](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/metered/setmeteredkey/) method.
3. Do processing (perform task).
4. call method [GetConsumptionQuantity](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/metered/getconsumptionquantity) of the `Metered` class.
5. It will return the amount/quantity of API requests that you have consumed so far.
6. call method [GetConsumptionCredit](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/metered/getconsumptioncredit) of the [Metered](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/metered) class.
7. It will return the credit that you have consumed so far.

Following is the sample code demonstrating how to use [Metered](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/metered) class.
-->

```csharp
string publicKey = ""; // Your public license key
string privateKey = ""; // Your private license key

Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);

// Get amount (MB) consumed
decimal amountConsumed = GroupDocs.Conversion.Metered.GetConsumptionQuantity();
Console.WriteLine("Amount (MB) consumed: " + amountConsumed);

// Get count of credits consumed
decimal creditsConsumed = GroupDocs.Conversion.Metered.GetConsumptionCredit();
Console.WriteLine("Credits consumed: " + creditsConsumed);
```
