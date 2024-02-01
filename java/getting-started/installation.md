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

All Java packages are hosted at[GroupDocs Artifact Repository](https://repository.groupdocs.com/). You can easily
reference GroupDocs.Conversion for Java API directly in your Maven project using the following steps.

### Add GroupDocs Artifact Repository

First, you need to specify the repository configuration/location in your Maven`pom.xml` file as follows:

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

Then define GroupDocs.Conversion for Java API dependency in your`pom.xml` file as follows:

```xml

<dependencies>
    <dependency>
        <groupId>com.groupdocs</groupId>
        <artifactId>groupdocs-conversion</artifactId>
        <version>23.12</version>
    </dependency>
</dependencies>
```

### Example: creating a simple command line application

Create following project structure:

```
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

<details>
<summary>pom.xml</summary>

```xml
<?xml version="1.0" encoding="UTF-8"?>

<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
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
            <version>23.12</version>
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

</details>

<details>
<summary>App.java</summary>

```java
package com.mycompany.app;

import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;

/**
 * Hello world!
 */
public class App {
    public static void main(String[] args) {
        try (Converter converter = new Converter("sample.txt")) {
            converter.convert("sample.pdf", new PdfConvertOptions());
        }
        System.out.println("Conversion complete");
    }
}
```

</details>


<details>
<summary>sample.txt</summary>

```
Sample text
```

</details>

To run the application first build it (from the root project directory where pom.xml is located):

```
mvn clean package
```

Next run it:

```
java -jar target/conversion-helloworld-1.0-SNAPSHOT-jar-with-dependencies.jar
```

Here is a program output:

```
Conversion complete
```

After that you can see and open sample.pdf file in the root project directory

Note: you can create and run this project in your favourite IDE instead. Also you can build and run it without Maven usage, for example using the IDE dependency and build system or for example using Gradle.