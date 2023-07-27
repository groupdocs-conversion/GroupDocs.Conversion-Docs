---
id: licensing-and-subscription
url: conversion/nodejs-java/licensing-and-subscription
title: Licensing
weight: 5
description: "Free conversion API version for Node.js developers is available to evaluate the API which will be similar to licensed version but with few limitations."
keywords: free conversion, license, conversion, API, nodejs
productName: GroupDocs.Conversion for Node.js via Java
hideChildren: False
toc: True
---

Sometimes, in order to study the system better, you want to dive into the code as fast as possible. To make this easier, GroupDocs.Conversion provides different purchase plans or offers a Free Trial and a 30-day Temporary License for evaluation.

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

You can find pricing information on the ["Pricing Information"](https://purchase.groupdocs.com/pricing/conversion/nodejs-java) page.

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

```js
String licensePath = "path to the .lic file";
License license = new License();
license.setLicense(licensePath);
```

### Set License from Stream

The following example shows how to load a license from a stream.

```js
String licensePath = "path to the .lic file";
try (InputStream fileStream = new FileInputStream(licensePath)) {
    License license = new License();
    license.setLicense(fileStream);
}
```

### Set Metered License

You can also set `Metered` license as an alternative to the license file. It is a new licensing mechanism that will be used along with the existing licensing method. It is useful for customers who want to be billed based on the usage of the API features. For more details, please refer to [Metered Licensing FAQ](https://purchase.groupdocs.com/faqs/licensing/metered) section.

Following is the sample code demonstrating how to use the `Metered` class.

```js
String publicKey = ""; // Your public license key
String privateKey = ""; // Your private license key

Metered metered = new Metered();
metered.setMeteredKey(publicKey, privateKey);

// Get amount (MB) consumed
Double consumption = metered.getConsumptionQuantity();
System.out.print("Metered consumption = " + consumption);

// Get count of credits consumed
Double credit = metered.getConsumptionCredit();
System.out.print("Metered credit = " + credit);
```
