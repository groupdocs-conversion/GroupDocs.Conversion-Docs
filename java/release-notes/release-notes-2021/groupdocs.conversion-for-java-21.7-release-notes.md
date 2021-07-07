---
id: groupdocs-conversion-for-java-21-7-release-notes
url: conversion/java/groupdocs-conversion-for-java-21-7-release-notes
title: GroupDocs.Conversion for Java 21.7 Release Notes
weight: 12
description: ""
keywords:
productName: GroupDocs.Conversion for Java
hideChildren: False
---
{{< alert style="info" >}}This page contains release notes for GroupDocs.Conversion for Java 21.7{{< /alert >}}
## Major Features

There are 20+ features, improvements and bug-fixes in this release, most notable are:

*   Conversions from/to Tga
*   Specified watermark font style (bold, italic) now respected
*   Fixed issue with custom fonts folders
*   Diagram to diagram conversion
*   Project management to project management conversion
*   CSV to Json conversion
*   Conversion from Json as a datasource
*   Conversion from Fodg
*   Conversion from/to Psb
*   Improved Email to Html conversion



## Full List of Issues Covering all Changes in this Release

| Key | Category | Summary |
| --- | --- | --- |
| CONVERSIONNET-4509 | Feature | Csv to Json conversions |
| CONVERSIONNET-4510 | Feature | Conversion from Json as datasource |
| CONVERSIONNET-4554 | Feature | Override the source file type detection by setting Format property in LoadOptions |
| CONVERSIONNET-4595 | Feature | Implement Diagram to Diagram conversion |
| CONVERSIONNET-4614 | Feature | Implement conversion from Primavera Xer |
| CONVERSIONNET-4615 | Feature | Implement ProjectManagement to ProjectManagement conversion |
| CONVERSIONNET-4624 | Feature | Implement conversion from Apple iWork Numbers format |
| CONVERSIONNET-4626 | Feature | Implement conversion from/to Psb |
| CONVERSIONNET-4632 | Feature | Implement conversion from Fodg |
| CONVERSIONNET-4567 | Improvement | Improve Email to Markup conversion |
| CONVERSIONNET-4521 | Feature | Implement conversion from/to Tga |
| CONVERSIONNET-1785 | Bug | Docx to PDF conversion characters issue |
| CONVERSIONNET-4489 | Bug | Improper conversion from Mbox |
| CONVERSIONNET-4493 | Bug | Options equality comparison not working properly when the class contains arrays |
| CONVERSIONNET-4519 | Bug | Exception when trying to convert WordML document stream to PDF |
| CONVERSIONNET-4546 | Bug | Converting using ConverterSettings.FontDirectories |
| CONVERSIONNET-4549 | Bug | Watermark font styles not respected when converting to PDF |
| CONVERSIONNET-4571 | Bug | Wordprocessing conversion issue under linux and windows core |
| CONVERSIONNET-3819 | Bug | Conversion from XPS to PDF throws OOM or uses too much memory and lasts for 5 minutes |
| CONVERSIONNET-4200 | Bug | Exception is thrown when converting particular Cdr document |
| CONVERSIONNET-4312 | Bug | Cannot convert particular EMF to PDF document |
| CONVERSIONNET-4321 | Bug | Tif to Svg conversion issue |
| CONVERSIONNET-4337 | Bug | Unable to convert particular Gif |
| CONVERSIONNET-4434 | Bug | Html to XLS conversion exception: The max length of the font name is 31 |
| CONVERSIONNET-4566 | Bug | Html improperly detected as Mbox when converting from stream |
| CONVERSIONNET-4568 | Bug | Missing watermark when converting from Email |
| CONVERSIONNET-4635 | Bug | Conversion from Pst/Ost do not produce output documents |
/ CONVERSIONJAVA-1328/ Bug / Convert email with attachment to PDF
/ CONVERSIONJAVA-1349/ Bug / Word to PDF conversion - formatting issue

## Public API and Backward Incompatible Changes

1.  **Introduced new property in class WordProcessingLoadOptions**

    ```java
    /**
    * Specifies whether to use a text shaper for better kerning display. Default is false.
    */ 
    public boolean isUseTextShaper();
    
    public void setUseTextShaper(boolean isUseTextShaper)
    ```
2.  **Introduced new class DataConvertOptions**
3.  **Introduced new class DiagramConvertOptions**
4.  **Introduced new class ProjectManagementConvertOptions**
5.  **Introduced new class DataLoadOptions**
6.  **Introduced new property in class XmlLoadOptions**

    ```java
    /**
    * Use Xml document as data source
    */
    public boolean isUseAsDataSource();
    
    public void setUseAsDataSource(boolean useAsDataSource);
    ```
