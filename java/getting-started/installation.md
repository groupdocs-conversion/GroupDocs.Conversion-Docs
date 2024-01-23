---
id: installation
url: conversion/java/installation
title: Install GroupDocs.Conversion for Java
weight: 4
description: "GroupDocs.Conversion for Java installation"
keywords: "groupdocs conversion java, installation, maven"
productName: GroupDocs.Conversion for Java
hideChildren: False
toc: True
---

## Install using Maven

All Java packages are hosted at [GroupDocs Artifact Repository](https://repository.groupdocs.com/). You can easily reference the GroupDocs.Conversion for Java API directly in your Maven project using the following steps.

### Add GroupDocs Artifact Repository

First, specify the repository configuration/location in your Maven `pom.xml` file as follows:

```xml
<repositories>
    <repository>
        <id>GroupDocs Artifact Repository</id>
        <name>GroupDocs Artifact Repository</name>
        <url>https://releases.groupdocs.com/java/repo/</url>
    </repository>
</repositories>
```

### Add GroupDocs.Conversion as a dependency

Then define the GroupDocs.Conversion for Java API dependency in your `pom.xml` file as follows:

```xml
<dependencies>
    <dependency>
        <groupId>com.groupdocs</groupId>
        <artifactId>groupdocs-conversion</artifactId>
        <version>22.11</version>
    </dependency>
</dependencies>
```

