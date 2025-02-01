---
id: save-file-to-local-disk
url: conversion/java/save-file-to-local-disk
title: Saving a File to Local Disk
weight: 1
description: "This article demonstrates how to convert files stored on local disk using GroupDocs.Conversion for Java API."
keywords: Convert local file, Convert file
productName: GroupDocs.Conversion for Java
hideChildren: False
---
To save the conversion results to a local disk, you can use the [convert(String filePath, ConvertOptions convertOptions)](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/#convert-java.lang.String-com.groupdocs.conversion.options.convert.ConvertOptions-) method. This implementation requires two parameters:

- `filePath` – The path where the output file will be saved. It can be an **absolute path** (e.g., *C:\\files\\converted.pdf)* or a **relative path** (e.g., *converted.pdf*).
- `convertOptions` – Options specifying the conversion settings, such as the output format or specific configurations related to the conversion process.

{{< alert style="note" >}}
- If the specified output file does not exist, it will be automatically created.
- If the file already exists, it may be overwritten unless specified otherwise in the options.
{{< /alert >}}

The following code snippet demonstrates how to convert a Word document (`.docx`) to a PDF file and save it to a specified directory on your local disk:

{{< tabs "code-example">}}
{{< tab "ConvertDocxToPdf.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;

public class ConvertDocxToPdf {
    public static void convert() {
        // Specify the source file location
        Converter converter = new Converter("c:\\files\\business-plan.docx");
        
        // Define conversion options (in this case, converting to PDF)
        PdfConvertOptions options = new PdfConvertOptions();
    
        // Specify the output file location and perform the conversion
        converter.convert("c:\\files\\business-plan.pdf", options);
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "business-plan.docx" >}}  
{{< tab-text >}}
`business-plan.docx` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/save-file-to-local-disk/business-plan.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "business-plan.pdf" >}}  
{{< tab-text >}}
`business-plan.pdf` is converted PDF document. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/save-file-to-local-disk/business-plan.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

### Explanation:
- **Source File Specification**:
The `Converter` object is initialized with the path to the source document (`business-plan.docx`).
- **Conversion Options**:
The `PdfConvertOptions` object is created to configure settings specific to PDF conversion. Depending on the library you are using, you may have options to customize aspects such as page size, orientation, or compression.
- **Saving the Converted File**:
The `convert()` method is called with the desired output file path (`c:\\files\\business-plan.pdf`) and the conversion options (`options`). The file will be saved in the specified directory.