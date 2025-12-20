---
id: how-to-run-examples
url: conversion/net/how-to-run-examples
title: How to run examples
weight: 7
description: "This article describes how to run .NET file conversion API code examples."
keywords: file conversion, C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: true
---
<!--
{{< alert style="warning" >}}Before running an example make sure that GroupDocs.Conversion has been installed successfully.{{< /alert >}}

This article describes how to run .NET file conversion API code examples.
-->
We offer multiple solutions on how you can run GroupDocs.Conversion examples, by building your own or using our back-end or front-end examples.

<!--Please choose one from the following list:-->

## Build a project from scratch

You can build a project from scratch using Visual Studio or [.NET CLI](https://docs.microsoft.com/en-us/dotnet/core/tools/). We'll step you through both cases.

### Build a project using .NET CLI

This method applies to .NET 6+ projects.

1. Make sure you have .NET SDK installed <https://dotnet.microsoft.com/download>.
2. Create a directory for your console app by executing the `mkdir my-console-app` command in your terminal.
3. Navigate to the `my-console-app` directory by executing the `cd my-console-app` command.
4. Create an empty console app by executing the `dotnet new console` command.
5. Add the GroupDocs.Conversion for .NET package by executing the `dotnet add package GroupDocs.Conversion` command.
6. Edit `Program.cs` and add the following lines to the `Main` method:
  
  ```csharp
    using GroupDocs.Conversion;
	using GroupDocs.Conversion.Options.Convert;

    string documentPath = @"C:\sample.docx"; // NOTE: Put here actual path for your document
    string outputPath = @"C:\output\converted.pdf";
  
    using (Converter converter = new Converter(documentPath))
    {
        PdfConvertOptions convertOptions = new PdfConvertOptions();
        converter.Convert(outputPath, convertOptions);
    }
  ```
  
7. Replace the `documentPath` value with the actual path to the document you're going to convert.
8. Run the project by executing the `dotnet run` command.
9. The converted document will be saved in the `C:\\output\\` directory.

### Build a project using Visual Studio

This method applies to both .NET 6+ and .NET Framework 4.6.2+ projects.

1. Open Visual Studio and go to **File** -> **New** -> **Project**.
2. Select the appropriate project type - Console App, ASP.NET Web Application etc.
3. Install the appropriate **GroupDocs.Conversion** NuGet package for your target framework:
   * [GroupDocs.Conversion](https://www.nuget.org/packages/GroupDocs.Conversion) - for .NET 6+
   * [GroupDocs.Conversion.NETFramework](https://www.nuget.org/packages/GroupDocs.Conversion.NETFramework) - for .NET Framework 4.6.2+

   For detailed installation instructions, see the [Installation guide]({{< ref "conversion/net/getting-started/installation.md" >}}).
4. Add the following code to the `Main` method:

  ```csharp
    using GroupDocs.Conversion;
	using GroupDocs.Conversion.Options.Convert;

    string documentPath = @"C:\sample.docx"; // NOTE: Put here actual path for your document
    string outputPath = @"C:\output\converted.pdf";
  
    using (Converter converter = new Converter(documentPath))
    {
        PdfConvertOptions convertOptions = new PdfConvertOptions();
        converter.Convert(outputPath, convertOptions);
    }
  ```

5. Replace the `documentPath` value with the actual path to the document you're going to convert.
6. Build and Run your project.
7. The converted document will be saved in the `C:\\output\\` directory.

## Run back-end examples

You can find many back-end examples in our [GitHub](https://github.com/groupdocs-conversion/GroupDocs.Conversion-for-.NET) repository. You can either download the ZIP file from [here](https://github.com/groupdocs-conversion/GroupDocs.Conversion-for-.NET/archive/master.zip) or clone the repository from GitHub using your favorite Git client.  
In case you download the ZIP file, extract the folders on your local disk.

1. Navigate to the `Examples` directory and open the `GroupDocs.Conversion.Examples.CSharp.sln` solution using Visual Studio.
2. Open the `RunExamples.cs` file and uncomment the example(s) that you would like to run.
3. Optionally, you can set the path to the license in `Utils.cs` file.

## Run demo projects

To run any demo from [GroupDocs.Conversion for .NET Demo projects](https://github.com/groupdocs-conversion/GroupDocs.Conversion-for-.NET/tree/master/Demos/), you can either:

* Clone the repository:

  ```bash
  git clone git@github.com:groupdocs-conversion/GroupDocs.Conversion-for-.NET.git  
  ```

* or [download](https://github.com/groupdocs-conversion/GroupDocs.Conversion-for-.NET/archive/master.zip) the source code.

### ASP.NET MVC demo

1. Clone or download the [GroupDocs.Conversion-for-.NET](https://github.com/groupdocs-conversion/GroupDocs.Conversion-for-.NET) repository from GitHub or skip this step if you already have the code.
2. Navigate to the `Demos/MVC` directory.
3. Open the `GroupDocs.Conversion.MVC.sln` solution using Visual Studio.
4. Update common parameters in the `**web.config**` file and demo-related properties in the `**configuration.yml**` file to meet your requirements.
<!--
 see more about configuring the demo at ["Configuration"](https://github.com/groupdocs-conversion/GroupDocs.Conversion-for-.NET/tree/master/Demos/MVC#configuration) section. -->
5. Run the project and open [http://localhost:8080/conversion](http://localhost:8080/conversion) in your favorite browser.
<!--
{{< alert style="info" >}}

For more details about demo configuration please refer to ["Configuration"](https://github.com/groupdocs-conversion/GroupDocs.Conversion-for-.NET/tree/master/Demos/MVC#configuration) section.

{{< /alert >}}
-->
### ASP.NET Web Forms demo

1. Clone or download the [GroupDocs.Conversion-for-.NET](https://github.com/groupdocs-conversion/GroupDocs.Conversion-for-.NET) repository from GitHub or skip this step if you already have the code.
2. Navigate to `Demos/WebForms` directory.
3. Open the `GroupDocs.Conversion.WebForms.sln` solution using Visual Studio.
4. Update common parameters in the `**web.config**` file and demo-related properties in the `**configuration.yml**` file to meet your requirements.
5. Open [http://localhost:8080/conversion](http://localhost:8080/conversion) in your favorite browser.

<!--
{{< alert style="info" >}}

For more details about demo configuration please refer to ["Configuration"](https://github.com/groupdocs-conversion/GroupDocs.Conversion-for-.NET/tree/master/Demos/WebForms#configuration) section.

{{< /alert >}}
-->
### Docker demo

Use the [Docker](https://www.docker.com/) image to try GroupDocs.Conversion for .NET features in an easy way. Here are the commands to run GroupDocs.Conversion for .NET from the Docker image.

```bash
mkdir DocumentSamples
mkdir Licenses
docker run -p 8080:8080 --env application.hostAddress=localhost  \
    -v `pwd`/DocumentSamples:/home/groupdocs/app/DocumentSamples  \
    -v `pwd`/Licenses:/home/groupdocs/app/Licenses  \
    groupdocs/conversion
## Open http://localhost:8080/conversion in your favorite browser.
```

## Contribute

If you like to add or improve an example, we encourage you to contribute to the project. All examples in this repository are open source and can be freely used in your own applications.  
To contribute, you can fork the repository, edit the code and create a pull request. We will review the changes and include them in the repository if found helpful.
