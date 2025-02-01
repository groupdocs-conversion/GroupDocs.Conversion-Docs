---
id: save-file-to-stream
url: conversion/java/save-file-to-stream
title: Saving a File to an Output Stream
weight: 4
description: "This article demonstrates how to convert a file and save it as a stream using GroupDocs.Conversion for Java API."
keywords: Convert file to stream, Convert to stream
productName: GroupDocs.Conversion for Java
hideChildren: False
---
To save the conversion results directly to an **OutputStream**, follow these steps:

1.   **Define a Method to Obtain the Output Stream**:
Create a method that returns an OutputStream. This stream will be the destination for the converted file.

2.   **Pass the Output Stream to the** `convert()` **Method**:
Use the output stream as a parameter in the [convert()](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/#convert-com.groupdocs.conversion.contracts.SaveDocumentStream-com.groupdocs.conversion.options.convert.ConvertOptions-) method to direct the converted file to the stream instead of saving it directly to a file.

{{< alert style="note" >}}
This approach is particularly useful when:
- You want to process the converted file in memory without writing it to disk immediately.
- You need to send the file over a network, such as through an HTTP response.
- You are integrating with external systems or APIs that require stream-based file handling.
{{< /alert >}}
The following code snippet demonstrates how to convert a Word document (`.docx`) to a PDF file and save the output to an `OutputStream`:

{{< tabs "code-example">}}
{{< tab "ConvertDocxToPdf.java" >}}  
```java
import java.io.File;
import java.io.FileOutputStream;
import java.io.OutputStream;
import java.util.function.Supplier;
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;

public class ConvertDocxToPdf {
    public static void convert() {
        // Create a supplier that provides the output stream for the converted file
        Supplier<OutputStream> getOutputStream = () -> getFileStream("c:\\files\\business-plan.pdf");

        // Initialize the converter with the source document
        Converter converter = new Converter("c:\\files\\business-plan.docx");

        // Define conversion options (converting to PDF)
        PdfConvertOptions options = new PdfConvertOptions();

        // Pass the output stream to the convert method
        converter.convert(getOutputStream.get(), options);
    }

    // Method to obtain the output stream for the conversion result
    public static OutputStream getFileStream(String outFile) {
        try {
            return new FileOutputStream(new File(outFile));
        } catch (Exception e) {
            e.printStackTrace();
            return null;
        }
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
- **Creating the Output Stream Supplier**:
The `Supplier<OutputStream>` is a functional interface that lazily provides the output stream. This allows flexibility if you need to configure the stream dynamically.
- **Initializing the Converter**:
The `Converter` object is initialized with the source file (`business-plan.docx`).
- **Setting Conversion Options**:
The `PdfConvertOptions` object defines specific options for converting to PDF. You can customize this according to your needs, such as setting the page orientation, margins, or compression.
- **Converting and Writing to the Stream**:
The `convert()` method takes the output stream provided by `getOutputStream.get()` and writes the converted content directly to it. In this case, the PDF file will be saved to `c:\\files\\business-plan.pdf`.
- **Error Handling**:
The `getFileStream()` method includes basic error handling. If an exception occurs while creating the file stream (e.g., due to incorrect file paths or permission issues), the stack trace will be printed, and `null` will be returned.
