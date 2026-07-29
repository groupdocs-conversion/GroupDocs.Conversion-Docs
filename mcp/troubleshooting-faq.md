---
id: mcp-troubleshooting-faq
url: conversion/mcp/troubleshooting-faq
title: Troubleshooting & FAQ
weight: 5
description: "Solutions to the most common GroupDocs.Conversion MCP server issues — server not appearing in the client, startup failures, missing native dependencies, and first-launch timeouts."
keywords: MCP server not showing up in Claude Desktop, Claude can't see MCP tools, MCP server failed to start, dnx command not found, libgdiplus not found error, remove watermark evaluation
productName: GroupDocs.Conversion MCP Server
toc: True
---

Solutions to the most common GroupDocs.Conversion MCP server issues — server not appearing in the client, startup failures, missing native dependencies, and first-launch timeouts.

## Why is my MCP server not showing up in Claude Desktop?

1. **Restart the client** — every client reads its MCP config only at startup.
2. Check the config file location for your OS ([per-client reference]({{< ref "conversion/mcp/getting-started/install-in-ai-clients.md" >}})) and that the entry sits under the right root key (`mcpServers` for Claude Desktop/Cursor/Windsurf, `servers` for VS Code/VS 2022).
3. Validate the JSON — a trailing comma silently breaks the whole file. If you used the [installer](https://github.com/groupdocs/GroupDocs.Mcp.Installer), a timestamped `.bak` of your previous config sits next to the file for comparison.

## The first tool call is slow or fails once, then works

A **cold cache**: on the very first use, `dnx` downloads the package (or Docker pulls the image) while the client is already waiting on the connection. Pre-warm once and the problem disappears:

```powershell
./install-groupdocs-mcp.ps1 -Prewarm
```

(The installer's `-Verify` mode pre-warms automatically.)

## `dnx` command not found

The `dnx` runner ships **inside the .NET 10 SDK**. Install the SDK (the `setup/<os>` bootstrapper does it), then open a **new** terminal so PATH refreshes. On Windows it lives at `C:\Program Files\dotnet\dnx.cmd`.

## `DllNotFoundException: libgdiplus` (Linux/macOS, NuGet channel)

The engine needs native graphics libraries when running outside Docker:

```bash
# Linux (Debian/Ubuntu)
sudo apt-get install -y --no-install-recommends libgdiplus libfontconfig1 ttf-mscorefonts-installer
# macOS
brew install mono-libgdiplus
```

Or switch to the **docker channel**, where everything is bundled in the image.

## "docker daemon not reachable"

Start Docker Desktop (or `dockerd`). The installer's preflight detects this **before** writing any config and prints the exact `setup/<os>` command that fixes the environment.

## How do I remove the evaluation watermark?

Apply your GroupDocs.Conversion (or GroupDocs.Total) license — set `licensePath` in the installer config or `GROUPDOCS_LICENSE_PATH` in a manual entry. Evaluation mode also caps a server process at 15 opened documents. Details and license links: [Licensing]({{< ref "conversion/mcp/getting-started/licensing.md" >}}).

## Does the server support OCR for scanned PDFs?

**Not currently.** Conversion works on documents with a text layer; a scanned, image-only PDF converts as images, not recognized text. If OCR is important for your pipeline, tell us in the [forum](https://forum.groupdocs.com/c/conversion/11) — it directly shapes the roadmap.

## Verifying an installation end-to-end

```powershell
./verify-groupdocs-mcp.ps1
```

Performs the real MCP handshake per configured product and — when a document exists in your storage folder — a live `get_document_info` call through the engine. Exit `0` = healthy; failures print the server's own error text.

## Still stuck?

Post your config (redact license paths) and the client name in the [Conversion forum](https://forum.groupdocs.com/c/conversion/11) — we answer MCP questions daily. Bugs: [GitHub issues](https://github.com/groupdocs-conversion/GroupDocs.Conversion.Mcp/issues).
