---
id: mcp-net
url: conversion/net/mcp
title: MCP server for .NET
linkTitle: MCP Server
weight: 7
description: "Install and configure the GroupDocs.Conversion MCP server for .NET — one-click install links for VS Code and Cursor, per-OS setup for Windows, Linux, and macOS, and the full environment-variable reference."
keywords: GroupDocs.Conversion MCP .NET, install MCP server dnx, MCP server Docker image, MCP server configuration, Model Context Protocol .NET
productName: GroupDocs.Conversion MCP Server for .NET
hideChildren: True
toc: True
---

Everything needed to **install and run** the GroupDocs.Conversion MCP server on the .NET platform. What the server *does* — its tools, use cases, and licensing model — is platform-independent and lives in the [MCP server section]({{< ref "conversion/mcp/_index.md" >}}).

| The .NET build at a glance | |
|---|---|
| Package | [`GroupDocs.Conversion.Mcp`](https://www.nuget.org/packages/GroupDocs.Conversion.Mcp) (current **26.9.0**) |
| One-command run | `dnx GroupDocs.Conversion.Mcp --yes` |
| Container images | `ghcr.io/groupdocs-conversion/conversion-net-mcp` · `groupdocs/conversion-net-mcp` |
| Prerequisites | [.NET 10 SDK](https://dotnet.microsoft.com/download/dotnet/10.0) for the NuGet channel, or Docker |
| Source | [GroupDocs.Conversion.Mcp on GitHub](https://github.com/groupdocs-conversion/GroupDocs.Conversion.Mcp) |
| Release notes | [changelog](https://github.com/groupdocs-conversion/GroupDocs.Conversion.Mcp/tree/main/changelog) · [GitHub releases](https://github.com/groupdocs-conversion/GroupDocs.Conversion.Mcp/releases) |

## Start here

1. **Install** for your operating system — [Windows]({{< ref "conversion/net/mcp/windows-installation.md" >}}) · [Linux]({{< ref "conversion/net/mcp/linux-installation.md" >}}) · [macOS]({{< ref "conversion/net/mcp/macos-installation.md" >}})
2. **Register it in your AI client** — [one-click links and per-client configs]({{< ref "conversion/net/mcp/install-in-ai-clients.md" >}})
3. **Point it at your documents** — [configuration]({{< ref "conversion/net/mcp/configuration.md" >}})
4. **License it** — evaluation, a license file, or metered keys: [Licensing]({{< ref "conversion/mcp/getting-started/licensing.md" >}})

## In this section

* [Install on Windows]({{< ref "conversion/net/mcp/windows-installation.md" >}})
* [Install on Linux]({{< ref "conversion/net/mcp/linux-installation.md" >}})
* [Install on macOS]({{< ref "conversion/net/mcp/macos-installation.md" >}})
* [Register in AI clients]({{< ref "conversion/net/mcp/install-in-ai-clients.md" >}}) — VS Code, Cursor, Claude, Visual Studio, Windsurf, Cline, Codex, Rider
* [Configuration]({{< ref "conversion/net/mcp/configuration.md" >}}) — storage, output, license, metered keys
* [System requirements]({{< ref "conversion/net/mcp/system-requirements.md" >}})
* [Troubleshooting (.NET)]({{< ref "conversion/net/mcp/troubleshooting.md" >}}) — `dnx`, native libraries, Docker daemon

## Platform-independent reference

* [Tools reference]({{< ref "conversion/mcp/tools-reference/_index.md" >}}) — `convert`, `get_supported_formats`, `get_document_info`, `get_license_status`
* [Use cases]({{< ref "conversion/mcp/use-cases/_index.md" >}}) · [Supported formats]({{< ref "conversion/mcp/supported-formats.md" >}}) · [Troubleshooting & FAQ]({{< ref "conversion/mcp/troubleshooting-faq.md" >}})
