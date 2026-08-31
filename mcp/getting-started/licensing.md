---
id: mcp-licensing
url: conversion/mcp/getting-started/licensing
title: Licensing
weight: 7
description: "The GroupDocs.Conversion MCP server runs in evaluation mode out of the box; your existing GroupDocs.Conversion license unlocks full functionality — point the installer's licensePath (or GROUPDOCS_LICENSE_PATH) at your .lic file."
keywords: GroupDocs MCP license, MCP server evaluation mode, does my GroupDocs license cover MCP, remove evaluation watermark
productName: GroupDocs.Conversion MCP Server
toc: True
---

The GroupDocs.Conversion MCP server runs in **evaluation mode out of the box** — no sign-up, no key. Your existing GroupDocs.Conversion (or GroupDocs.Total) license unlocks full functionality: point the installer's `licensePath` — or the `GROUPDOCS_LICENSE_PATH` environment variable in a manual install — at your `.lic` file.

**The MCP server itself is open source (MIT); the underlying GroupDocs.Conversion engine requires a license for production use.**

## Evaluation mode limitations

Without a license:

* Converted output carries an **evaluation watermark**, and tool responses include an evaluation-mode notice.
* A single server process can open at most **15 documents**; further calls fail with *"Could not open more than 15 document files in evaluation mode"* until the server restarts (your AI client restarts it automatically on the next session).

An **empty** license path is always safe — the server logs a notice and continues in evaluation mode; it never errors because a license is absent.

## Applying a license

**Installer config:**

```json
{ "licensePath": "D:/Storage/Licenses/GroupDocs.Total.lic" }
```

**Manual (NuGet channel)** — set the environment variable in your client's server entry:

```json
"env": { "GROUPDOCS_LICENSE_PATH": "/path/to/GroupDocs.Total.lic" }
```

**Docker channel** — mount the license folder read-only:

```bash
docker run --rm -i -v /path/to/documents:/data \
  -v /path/to/license-folder:/license:ro \
  -e GROUPDOCS_LICENSE_PATH=/license/GroupDocs.Total.lic \
  ghcr.io/groupdocs-conversion/conversion-net-mcp:latest
```

Your license file is read from local disk by the local server process — like your documents, **it never leaves your machine**.

## Getting a license

* [Free 30-day temporary license](https://purchase.groupdocs.com/temporary-license/) — full functionality for evaluation.
* [Purchase GroupDocs.Conversion](https://purchase.groupdocs.com/pricing/conversion/net) · [Product page](https://products.groupdocs.com/conversion/net/)
* General policies: [Purchase Policies and FAQ](https://purchase.groupdocs.com/policies)
