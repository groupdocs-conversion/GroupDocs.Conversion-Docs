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

{{< alert style="info" >}}
**Platform-specific troubleshooting:** runtime problems depend on which build you run. For the `dnx` runner, native graphics libraries, and the Docker channel, see [Troubleshooting (.NET)]({{< ref "conversion/net/mcp/troubleshooting.md" >}}). The issues on this page apply to every platform.
{{< /alert >}}

## Why is my MCP server not showing up in Claude Desktop?

1. **Restart the client** — every client reads its MCP config only at startup.
2. Check the config file location for your OS ([per-client reference]({{< ref "conversion/net/mcp/install-in-ai-clients.md" >}})) and that the entry sits under the right root key (`mcpServers` for Claude Desktop/Cursor/Windsurf, `servers` for VS Code/VS 2022).
3. Validate the JSON — a trailing comma silently breaks the whole file. If you used the [installer](https://github.com/groupdocs/GroupDocs.Mcp.Installer), a timestamped `.bak` of your previous config sits next to the file for comparison.

## The first tool call is slow or fails once, then works

A **cold cache**: on the very first use the server's package or image is still downloading while the client is already waiting on the connection. Warming it once fixes it for good — the exact command depends on your build: [.NET]({{< ref "conversion/net/mcp/troubleshooting.md" >}}#the-first-tool-call-is-slow-or-fails-once-and-then-works).

## The server fails to start, or a runtime dependency is missing

These are properties of the build you run rather than of MCP, so the fixes live with the platform:

| Symptom | Where the fix is |
|---|---|
| `dnx: command not found` | [.NET troubleshooting]({{< ref "conversion/net/mcp/troubleshooting.md" >}}#dnx-command-not-found) — `dnx` ships inside the .NET 10 SDK |
| `DllNotFoundException: libgdiplus` on Linux/macOS | [.NET troubleshooting]({{< ref "conversion/net/mcp/troubleshooting.md" >}}#dllnotfoundexception-libgdiplus) — install the native graphics libraries, or use the Docker image |
| "docker daemon not reachable" | [.NET troubleshooting]({{< ref "conversion/net/mcp/troubleshooting.md" >}}#docker-daemon-not-reachable) — start Docker Desktop or `dockerd` |

## How do I remove the evaluation watermark?

Apply your GroupDocs.Conversion (or GroupDocs.Total) license — set `licensePath` in the installer config or `GROUPDOCS_LICENSE_PATH` in a manual entry. Evaluation mode also caps a server process at 15 opened documents. Details and license links: [Licensing]({{< ref "conversion/mcp/getting-started/licensing.md" >}}).

## Does the server support OCR for scanned PDFs?

**Not currently.** Conversion works on documents with a text layer; a scanned, image-only PDF converts as images, not recognized text. If OCR is important for your pipeline, tell us in the [forum](https://forum.groupdocs.com/c/conversion/11) — it directly shapes the roadmap.

## Verifying an installation end-to-end

Ask your agent *"list your GroupDocs conversion tools and the license status"* — it should name `convert`, `get_supported_formats`, `get_document_info`, and `get_license_status`. For a scripted check that performs the real MCP handshake and a live conversion call, see [verifying a .NET installation]({{< ref "conversion/net/mcp/troubleshooting.md" >}}#verifying-an-installation-end-to-end).

## Still stuck?

Post your config (redact license paths) and the client name in the [Conversion forum](https://forum.groupdocs.com/c/conversion/11) — we answer MCP questions daily. Bugs: [GitHub issues](https://github.com/groupdocs-conversion/GroupDocs.Conversion.Mcp/issues).
