---
id: installation
url: conversion/net/installation
title: Install GroupDocs.Conversion for .NET
linkTitle: Installation
weight: 4
description: "This guide explains how to install GroupDocs.Conversion for .NET to your environment"
keywords: 
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

This topic describes how to add the **GroupDocs.Conversion** library to your .NET project. You can use a NuGet package to install this library or you can download necessary DLLs from the GroupDocs website: [https://releases.groupdocs.com/conversion/net/](https://releases.groupdocs.com/conversion/net/).  

## Install GroupDocs.Conversion using NuGet packages

Install the [GroupDocs.Conversion](https://www.nuget.org/packages/GroupDocs.Conversion) package for every supported target framework — .NET Framework 4.6.2 and later, .NET 6, .NET 8 and .NET 10. NuGet selects the matching runtime package for your project's target framework automatically.

{{< alert style="info" >}}
The separate `GroupDocs.Conversion.NETFramework` package is no longer updated. .NET Framework projects should reference `GroupDocs.Conversion` instead.
{{< /alert >}}

You can use the following tools to install the NuGet package:

 * [NuGet Package Manager](#use-the-nuget-package-manager)
 * [Package Manager Console](#use-the-package-manager-console)
 * [.NET CLI](#use-the-net-cli)

### Use the NuGet Package Manager

Open your project or solution in Visual Studio and follow the steps below to install the **GroupDocs.Conversion** package using the [NuGet Package Manager](https://learn.microsoft.com/en-us/nuget/consume-packages/install-use-packages-visual-studio):

1. In **Solution Explorer**, right-click your project name and select **Manage NuGet Packages** to display the NuGet Package Manager.

    ![Manage NuGet packages in Visual Studio](/conversion/net/images/getting-started/installation/manage-nuget-packages.png)

2. Select the **Browse** tab and type **GroupDocs.Conversion** in the search box. Select the **GroupDocs.Conversion** package and click **Install**.

    ![Install NuGet packages in Visual Studio](/conversion/net/images/getting-started/installation/install-nuget-package.png)

### Use the Package Manager Console

The [Package Manager Console](https://learn.microsoft.com/en-us/nuget/consume-packages/install-use-packages-powershell) uses PowerShell commands to install, update, and remove NuGet packages. Open your project in Visual Studio and click **Tools** -> **NuGet Package Manager** -> **Package Manager Console** to open the console window. Run the following command to install the latest version of the **GroupDocs.Conversion** library:

{{< tabs "example1">}}
{{< tab "Package Manager" >}}
```shell
PM> Install-Package GroupDocs.Conversion
```
{{< /tab >}}
{{< /tabs >}}

![Use Package Manager Console ](/conversion/net/images/getting-started/installation/package-manager-console.png)

### Use the .NET CLI

You can also use the [.NET CLI tool](https://docs.microsoft.com/en-us/dotnet/core/tools/) to install and update NuGet packages. This method is available for .NET 6+ projects. Open a terminal in your project's folder and execute the following command to install the **GroupDocs.Conversion** package:

{{< tabs "example2">}}
{{< tab ".NET CLI" >}}
```shell
dotnet add package GroupDocs.Conversion
```
{{< /tab >}}
{{< /tabs >}}

## Download GroupDocs.Conversion from the official website

Visit [https://releases.groupdocs.com/conversion/net/](https://releases.groupdocs.com/conversion/net/) and download the **GroupDocs.Conversion** assemblies as a ZIP archive or MSI installer. To reference the downloaded assembly files in your project, do the following:

1. Extract files from the ZIP archive or run the MSI installer to install **GroupDocs.Conversion** to a specific location on your computer.
2. Open your solution or project in Visual Studio.
3. In **Solution Explorer**, right-click the **References** or **Dependencies** node, and select **Add Reference** (for a .NET Framework project) or **Add Project Reference** (for a .NET project).
4. In the **Reference Manager** dialog box, select the **Browse** tab and click **Browse** to locate the _GroupDocs.Conversion.dll_ file for the target framework.

    ![Browse for the GroupDocs.Conversion assembly](/conversion/net/images/getting-started/installation/browse-for-groupdocs-dll.png)

5. Click **OK** to add a reference to the **GroupDocs.Conversion** library to your project.

{{< alert style="warning" >}}
The downloaded assemblies reference NuGet packages that are not included in the ZIP archive or the MSI installer. Ensure that your project has all the required dependencies installed — they are listed on the runtime package for your target framework: [GroupDocs.Conversion.Net462](https://www.nuget.org/packages/GroupDocs.Conversion.Net462#dependencies-body-tab), [GroupDocs.Conversion.Net60](https://www.nuget.org/packages/GroupDocs.Conversion.Net60#dependencies-body-tab), [GroupDocs.Conversion.Net80](https://www.nuget.org/packages/GroupDocs.Conversion.Net80#dependencies-body-tab), [GroupDocs.Conversion.Net100](https://www.nuget.org/packages/GroupDocs.Conversion.Net100#dependencies-body-tab). Installing the **GroupDocs.Conversion** NuGet package brings them in automatically.
{{< /alert >}}
