---
id: common-conversion-options
url: conversion/java/common-conversion-options
title: Common conversion options
weight: 1
description: "This documentation sections describe how to customize document conversion process - convert specific document pages, apply watermarks etc. when using GroupDocs.Conversion for Java."
keywords: customize document conversion, how to customize document conversion process, convert specific document pages, apply watermarks
productName: GroupDocs.Conversion for Java
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) has many different [**ConvertOptions**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/ConvertOptions) which gives control over required conversion result. All [**ConvertOptions**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/ConvertOptions) have some common properties which are:

*   [**PageNumber**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/IPagedConvertOptions#setPageNumber(int)) specifies the page number from which the conversion should start from.
*   [**PagesCount**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/IPagedConvertOptions#setPagesCount(int)) specifies the number of pages to be converted.
*   [**Pages**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/IPageRangedConvertOptions#setPages(java.util.List)) is a list of specific page number to be converted.
*   [**Watermark**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/IWatermarkedConvertOptions#setWatermark(com.groupdocs.conversion.options.convert.WatermarkOptions)) sets watermark options.

The samples below shows how each of these options could be used:
