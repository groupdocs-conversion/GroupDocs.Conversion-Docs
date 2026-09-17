---
id: mcp-licensing
url: conversion/mcp/getting-started/licensing
title: Licensing
weight: 7
description: "The GroupDocs.Conversion MCP server runs in evaluation mode out of the box; unlock it with your existing GroupDocs.Conversion license file or with metered (pay-per-use) keys, and confirm the active mode with the get_license_status tool."
keywords: GroupDocs MCP license, MCP server evaluation mode, does my GroupDocs license cover MCP, remove evaluation watermark, metered license MCP, GROUPDOCS_METERED_PUBLIC_KEY, get_license_status
productName: GroupDocs.Conversion MCP Server
toc: True
---

The GroupDocs.Conversion MCP server runs in **evaluation mode out of the box** — no sign-up, no key. Your existing GroupDocs.Conversion (or GroupDocs.Total) license unlocks full functionality: point the installer's `licensePath` — or the `GROUPDOCS_LICENSE_PATH` environment variable in a manual install — at your `.lic` file.

**The MCP server itself is open source (MIT); the underlying GroupDocs.Conversion engine requires a license for production use.**

There are three modes. The server takes the first one that is configured:

| Mode | Configure | Result |
|---|---|---|
| **Metered** (pay-per-use) | `GROUPDOCS_METERED_PUBLIC_KEY` **and** `GROUPDOCS_METERED_PRIVATE_KEY` | Billed for what you process; no evaluation limits |
| **License file** | `licensePath` / `GROUPDOCS_LICENSE_PATH` | Fully licensed; works offline |
| **Evaluation** | nothing | Watermark and a 15-document cap per process |

{{< alert style="info" >}}
**Metered wins.** If both metered keys and a license file are configured, the server uses metered licensing and ignores the file — and says so in its startup log.
{{< /alert >}}

## Evaluation mode limitations

Without a license:

* Converted output carries an **evaluation watermark**, and tool responses include an evaluation-mode notice.
* A single server process can open at most **15 documents**; further calls fail with *"Could not open more than 15 document files in evaluation mode"* until the server restarts (your AI client restarts it automatically on the next session).

An **empty** license path is always safe — the server logs a notice and continues in evaluation mode; it never errors because a license is absent.

## Applying a license

**Installer config:**

```json
{ "licensePath": "D:/Storage/Licenses/GroupDocs.Conversion.lic" }
```

**Manual (NuGet channel)** — set the environment variable in your client's server entry:

```json
"env": { "GROUPDOCS_LICENSE_PATH": "/path/to/GroupDocs.Conversion.lic" }
```

**Docker channel** — mount the license folder read-only:

```bash
docker run --rm -i -v /path/to/documents:/data \
  -v /path/to/license-folder:/license:ro \
  -e GROUPDOCS_LICENSE_PATH=/license/GroupDocs.Conversion.lic \
  ghcr.io/groupdocs-conversion/conversion-net-mcp:latest
```

Your license file is read from local disk by the local server process — like your documents, **it never leaves your machine**.

## Metered (pay-per-use) licensing

Metered licensing bills you for what you actually process, which suits AI agents: their usage is bursty and hard to size in advance. It is configured with two environment variables — there is nothing to mount and no file to ship:

```json
"env": {
  "GROUPDOCS_METERED_PUBLIC_KEY":  "<your public key>",
  "GROUPDOCS_METERED_PRIVATE_KEY": "<your private key>"
}
```

**One key pair covers every GroupDocs product and platform** — the same pair you already use for the library works here, and the consumption it reports is account-wide rather than per server.

{{< alert style="warning" >}}
**Both keys are required.** With only one set, the server ignores the metered configuration and stays in evaluation mode — it reports this explicitly rather than failing silently. Check with [`get_license_status`]({{< ref "conversion/mcp/tools-reference/get-license-status.md" >}}).
{{< /alert >}}

{{< alert style="warning" >}}
**Metered mode needs outbound connectivity.** Usage is reported to GroupDocs servers, so air-gapped or firewalled deployments must allow that egress — or use a license file instead. Only usage is reported; document content never leaves your machine.
{{< /alert >}}

### Keeping the private key out of committed files

The private key is a secret, and client configurations are plain files on disk — a project-scoped `.mcp.json` is committed by convention. In order of preference:

1. **Set both variables in your OS environment** and leave them out of the client config entirely. A stdio server inherits its client's environment, so this works in every client.
2. **Reference them indirectly** where the client supports it — Claude Code expands `${VAR}`; VS Code uses `${env:VAR}` and `${input:...}`.
3. **A literal value in a user-scoped config** (for example `~/.claude.json`) is acceptable for a single developer.
4. **Never** commit a literal key in a project-scoped `.mcp.json`.

With Docker, forward the two variables **by name** — `-e VAR` with no value copies it from the launching process, so the key never appears in the file:

```bash
docker run --rm -i -v /path/to/documents:/data \
  -e GROUPDOCS_MCP_STORAGE_PATH=/data \
  -e GROUPDOCS_METERED_PUBLIC_KEY -e GROUPDOCS_METERED_PRIVATE_KEY \
  ghcr.io/groupdocs-conversion/conversion-net-mcp:latest
```

{{< alert style="info" >}}
On macOS, an app launched from Finder does **not** inherit variables exported in your shell profile. Use `launchctl setenv`, or start the client from a terminal.
{{< /alert >}}

## Confirming which mode is active

Ask your agent *"what is the license status of the conversion server?"*. The [`get_license_status`]({{< ref "conversion/mcp/tools-reference/get-license-status.md" >}}) tool (server **26.9.0+**) answers without processing a document:

```json
{
  "mode": "metered",
  "licensed": true,
  "source": "metered-keys",
  "consumption": { "quantity": 1234.5678, "credit": 9642.0 },
  "server": { "name": "GroupDocs.Conversion.Mcp", "version": "26.9.0" },
  "engine": { "name": "GroupDocs.Conversion", "version": "26.6.0.0" }
}
```

If a key pair is rejected, the mode reverts to `evaluation` and the `note` field says why — for example *"Metered keys were supplied but the engine rejected them (Authentication failed.)"* — so a mistyped key surfaces here instead of as a watermark on your output.

## Getting a license

* [Free 30-day temporary license](https://purchase.groupdocs.com/temporary-license/) — full functionality for evaluation.
* [Purchase GroupDocs.Conversion](https://purchase.groupdocs.com/pricing/conversion/net) · [Product page](https://products.groupdocs.com/conversion/net/)
* General policies: [Purchase Policies and FAQ](https://purchase.groupdocs.com/policies)
