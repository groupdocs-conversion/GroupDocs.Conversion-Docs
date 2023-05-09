---
id: groupdocs-conversion-for-java-23-4-release-notes
url: conversion/java/groupdocs-conversion-for-java-23-4-release-notes
title: GroupDocs.Conversion for Java 23.4 Release Notes
weight: 26
description: ""
keywords:
productName: GroupDocs.Conversion for Java
hideChildren: False
---
{{< alert style="info" >}}This page contains release notes for GroupDocs.Conversion for Java 23.4{{< /alert >}}

## Major Features

There are 10+ features, improvements and bug-fixes in this release, most notable are:

* Conversion from PUB (Microsoft Publisher) file format to PDF format
* Improved performance of PDF to XLSM conversion
* Conversion to AZW3 format
* Options to extract audio from video
* Improved document types classification
* Improved conversion from composite documents
* Conversions between font formats
* Improved conversions from ICO format
* Improved spreadsheet to wordprocessing document conversions
* Improved logging during conversion
* Conversions to MOBI format.
* New load options when converting spreadsheets - Specify desired sheets by their index number.
* Improved file type detection from a stream

## Full List of Issues Covering all Changes in this Release

| Key                 | Category | Summary                                                        |
|---------------------| --- |----------------------------------------------------------------|
| CONVERSIONNET&#8209;5257 | Feature | .PUB file to PDF conversion support |
| CONVERSIONNET&#8209;5527 | Feature | Change the producer of PDF file |
| CONVERSIONNET&#8209;5432 | Feature | [Implement conversion to Amazon Kindle AZW3 format](#conversion-to-azw3-format) |
| CONVERSIONNET&#8209;5643 | Feature | [Video to Audio conversion](#extracting-audio-track-from-video-formats) |
| CONVERSIONNET&#8209;5407 | Feature | [Implemented font formats conversion](#conversion-between-font-formats) |
| CONVERSIONNET&#8209;5803 | Feature | [Implement conversion to MOBI format](#conversion-to-mobi-format)|
| CONVERSIONNET&#8209;5833 | Feature | [Specify converted worksheets by indexes](#specify-converted-worksheets-by-their-indexes)|
| CONVERSIONNET&#8209;5414 | Enhancement | Conversion from PDF to XLSM is freezing |
| CONVERSIONNET&#8209;5700 | Enhancement | Improved conversions from composite documents: PST/OST, MBOX, and archives |
| CONVERSIONNET&#8209;5517 | Enhancement | Improved document types classification following the [File Format Guide](https://docs.fileformat.com) |
| CONVERSIONNET&#8209;5746 | Enhancement | Improve Ico format conversion |
| CONVERSIONNET&#8209;5748 | Enhancement | Improve Spreadsheet to WordProcessing document conversion |
| CONVERSIONNET&#8209;5724 | Enhancement | Return list of available folders from PST/OST and other composite documents in document info class |
| CONVERSIONNET&#8209;5750 | Enhancement | Improve Spreadsheet to Presentation document conversion |
| CONVERSIONNET&#8209;5732 | Enhancement | EML with attachments to PDF conversion issue |
| CONVERSIONNET&#8209;5761 | Enhancement | Improve logging during conversion |
| CONVERSIONNET&#8209;5837 | Enhancement | Do not process hidden worksheets when convert from spreadsheet |
| CONVERSIONNET&#8209;5825 | Enhancement | Improve FileType from Stream detection |
| CONVERSIONNET&#8209;5808 | Enhancement | Return meaningful data in DocumentInfo classes that have IEnumerable properties when accessed through the indexer |
| CONVERSIONNET&#8209;5609 | Fix | Large temp files are created during conversion to image on macOS |
| CONVERSIONNET&#8209;4976 | Fix | Cannot convert PDF to Excel |
| CONVERSIONNET&#8209;5558 | Fix | Error converting WEBP to JPG |
| CONVERSIONNET&#8209;5234 | Fix | Cannot convert ASE to 3DS and OBJ |
| CONVERSIONNET&#8209;5233 | Fix | Cannot convert from 3D VRML file format |
| CONVERSIONNET&#8209;5232 | Fix | Cannot convert from 3D X file format |
| CONVERSIONNET&#8209;5231 | Fix | Cannot convert from 3D GLTF file format |
| CONVERSIONNET&#8209;5726 | Fix | When converting from PST/OST no files are processed |
| CONVERSIONNET&#8209;5560 | Fix | Keeping the hyperlink (text with link) format when converting PDF to PPTX |
| CONVERSIONNET&#8209;4742 | Fix | PDF to image conversion issue |
| CONVERSIONNET&#8209;5415 | Fix | Evaluation tag when converting to Image |
| CONVERSIONNET&#8209;5457 | Fix | Particular PDF to PNG conversion crashes |
| CONVERSIONNET&#8209;5563 | Fix | PDF to PNG: Path conversion requested exception |
| CONVERSIONNET&#8209;5280 | Fix | Word to PDF conversion issue |
| CONVERSIONNET&#8209;5736 | Fix | Converter.GetAllPossibleConversions method returns enum with duplicates |
| CONVERSIONNET&#8209;5477 | Fix | Regression: EPUB to HTML raises "CorruptOrDamagedFileException" |
| CONVERSIONNET&#8209;5698 | Fix | Cannot convert from Note on macOS due to missing fonts |
| CONVERSIONNET&#8209;5831 | Fix | Error while Converting XLSX to PDF: Same key added |
| CONVERSIONNET&#8209;5823 | Fix | Converting Numbers to Pptx produce broken result |
| CONVERSIONNET&#8209;5794 | Fix | Converting particular Xlsx to Pptx produce broken result |
| CONVERSIONNET&#8209;5341 | Fix | DWG to PDF conversion - Its messing the image |
| CONVERSIONNET&#8209;5835 | Fix | XSLX to PDF: #REF! instead of 0 |
| CONVERSIONNET&#8209;5836 | Fix | XLS to PDF: ConversionNotSupportedException |


