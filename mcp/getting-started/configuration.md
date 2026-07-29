---
id: mcp-configuration
url: conversion/mcp/getting-started/configuration
title: Configuration
weight: 6
description: "Configure the GroupDocs.Conversion MCP server through one config file: set the documents folder, output folder, license path, delivery channel (Docker or NuGet), and target clients in a single place."
keywords: MCP server environment variables, MCP server config file, MCP server storage path, pin MCP server version
productName: GroupDocs.Conversion MCP Server
---

Configure the GroupDocs.Conversion MCP server through **one config file**: the documents folder, output folder, license path, delivery channel (Docker or NuGet), and target clients — set once, applied everywhere. This is the installer's `groupdocs-mcp.config.json`:

```json
{
  "channel":     "docker",
  "registry":    "ghcr",
  "clients":     ["claude-desktop", "vscode"],
  "version":     "latest",
  "storagePath": "D:/Storage/Documents",
  "outputPath":  "D:/Storage/Output",
  "licensePath": "D:/Storage/Licenses/GroupDocs.Total.lic",
  "products":    ["conversion"]
}
```

* `channel` — `docker` (self-contained, recommended) or `nuget` (`dnx`, needs the .NET 10 SDK).
* `storagePath` — where the server reads input documents (created if missing).
* `outputPath` — optional separate folder for converted files; empty = same as storage.
* `licensePath` — empty string = evaluation mode (safe, no error); see [Licensing]({{< ref "conversion/mcp/getting-started/licensing.md" >}}).
* `version` — `"latest"` or a pin such as `"26.7.2"`. Pinning is recommended for shared/committed configs.
* Any CLI switch overrides the file: `-Channel`, `-Products`, `-Clients`, `-Version`.

## Environment variables (manual installs)

When you register the server manually, the same settings travel as environment variables:

| Variable | Description | Default |
|---|---|---|
| `GROUPDOCS_MCP_STORAGE_PATH` | Base folder for input and output files | current directory |
| `GROUPDOCS_MCP_OUTPUT_PATH` | Optional separate folder for output files | same as storage |
| `GROUPDOCS_LICENSE_PATH` | Path to a GroupDocs license file | empty = evaluation mode |

## Docker volume mapping

On the docker channel, host folders map into the container:

* `storagePath` → `/data` (with `GROUPDOCS_MCP_STORAGE_PATH=/data`)
* `outputPath` → `/data/output` (when set)
* license folder → `/license:ro` with `GROUPDOCS_LICENSE_PATH=/license/<file>.lic`

```bash
docker run --rm -i \
  -v /path/to/documents:/data \
  -v /path/to/license-folder:/license:ro \
  -e GROUPDOCS_LICENSE_PATH=/license/GroupDocs.Total.lic \
  ghcr.io/groupdocs-conversion/conversion-net-mcp:latest
```

## Compose-only setups

For container fleets without client registration, generate a `docker-compose.yml`:

```powershell
./install-groupdocs-mcp.ps1 -EmitCompose -Clients @()
```
