---
id: installation
url: conversion/java/installation
title: Install GroupDocs.Conversion for Java
linkTitle: Installation
weight: 1
description: "Learn how to install GroupDocs.Conversion for Java. Follow a step-by-step guide for Maven, Gradle, Kotlin, and manual JAR setup, and integrate seamless document conversion into your Java projects."
keywords: "GroupDocs.Conversion for Java, Java document conversion, installation guide, Maven setup, Gradle integration, Kotlin setup, JAR installation"
productName: GroupDocs.Conversion for Java
hideChildren: false
toc: true
---

**GroupDocs.Conversion for Java** enables seamless conversion between multiple document formats with high fidelity. This guide provides steps to integrate the library into your Java project.

### Prerequisites:

1. **Java Development Environment:** Ensure you have Java Development Kit (JDK) installed. The library supports versions 8 and above.
2. **Build Tool:** Compatible with Maven, Gradle, Kotlin and others for dependency management.
3. **GroupDocs.Conversion for Java License (optional):** Use the API in evaluation mode or apply for a free temporary license.

## Installation from GroupDocs Repository

All Java packages are hosted at [GroupDocs Artifact Repository](https://repository.groupdocs.com/). You can easily reference the GroupDocs.Conversion for Java API directly in your project using the following steps.

### Add GroupDocs Artifact Repository

First, you need to specify repository configuration/location in your project as follows:

{{< tabs "example1">}}
{{< tab "Maven" >}}
```xml
<repositories>
  <repository>
    <id>GroupDocs Artifact Repository</id>
    <name>GroupDocs Artifact Repository</name>
    <url>https://releases.groupdocs.com/java/repo/</url>
  </repository>
</repositories>
```
{{< /tab >}}
{{< tab "Gradle" >}}
```xml
repositories {
  maven {
    url "https://repository.groupdocs.com/repo/"
  }
}
```
{{< /tab >}}
{{< tab "Kotlin" >}}
```xml
repositories {
  maven(url = "https://repository.groupdocs.com/repo/")
}
```
{{< /tab >}}
{{< tab "Ivy" >}}
```xml
<ivysettings>
  <settings defaultResolver="chain"/>
  <resolvers>
    <chain name="chain">
      <ibiblio name="GroupDocs Repository" m2compatible="true" root="https://releases.groupdocs.com/java/repo/"/>
    </chain>
  </resolvers>
</ivysettings>
```
{{< /tab >}}
{{< tab "Sbt" >}}
```xml
resolvers += Resolver.url("GroupDocs Repository", url("https://releases.groupdocs.com/java/repo/"))
```
{{< /tab >}}
{{< /tabs >}}

### Add GroupDocs.Conversion as a dependency

Then define the GroupDocs.Conversion for Java API dependency in your project as follows:

{{< tabs "example2">}}
{{< tab "Maven" >}}
```xml
<dependencies>
  <dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-conversion</artifactId>
    <version>25.2</version>
  </dependency>
</dependencies>
```
{{< /tab >}}
{{< tab "Gradle" >}}
```xml
dependencies {
  implementation 'com.groupdocs:groupdocs-conversion:25.2'
}
```
{{< /tab >}}
{{< tab "Kotlin" >}}
```xml
dependencies {
  implementation("com.groupdocs:groupdocs-conversion:25.2")
}
```
{{< /tab >}}
{{< tab "Ivy" >}}
```xml
<dependency org="com.groupdocs" name="groupdocs-conversion" rev="25.2">
  <artifact name="groupdocs-conversion" ext="jar"/>
</dependency>
```
{{< /tab >}}
{{< tab "Sbt" >}}
```xml
libraryDependencies += "com.groupdocs" % "groupdocs-conversion" % "25.2"
```
{{< /tab >}}
{{< /tabs >}}

## Manual JAR Download

You can also download the JAR files directly from the [GroupDocs Downloads page](https://releases.groupdocs.com/java/repo/com/groupdocs/groupdocs-conversion/) and include them in your project manually.

## Example: Creating a simple command line application

Create following project structure:

```log
|--- pom.xml
|--- sample.txt
|--- src
     |--- main
          |-- java
              |-- com
                  |-- mycompany
                      |-- app
                          |-- App.java
```

Below is a content of the project files:

{{< tabs "project-files">}}
{{< tab "App.java" >}}
```java
package com.mycompany.app;

import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;

public class App {
  public static void main(String[] args) {
    try (Converter converter = new Converter("sample.txt")) {
      converter.convert("sample.pdf", new PdfConvertOptions());
    }
    System.out.println("Conversion complete");
  }
}
```
{{< /tab >}}
{{< tab "pom.xml" >}}
```xml
<?xml version="1.0" encoding="UTF-8"?>

<project xmlns="http://maven.apache.org/POM/4.0.0"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>

  <groupId>com.mycompany.app</groupId>
  <artifactId>conversion-helloworld</artifactId>
  <version>1.0-SNAPSHOT</version>

  <name>conversion-helloworld</name>

  <properties>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    <maven.compiler.source>1.8</maven.compiler.source>
    <maven.compiler.target>1.8</maven.compiler.target>
  </properties>

  <dependencies>
    <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-conversion</artifactId>
      <version>25.2</version>
    </dependency>
  </dependencies>

  <build>
    <plugins>
      <plugin>
        <artifactId>maven-assembly-plugin</artifactId>
        <executions>
          <execution>
            <phase>package</phase>
            <goals>
              <goal>single</goal>
            </goals>
          </execution>
        </executions>
        <configuration>
          <archive>
            <manifest>
              <mainClass>com.mycompany.app.App</mainClass>
              <addDefaultImplementationEntries>true</addDefaultImplementationEntries>
              <addDefaultSpecificationEntries>true</addDefaultSpecificationEntries>
            </manifest>
            <manifestEntries>
              <Specification-Vendor>My Company</Specification-Vendor>
              <Implementation-Vendor>My Company</Implementation-Vendor>
            </manifestEntries>
          </archive>
          <descriptorRefs>
            <descriptorRef>jar-with-dependencies</descriptorRef>
          </descriptorRefs>
        </configuration>
      </plugin>
    </plugins>
  </build>

  <repositories>
    <repository>
      <id>GroupDocs Artifact Repository</id>
      <name>GroupDocs Artifact Repository</name>
      <url>https://releases.groupdocs.com/java/repo/</url>
    </repository>
  </repositories>
</project>
```
{{< /tab >}}
{{< tab "sample.txt" >}}
```
Sample text
```
{{< /tab >}}
{{< /tabs >}}

To run the application first build it (from the root project directory where pom.xml is located):

```bash
mvn clean package
```

Next run it:

```bash
java -jar target/conversion-helloworld-1.0-SNAPSHOT-jar-with-dependencies.jar
```

Here is a program output:

```log
Conversion complete
```

After that you can see and open `sample.pdf` file in the root project directory

{{< alert style="info" >}}
Note: you can create and run this project in your favourite IDE instead. Also you can build and run it without Maven usage, for example using the IDE dependency and build system or for example using Gradle.
{{< /alert >}}

For more examples, visit the [developer guide]({{< ref "conversion/java/developer-guide" >}})
