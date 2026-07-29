---
id: mcp-linux-installation
url: conversion/mcp/getting-started/linux-installation
title: Install on Linux
weight: 3
description: "Install the GroupDocs.Conversion MCP server on Linux with the setup bootstrapper (installs PowerShell, Docker or the .NET 10 SDK with libgdiplus and libfontconfig1) and the guided installer."
keywords: install MCP server Linux, MCP server Ubuntu, libgdiplus MCP error, self-hosted document conversion Linux
productName: GroupDocs.Conversion MCP Server
---

Install the GroupDocs.Conversion MCP server on **Linux** with the setup bootstrapper — it installs PowerShell (`pwsh`) plus Docker, or the .NET 10 SDK with `libgdiplus` and `libfontconfig1` — and then the guided installer:

```bash
git clone https://github.com/groupdocs/GroupDocs.Mcp.Installer.git
cd GroupDocs.Mcp.Installer
bash setup/linux.sh --channel docker
pwsh ./install-groupdocs-mcp.ps1 -Interactive
```

## Prerequisites

`setup/linux.sh` automates Debian/Ubuntu (apt + packages.microsoft.com), idempotently; add `--check` to report without installing. Other distros get the official documentation links printed instead of guessed package names.

* **Always:** PowerShell 7 (`pwsh`) — runs the installer scripts.
* **Docker channel (recommended):** docker engine (`sudo apt-get install -y docker.io`); the script adds you to the `docker` group — **log out/in** (or `newgrp docker`) before the first run.
* **NuGet channel:** .NET 10 SDK (`sudo apt-get install -y dotnet-sdk-10.0`) plus native graphics dependencies:

```bash
sudo apt-get install -y --no-install-recommends libgdiplus libfontconfig1 ttf-mscorefonts-installer
```

## Install

**Recommended — the installer:**

```bash
pwsh ./install-groupdocs-mcp.ps1 -Channel docker -Products conversion -Clients claude-desktop -Verify
```

**Manual alternatives:**

```bash
# Docker channel - native deps bundled in the image (amd64 + arm64):
docker run --rm -i -v $(pwd)/documents:/data ghcr.io/groupdocs-conversion/conversion-net-mcp:latest

# NuGet channel (requires .NET 10 SDK + the native deps above):
dnx GroupDocs.Conversion.Mcp --yes
```

Client config locations on Linux: Claude Desktop `~/.config/Claude/claude_desktop_config.json`, VS Code user-level `~/.config/Code/User/mcp.json` — full list in [Register in AI clients]({{< ref "conversion/mcp/getting-started/install-in-ai-clients.md" >}}).

## Verify

```bash
pwsh ./verify-groupdocs-mcp.ps1
```

A passing run completes the MCP handshake (three tools listed) and — when a document sits in your storage folder — a real `get_document_info` call. Headless servers: the docker channel plus `-EmitCompose` gives you a `docker-compose.yml` for supervised operation.

## Linux-specific troubleshooting

* **`DllNotFoundException: libgdiplus`** in tool responses — the NuGet-channel native deps are missing; run the `apt-get install` line above, or switch to the docker channel where they are bundled.
* **`docker: permission denied`** — your user is not in the `docker` group yet; `newgrp docker` or re-login.
* **Fonts look wrong in converted output** — install `ttf-mscorefonts-installer` (the setup script pre-accepts its EULA via debconf).

Installing on a different OS? [Windows]({{< ref "conversion/mcp/getting-started/windows-installation.md" >}}) · [macOS]({{< ref "conversion/mcp/getting-started/macos-installation.md" >}})
