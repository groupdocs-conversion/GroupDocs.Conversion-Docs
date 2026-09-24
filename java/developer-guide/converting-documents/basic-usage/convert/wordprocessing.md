
## Convert Word document to PDF

While converting a file from Microsoft Office Word to PDF format, GroupDocs.Conversion for Java performs multiple calculations under the hood to preserve the document's original appearance and to correctly reproduce the layout of the converted PDF document like it was designed for the initial DOC or DOCX document in Microsoft Word. All this is necessary because Word documents are in flow-layout format and their appearance may differ depending on the device and platform that are used for viewing them. On the contrary, PDF format is fixed-layout and has the same appearance on different devices.

The following section explains how to convert DOC or DOCX to PDF programmatically without Microsoft Office and with the help of GroupDocs.Conversion for Java.

### Convert DOCX (or DOC) to PDF

GroupDocs.Conversion provides an easy and concise way to convert DOCX to PDF - all you need is a couple of lines of code to:

1. Load your DOCX document into the `Converter` object by providing a filename with the extension.
2. Invoke the `convert` method of the `Converter` object and specify the desired output format as PDF by passing the `PdfConvertOptions` object to it along with the name of the converted file.

The following code example demonstrates how to convert a document from DOCX into PDF format:

{{< tabs "convert-docx-to-pdf">}}
{{< tab "Java" >}}
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
...
// Load the source DOCX file
Converter converter = new Converter("sample.docx");
// Set the convert options for PDF format
PdfConvertOptions options = new PdfConvertOptions();
// Convert to PDF format
converter.convert("converted.pdf", options);
```
{{< /tab >}}
{{< /tabs >}}

{{< alert style="info" >}}
NOTE: Please be aware that the number of pages in a source document affects the conversion time.
{{< /alert >}}

## Convert Word document to HTML or MHTML

HTML is a very popular web page format as it can be viewed on every device and platform that has a web browser. MHTML format in turn represents a web page archive format that is known as archive format because it saves the web HTML code and associated resources in a single file. These resources include anything linked to the webpage such as images, applets, animations, audio files, and so on. MHTML files can be opened in a variety of applications such as Internet Explorer and Microsoft Word.

Converting Microsoft Word documents to HTML or MHTML formats is a popular and demanded feature of GroupDocs.Conversion. The basic use case of DOCX to HTML conversion could be implemented in several lines of Java code - all you need is to specify the source file name with the extension and call the `convert` method of the `Converter` class passing the name of the target HTML file to it. Please check the complete code snippet below:

{{< tabs "convert-docx-to-html">}}
{{< tab "Java" >}}
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.MarkupConvertOptions;
...
// Load the source DOCX file
Converter converter = new Converter("sample.docx");
// Set the convert options for HTML format
MarkupConvertOptions options = new MarkupConvertOptions();
// Save converted HTML file
converter.convert("converted.html", options);
```
{{< /tab >}}
{{< /tabs >}}

When converting a DOC or DOCX file to MHTML format the only difference from the previous code example is that it is needed to call [MarkupConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/MarkupConvertOptions) `setFormat` method with **MarkupFileType.Mhtml**. The code snippet for DOCX to MHTML conversion will look as follows:

{{< tabs "convert-docx-to-mhtml">}}
{{< tab "Java" >}}
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.MarkupConvertOptions;
import com.groupdocs.conversion.filetypes.MarkupFileType;
...
// Load the source DOCX file
Converter converter = new Converter("sample.docx");
MarkupConvertOptions options = new MarkupConvertOptions();
options.setFormat(MarkupFileType.Mhtml);
// Save converted HTML file
converter.convert("converted.html", options);
```
{{< /tab >}}
{{< /tabs >}}

## Convert Word document to Image

At times you may need to get images of DOC or DOCX document pages - it may be useful as a faster and therefore more efficient substitution for physical document scanning, when creating document pages previews for your website or application, or when trying to show your documents to someone who hasn’t Microsoft Word installed on their workstation. Then the solution is to convert a document into JPG, PNG, TIFF or any other supported image format (see the full list of [available conversions](#supported-word-processing-file-conversions)).

Similarly to other code examples that were explained already, all you need to convert a Word document to an image is to load the source DOC/DOCX file into the `Converter` object and call the `convert` method. The only difference is that every page from the source Word document will be saved as a separate image file, so it is required to specify the naming format for output images (page numbers will be set on the fly).

Please check the complete code example of how to convert DOCX to PNG below:

{{< tabs "convert-docx-to-png">}}
{{< tab "Java" >}}
```java
import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.contracts.SavePageStream;
import com.groupdocs.conversion.options.convert.ImageConvertOptions;
import com.groupdocs.conversion.filetypes.ImageFileType;
...
String outputFileNameFormat = "converted-page-%s.png";
SavePageStream getPageStream = page => new FileOutputStream(String.format(outputFileNameFormat, page));

// Load the source DOCX file
Converter converter = new Converter("sample.docx");
// Set the convert options for PNG format
ImageConvertOptions options = new ImageConvertOptions();
options.setFormat(ImageFileType.Png);  
// Convert to PNG format
converter.convert(getPageStream, options);
```
{{< /tab >}}
{{< /tabs >}}

## Convert Word document to Markdown

Markdown format gained popularity among developers because of its versatility - while it is used for writing programs description and documentation, its structure is quite simple and plain so it is good for transforming to PDF, HTML, DOCX and other formats.
GroupDocs.Conversion allows you to convert Microsoft Word documents to markdown files with ".md" extension without too much effort. Let’s see how to convert DOCX to MD using Java programming language.

{{< tabs "convert-docx-to-markdown">}}
{{< tab "Java" >}}
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.WordProcessingConvertOptions;
import com.groupdocs.conversion.filetypes.WordProcessingFileType;
...
// Load the source DOCX file
Converter converter = new Converter("sample.docx");
WordProcessingConvertOptions options = new WordProcessingConvertOptions();
options.setFormat(WordProcessingFileType.Md);
// Save converted TXT file
converter.convert("converted.md", options);
```
{{< /tab >}}
{{< /tabs >}}

So again - all you need to do for a quick convert with GroupDocs.Conversion for Java is to - load the source Word document into the `Converter` class and call the `convert` method to save the converted file. That’s it!
