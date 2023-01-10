---
id: groupdocs-conversion-for-java-22-11-release-notes
url: conversion/java/groupdocs-conversion-for-java-22-11-release-notes
title: GroupDocs.Conversion for Java 22.11 Release Notes
weight: 20
description: ""
keywords:
productName: GroupDocs.Conversion for Java
hideChildren: False
---
{{< alert style="info" >}}This page contains release notes for GroupDocs.Conversion for Java 22.11{{< /alert >}}

## Major Features

There are 5+ features, improvements and bug-fixes in this release, most notable are:

* Audio conversions
* Video conversions
* Add option to set custom font folders when converting from CAD
* Converting HTML/RTF to Image format by setting its transparency
* HTML to PDF conversion improvements
* Keeping original image resolution when converting WordProcessing documents to Pdf

## Full List of Issues Covering all Changes in this Release

| Key                 | Category | Summary                                                        |
|---------------------| --- |----------------------------------------------------------------|
| CONVERSIONNET-5094 | Feature | Set background color when convert from CAD |
| CONVERSIONNET-5095 | Feature | Set draw type when converting from CAD |
| CONVERSIONNET-5096 | Feature | Implement fixed size conversion from CAD when no CadLoadOptions.Width and CarLoadOptions.Height is set |
| CONVERSIONNET-5137 | Feature | Implement Audio conversion |
| CONVERSIONNET-5147 | Feature | Implement Video conversion |
| CONVERSIONNET-5252 | Improvement | Implement setting custom font folders when converting from CAD |
| CONVERSIONNET-4012 | Enhancement | Converting HTML/RTF to Image format by setting its transparency |
| CONVERSIONNET-4943 | Bug | Word table formatting issue using Customer XML data |
| CONVERSIONNET-5187 | Bug | Getting document info of a particular PSD raises exception |
| CONVERSIONNET-4314 | Bug | Converting particular DWFX to PDF produce empty result file |
| CONVERSIONNET-5279 | Bug | Converted MD to HTM file displayed as plain text |
| CONVERSIONNET-4818 | Bug | Exception - Object reference not set |
| CONVERSIONNET-5372 | Bug | Some conversions to Odp, Otp and Fodp throwing exception |
| CONVERSIONNET-5371 | Bug | Exception: 'IBM437' is not a supported encoding name. |
| CONVERSIONNET-4705 | Bug | HTML to PDF conversion - empty result |
| CONVERSIONNET-5343 | Bug | A pdf is reported as password protected but it is not |
| CONVERSIONNET-4430 | Bug | Pdf to Docx conversion exception: An attempt to create annotation using invalid dictionary. |
| CONVERSIONNET-4423 | Bug | PDF to PPTX conversion issue |
| CONVERSIONNET-5349 | Bug | Jpeg not converted properly to Presentation |
| CONVERSIONNET-4319 | Bug | JPG to PPT conversion issue |
| CONVERSIONNET-4316 | Bug | Failed to convert particular PSD |
| CONVERSIONNET-4149 | Bug | DWG to WMF conversion issue |
| CONVERSIONNET-3427 | Bug | .NET Core MacOS cannot convert PDF to Tiff |
| CONVERSIONNET-3805 | Bug | PSD to PPT/PPTX conversion issue |
| CONVERSIONNET-3853 | Bug | PDF to PPT conversion issue |
| CONVERSIONNET-3896 | Bug | Wrong anchor navigation in converted document  |
| CONVERSIONNET-4258 | Bug | Cannot convert Pdf to Pptx |
| CONVERSIONNET-5342 | Bug | WordProcessing documents having images with resolution higher than 220dpi are downscaled to 220dpi when converting to Pdf |
| CONVERSIONJAVA-1788 | Investigation | Decrease the size of Jar |

## Public API and Backward Incompatible Changes

1. Introduced **IAudioConnector** interface\

    ```java
    /**
    * Defines methods that are required to convert audio to audio documents.
    */
    public interface IAudioConnector
    {
       /**
       * Does the Audio conversion provided as a stream.
       *
       * @param sourceStream   Stream, containing an audio to process
       * @param convertOptions Audio convert options
       * @return Converted audio
       */
      Stream convertAudio(Stream sourceStream, AudioConvertOptions convertOptions);

    }
    ```
2. Introduced **AudioConvertOptions** class
3. Introduced **AudioLoadOptions** class
4. Introduced **IVideoConnector** interface\

    ```java
    /**
    * Defines methods that are required to convert video documents.
    */
    public interface IVideoConnector {
      /**
      * Does the Video conversion provided as a stream.
      *
      * @param sourceStream   Stream, containing an video to process
      * @param convertOptions Video convert options
      * @return Converted video
      */
      Stream convertVideo(Stream sourceStream, VideoConvertOptions convertOptions);
    }
    ```
5. Introduced **VideoConvertOptions** class
6. Introduced **VideoLoadOptions** class