### Conversion to AZW3 format
To convert any of the supported file types to the AZW3 file type, just specify it in the `Format` property of the [`EBookConvertOptions`](https://reference.groupdocs.com/conversion/java/groupdocs.conversion.options.convert/ebookconvertoptions/) class instance:

```java
// Load the source PDF file
try (Converter converter = new Converter("sample.pdf")) {
    // Set the convert options for AZW3 format
    EBookConvertOptions options = new EBookConvertOptions();
    options.setFormat(EBookFileType.Azw3);
    // Convert to AZW3 format
    converter.convert("converted.azw3", options);
}
```

### Extracting audio track from video formats
Extracting audio track from video is similar to [converting video]({{< ref "conversion/java/developer-guide/basic-usage/convert/video.md" >}}), however you need to set the [`ExtractAudioOnly`](https://reference.groupdocs.com/conversion/java/groupdocs.conversion.options.convert/videoconvertoptions/extractaudioonly/) property to `true` and specify the desired output format in the [`AudioFormat`](https://reference.groupdocs.com/conversion/java/groupdocs.conversion.options.convert/videoconvertoptions/audioformat/) property:

```java
// Load the source AVI file
VideoLoadOptions loadOptions = new VideoLoadOptions();
loadOptions.setVideoConnector(new VideoConnector());
try(Converter converter = new Converter("sample_with_audio.avi", () -> loadOptions)){
  // Set the convert options
  VideoConvertOptions options = new VideoConvertOptions();
  options.setExtractAudioOnly(true);
  options.setAudioFormat(AudioFileType.Ogg);
  // Convert to audio file
  converter.convert("extracted_audio.ogg", options);
}

```

### Conversion between font formats
Now you can [convert your font file]({{< ref "conversion/java/developer-guide/basic-usage/convert/font" >}}) from one format into another.
For example CFF to TTF conversion code snippet will look like this:

```java

// Load the source font file
try (Converter converter = new Converter("Lato-Regular.cff")) {
  // Set the convert options
  FontConvertOptions options = new FontConvertOptions
  options.setFormat(FontFileType.Ttf);
  // Convert to TTF format
  converter.convert("Lato-Regular.ttf", options);
}
```

### Conversion to MOBI format
To convert any of the supported file types to the MOBI file type, just specify it in the `Format` property of the [`EBookConvertOptions`](https://reference.groupdocs.com/conversion/java/groupdocs.conversion.options.convert/ebookconvertoptions/) class instance:

```java
// Load the source PDF file
try (Converter converter = new Converter("sample.pdf")) {
  // Set the convert options for MOBI format
  EBookConvertOptions options = new EBookConvertOptions();
  options.setFormat(EBookFileType.Mobi);
  // Convert to MOBI format
  converter.convert("converted.mobi", options);
}
```

### Specify converted worksheets by their indexes
When [converting spreadsheets]({{< ref "conversion/java/developer-guide/advanced-usage/loading/load-options-for-different-document-types/load-spreadsheet-document-with-options.md" >}}), you can now specify the desired sheets by their zero-based index numbers. To do this use the `SheetIndexes` property of the [SpreadsheetLoadOptions](https://reference.groupdocs.com/conversion/java/groupdocs.conversion.options.load/spreadsheetloadoptions) class:

```java
LoadOptionsProvider getLoadOptions = () -> {
  SpreadsheetLoadOptions options = new SpreadsheetLoadOptions();
  options.setSheetIndexes(Arrays.asList(0, 2));
  options.setOnePagePerSheet(true);
  return options;
};
try (Converter converter = new Converter("sample.xlsx", getLoadOptions)) {
  PdfConvertOptions options = new PdfConvertOptions();
  converter.convert("converted.pdf", options);
}
```

## Public API and backward incompatible changes

1. Introduced a new file type: [`WebFileType`](https://reference.groupdocs.com/conversion/java/groupdocs.conversion.filetypes/webfiletype/).
2. The `PersonalStorageFileType` file type becomes deprecated. Please use the [`EmailFileType`](https://reference.groupdocs.com/conversion/java/groupdocs.conversion.filetypes/emailfiletype/) or the [`DatabaseFileType`](https://reference.groupdocs.com/conversion/java/groupdocs.conversion.filetypes/databasefiletype/) types instead.
3. The `MarkupFileType` file type becomes deprecated. Please use the  [`WebFileType`](https://reference.groupdocs.com/conversion/java/groupdocs.conversion.filetypes/webfiletype/) type instead.
4. The `DataFileType` file type becomes deprecated. Please use the  [`WebFileType`](https://reference.groupdocs.com/conversion/java/groupdocs.conversion.filetypes/webfiletype/) type instead.
5. Introduced new [`ExtractAudioOnly`](https://reference.groupdocs.com/conversion/java/groupdocs.conversion.options.convert/videoconvertoptions/extractaudioonly/) property of the `VideoConvertOptions` class.
6. Introduced new [`AudioFormat`](https://reference.groupdocs.com/conversion/java/groupdocs.conversion.options.convert/videoconvertoptions/audioformat/) property of the `VideoConvertOptions` class.
7. Introduced new `PersonalStorageFolderInfo` class:

```java
//Personal Storage Folder info

public class PersonalStorageFolderInfo {

  //Name of the folder

  public String  getName();

  //Count of the items in the folder

  public int getItemsCount();

}
```

8. Changed the `Folders` property  in the `PersonalStorageDocumentInfo` class:

    before v23.4

```java
    public List<String> getFolders();
 ```

    from v23.4 and greater

```java
    public List<PersonalStorageFolderInfo> getFolders();
```

9. Introduced new `SheetIndexes` property of the `SpreadsheetLoadOptions` class:

```java
   /**
   * List of sheet indexes to convert.
   * The indexes must be zero-based
   */
   public List<Integer> getSheetIndexes();
   public void getSheetIndexes(List<Integer> indexes);
```