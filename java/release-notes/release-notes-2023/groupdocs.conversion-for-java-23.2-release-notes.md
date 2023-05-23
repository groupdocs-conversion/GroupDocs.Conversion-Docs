---
id: groupdocs-conversion-for-java-23-2-release-notes
url: conversion/java/groupdocs-conversion-for-java-23-2-release-notes
title: GroupDocs.Conversion for Java 23.2 Release Notes
weight: 30
description: ""
keywords:
productName: GroupDocs.Conversion for Java
hideChildren: False
---
{{< alert style="info" >}}This page contains release notes for GroupDocs.Conversion for Java 23.2{{< /alert >}}

## Major Features

There are 10+ features, improvements and bug-fixes in this release, the most notable are:

* Conversion from Amazon Kindle AZW3 format
* New load option to keep original date field value when converting from wordprocessing document
* Improved Pdf to JPEG/TIFF conversions
* Improved DOCX to MD conversions
* Improved PDF to DOCX conversions
* Improved conversions from PostScript files

## Full List of Issues Covering all Changes in this Release

| Key                 | Category | Summary                                                        |
|---------------------| --- |----------------------------------------------------------------|
| CONVERSIONNET&#8209;5429  | Feature | Conversion from Amazon Kindle AZW3 format |
| CONVERSIONNET&#8209;5433  | Enhancement | New load option to keep original date field value when converting from wordprocessing document |
| CONVERSIONNET&#8209;5466  | Enhancement | Incorrect detection of password protected spreadsheet document when loaded from stream |
| CONVERSIONNET&#8209;5416  | Fix | Comments still visible despite using HideComments when converting DOCX to PDF |
| CONVERSIONNET&#8209;5419  | Fix | File damaged or corrupt |
| CONVERSIONNET&#8209;5394  | Fix | Cannot convert from multipage TIFF when the source filename extension is "tif" |
| CONVERSIONNET&#8209;5393  | Fix | For a presentation file the value of IsPasswordProtected property is not in PropertiesNames of IDocumentInfo |
| CONVERSIONNET&#8209;5237  | Fix | PDF to JPEG/TIFF conversion problem |
| CONVERSIONNET&#8209;5370  | Fix | HTML to PDF conversion issue |
| CONVERSIONNET&#8209;5313  | Fix | DOCX to PDF conversion issue on Red Hat |
| CONVERSIONNET&#8209;5406  | Fix | DOCX to MD to HTML: Missing formatting |
| CONVERSIONNET&#8209;5455  | Fix | Evaluation tag when converting PDF to Image on Linux/MacOS |
| CONVERSIONNET&#8209;5456  | Fix | DOCX to PDF conversion: bullets list converted to squares |
| CONVERSIONNET&#8209;5494  | Fix | Particular Excel to PDF conversion - Blank output |
| CONVERSIONNET&#8209;5405  | Fix | DOCX to MD: Unhandled exception |
| CONVERSIONNET&#8209;5564  | Fix | Converting to image may produce larger file size than expected |
| CONVERSIONNET&#8209;5470  | Fix | PDF to JPG - Large File Size of Converted Images |
| CONVERSIONNET&#8209;5299  | Fix | Page orientation issue when converting from DWG to PDF |
| CONVERSIONNET&#8209;4719  | Fix | Exception `Parameter is not valid.` when converting DOCX to PPT using license file |
| CONVERSIONNET&#8209;4796  | Fix | PDF to DOCX - malformed output |
| CONVERSIONNET&#8209;4122  | Fix | PostScript files are converted to a single blank page |
| CONVERSIONNET&#8209;5518  | Fix | Object reference not set to an instance of an object exception when converting PDF to DOCX with fluent syntax |
| CONVERSIONJAVA&#8209;1676 | Fix | Issue in ConverterSettings Cache implementations |
| CONVERSIONJAVA&#8209;1861 | Fix | MD to PDF conversion issue |
| CONVERSIONJAVA&#8209;1870 | Fix | Fix conversion context input stream issue |
| CONVERSIONJAVA&#8209;1882 | Fix | Saving complete multi page document to image is not supported |


## Public API and Backward Incompatible Changes

1.  **Introduced new property in class WordProcessingLoadOptions**

    ```java
    /**
    * Keep original value of date field. Default: false
    */
    public boolean isKeepDateFieldOriginalValue();
    
    public void setKeepDateFieldOriginalValue(boolean keepDateFieldOriginalValue);
    ```
    