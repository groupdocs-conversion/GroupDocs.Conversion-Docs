---
id: mcp-system-requirements
url: conversion/mcp/getting-started/system-requirements
title: System requirements
weight: 8
description: "The GroupDocs.Conversion MCP server runs anywhere Docker runs, or on any OS with the .NET 10 SDK — this page lists exact requirements per channel and operating system."
keywords: MCP server requirements, does MCP server need Docker, .NET 10 MCP server
productName: GroupDocs.Conversion MCP Server
toc: True
---

The GroupDocs.Conversion MCP server runs **anywhere Docker runs**, or on any OS with the **.NET 10 SDK** — pick one channel; you do not need both.

| | Docker channel (recommended) | NuGet channel (`dnx`) |
|---|---|---|
| Runtime | Docker Desktop / docker engine | .NET 10 SDK (includes `dnx`) |
| Native graphics deps | bundled in the image | Windows: built-in GDI+ · Linux: `libgdiplus`, `libfontconfig1`, MS core fonts · macOS: `mono-libgdiplus` |
| Architectures | linux/amd64 + linux/arm64 (Apple Silicon native) | any .NET 10 platform |
| Installer scripts | PowerShell 5.1 (Windows built-in) or PowerShell 7 (`pwsh`, macOS/Linux) | same |
| Disk | image ~download once per version | package cached by `dnx`/NuGet |
| Network | pull from ghcr.io / docker.io at install only | nuget.org at install only — no network at runtime |

Per-OS setup, including the one-shot prerequisite bootstrappers (`setup/windows.ps1`, `setup/linux.sh`, `setup/macos.sh`):

* [Install on Windows]({{< ref "conversion/mcp/getting-started/windows-installation.md" >}})
* [Install on Linux]({{< ref "conversion/mcp/getting-started/linux-installation.md" >}})
* [Install on macOS]({{< ref "conversion/mcp/getting-started/macos-installation.md" >}})

AI client requirements: any MCP-compatible client (Claude Desktop, Claude Code, VS Code / GitHub Copilot, Visual Studio 2022 17.14+, Cursor, Windsurf, Cline, Codex CLI) — see [Register in AI clients]({{< ref "conversion/mcp/getting-started/install-in-ai-clients.md" >}}).
