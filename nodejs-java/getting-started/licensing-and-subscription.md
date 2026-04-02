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
'use strict';

// Require dependencies
const groupdocs = require('@groupdocs/groupdocs.conversion');
const path = require('path');

// Set license path
const licensePath = path.resolve(__dirname, 'GroupDocs.Conversion.lic');

// Set the license
const license = new groupdocs.License();
license.setLicense(licensePath);
console.log('License set successfully');

// Exit the process
process.exit(0);
```

### Set License from Stream

The following example shows how to load a license from a stream.

```js
// Require dependencies
const groupdocs = require('@groupdocs/groupdocs.conversion');
const path = require('path');
const fs = require('fs');

// Set license path get stream
const licensePath = path.resolve(__dirname, 'GroupDocs.Conversion.lic');
const licenseStream = fs.createReadStream(licensePath);

// Read license from stream
groupdocs.readDataFromStream(licenseStream)
  .then(stream => {
    // Set the license
    const license = new groupdocs.License();
    license.setLicense(stream);
    process.exit(0);
  })
  .catch(error => {
    // Show error
    console.error('Error setting license:', error);
    process.exit(1);
  });
```
