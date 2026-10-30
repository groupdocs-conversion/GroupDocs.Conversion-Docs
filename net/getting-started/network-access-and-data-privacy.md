---
id: network-access-and-data-privacy
url: conversion/net/network-access-and-data-privacy
title: Network access and data privacy
weight: 7
description: "Learn when GroupDocs.Conversion for .NET accesses the network, what never leaves your machine, and how to run it offline or in an air-gapped environment."
keywords: network access, data privacy, offline, air-gapped, SSRF, external resources, metered license, GroupDocs.Conversion
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

## Summary

[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) is an on-premise library: it runs inside your own process, on your own infrastructure. GroupDocs never receives the documents you convert.

By default, converting a document does not request the resources it references. The library's own code contacts a server only in the situations listed below, and each of them is either off by default or something your code asks for explicitly.

## What never leaves your machine

* The content of the documents you convert and of the files they produce.
* File names and paths.
* Usage data. The library's code reports usage only when you use a [metered license](#metered-licensing), and then only quantities, never document content.

## When GroupDocs.Conversion accesses the network

### Loading external resources referenced by a document

**Off by default.** A document can reference content it does not carry: a remote image or stylesheet in an HTML page or an e-mail, a linked picture in a Word document, a taxonomy schema in an XBRL filing. GroupDocs.Conversion does not load such resources unless you allow them: `SkipExternalResources` is `true` in every load options class that supports it, and UNC paths are never loaded.

You can allow specific resources by absolute URI prefix with `WhitelistedResources`, all of them with `SkipExternalResources = false`, or decide for each resource in your own code with `ExternalResourceHandler`, which can also supply a resource's content so that no request is made. See [Skip loading of external resources]({{< ref "conversion/net/developer-guide/advanced-usage/loading/skip-external-resources.md" >}}) for the rules, the supported formats and examples.

### Downloading a license file over HTTP

**Opt-in.** When you call `License.SetLicense` with a path to a license file that does not exist, and the `GROUPDOCS_LIC_PATH` environment variable holds an `http://` or `https://` URL, the license file is downloaded from that URL, with a five-second timeout. If the variable is not set, or the license file exists, no request is made. Setting a license from a local file or from a stream never accesses the network. See [Licensing]({{< ref "conversion/net/getting-started/licensing-and-subscription.md" >}}).

### Metered licensing

**Opt-in.** With a metered license (`Metered.SetMeteredKey`), the library reports usage quantities — the amount of data processed and the credits consumed — together with your subscription identifiers to the GroupDocs billing service. The report carries no document content, file names or paths. Metered licensing needs network access, so it does not suit air-gapped systems: use a license file or a license stream there instead.

### Code you supply

GroupDocs.Conversion itself makes no request in the following cases, but code you provide may:

* **Loading a document from a URL.** The library has no URL-based constructor: the [load from URL]({{< ref "conversion/net/developer-guide/advanced-usage/loading/loading-files-from-different-sources/load-file-from-url.md" >}}) example downloads the file in your code and passes the stream to `Converter`.
* **Connectors.** Video, audio, OCR and HEIC conversions run through connectors you implement and register, such as `IVideoConnector` or `IOcrConnector`. Whatever they access is up to your implementation. See [Convert video]({{< ref "conversion/net/developer-guide/basic-usage/convert/video.md" >}}) and [Convert image with OCR]({{< ref "conversion/net/developer-guide/basic-usage/convert/image-ocr.md" >}}).

## How this is verified

The product's test suite converts probe documents whose external references point at a local test listener — HTML, e-mail, office documents, SVG, XML, XBRL, 3D models, PDF, archives and more — and fails if any conversion under default options sends a request to it. It also checks that references a document only mentions, such as hyperlinks and form actions, are never requested even when external resources are allowed, and that every load options class denies external resources as soon as it is constructed.

The measurement has limits: it observes requests to the references planted in the probe documents, and when one entry of an archive fails to convert, the conversion stops, so the entries after it are not measured.

These statements apply to version 26.10 and later.

## Running offline

To run GroupDocs.Conversion without any network access:

1. Keep the default `SkipExternalResources = true`, or allow only `file:` prefixes in `WhitelistedResources`.
2. Set the license from a local file or a stream, and do not set `GROUPDOCS_LIC_PATH` to a URL.
3. Do not use a metered license.
4. Make sure your own connectors and loading code do not access the network.

To enforce this independently of the library, block outbound traffic for the process at the network or container level.

## Diagnosing an unexpected request

If you observe an outbound request from a process that uses GroupDocs.Conversion:

1. Capture the traffic and note the requested URL.
2. Search the documents being converted for that URL. If a document references it, check the load options of that conversion: `SkipExternalResources` set to `false`, or a `WhitelistedResources` entry that matches it.
3. Check whether the request goes to a licensing endpoint: a metered license, or `GROUPDOCS_LIC_PATH`.
4. Check your connectors and your own loading code.
5. Block egress for the process and repeat the conversion to confirm the source.

If the request comes from GroupDocs.Conversion itself under default options, please report it on the [free support forum](https://forum.groupdocs.com/c/conversion/11).

## More resources

* [Skip loading of external resources]({{< ref "conversion/net/developer-guide/advanced-usage/loading/skip-external-resources.md" >}})
* [Licensing]({{< ref "conversion/net/getting-started/licensing-and-subscription.md" >}})
* [System requirements]({{< ref "conversion/net/getting-started/system-requirements.md" >}})
* [GroupDocs security and customer data](https://about.groupdocs.com/security/customer-data-and-security/)
