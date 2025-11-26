---
id: installation
url: conversion/nodejs-java/installation
title: Install GroupDocs.Conversion for Node.js via Java 
linkTitle: Installation
weight: 4
description: "Install GroupDocs.Conversion for Node.js via Java using npm or an offline package. Includes prerequisites, Java setup, verification, and troubleshooting."
keywords:
productName: GroupDocs.Conversion for Node.js via Java
hideChildren: False
toc: True
---

### Prerequisites

- Node.js: 20 LTS or later
- Java: JRE/JDK 8+ (recommended 17 LTS)
- Build tools if needed by your environment (node-gyp toolchain)

See full details on the [System Requirements]({{< ref "conversion/nodejs-java/getting-started/system-requirements" >}}) page.

### Install from npm

All Java-bridged packages are hosted on npm. Install the library into your project using your preferred package manager:

```bash
# npm
npm install @groupdocs/groupdocs.conversion

# yarn
yarn add @groupdocs/groupdocs.conversion

# pnpm
pnpm add @groupdocs/groupdocs.conversion
```

### Set up Java (JAVA_HOME)

Ensure your Java installation is available on PATH and `JAVA_HOME` is set.

Windows (PowerShell):

```powershell
$env:JAVA_HOME="C:\Program Files\Java\jdk-17"
$env:Path="$env:JAVA_HOME\bin;$env:Path"
```

Linux/macOS (Bash):

```bash
export JAVA_HOME=/usr/lib/jvm/java-17
export PATH="$JAVA_HOME/bin:$PATH"
```

See the [System Requirements]({{< ref "conversion/nodejs-java/getting-started/system-requirements" >}}) page for more details.

### Verify installation

Create a small script (e.g., `check.js`) and run it with Node.js:

{{< tabs "check_installation" >}}

{{< tab "check.js" >}}  
{{< highlight javascript "" >}}

try {
  const conversion = require('@groupdocs/groupdocs.conversion');
  console.log('GroupDocs.Conversion loaded:', typeof conversion === 'object');
  console.log('Java bridge initialized successfully.');
} catch (e) {
  console.error('Failed to load GroupDocs.Conversion:', e);
  process.exit(1);
}

{{< /highlight >}}
{{< /tab >}}

{{< /tabs >}}


And then run the script to verify the installation:

```bash
node check.js
```

### Download from GroupDocs.Releases (offline)

You can download a package archive from [GroupDocs.Releases](https://releases.groupdocs.com/conversion/nodejs-java/#direct-download) and add it to your app. After downloading the `.tar` file, install it locally:

```bash
npm install ./groupdocs-conversion-<version>.tar
```

Alternatively, configure npm to use your corporate registry or proxy, then install using the standard command.

### Troubleshooting installation

- node-gyp toolchain not found: install the required build tools for your OS (see System Requirements).
- Java not detected: set `JAVA_HOME` and add `<JAVA_HOME>/bin` to `PATH`.
- Corporate proxy: configure npm proxy settings before running install.
- Permission errors: ensure you have write access to the project directory and cache folders.