---
id: mcp-on-premise-document-conversion
url: conversion/mcp/use-cases/on-premise-document-conversion
title: "Running GroupDocs MCP servers on-premise: architecture and security model"
weight: 5
description: "Run document conversion for AI agents fully on-premise: the GroupDocs.Conversion MCP server uses local stdio transport with no external endpoints — suitable for regulated environments where documents cannot leave the network."
keywords: on-premise MCP server, self-hosted document conversion AI, local MCP server no cloud, air-gapped AI document processing
productName: GroupDocs.Conversion MCP Server
toc: True
---

Run document conversion for AI agents **fully on-premise**: the GroupDocs.Conversion MCP server uses local stdio transport with **no external endpoints, no inbound ports, and no telemetry** — suitable for regulated environments where documents cannot leave the network. This page is the one to send your security reviewer.

## The architecture in one picture

```
┌─────────────┐   stdio (stdin/stdout)   ┌──────────────────────┐        ┌──────────────────┐
│  AI client   │ ───────────────────────► │  MCP server process   │ ─────► │ local filesystem  │
│ (Claude, VS  │ ◄─────────────────────── │ (GroupDocs engine)    │ ◄───── │ storage / output  │
│ Code, agent) │      tool results        │  child process        │        │ folders           │
└─────────────┘                           └──────────────────────┘        └──────────────────┘
```

* **Transport:** the AI client *starts the server as a child process* and communicates over standard input/output. The server never listens on a network socket — there is nothing to firewall, nothing to expose.
* **Data path:** agent → local server → local filesystem. Documents are read from and written to the folders you configure; no document content is transmitted anywhere.
* **Network use:** only at install time (pulling the package from nuget.org or the image from ghcr.io/docker.io). At runtime the server makes no outbound calls. In an air-gapped segment, pre-pull the image or pre-cache the package and pin the version.
* **Telemetry:** none. The server does not phone home, and the engine processes documents in-process.

Note the distinction that matters for review: the **documents** stay local unconditionally. The **prompts** go wherever your AI client's model runs — with a cloud-hosted assistant, your instruction text ("convert invoice.pdf") reaches the model, but the invoice itself never does. Pair the server with a locally-hosted model (as in our [n8n self-hosted walkthrough](https://blog.groupdocs.com/conversion/agentic-document-conversion-with-n8n-and-mcp/)) and the entire loop stays inside the perimeter.

## Docker deployment inside the perimeter

The container is self-contained (all native dependencies bundled, `linux/amd64` + `linux/arm64`), which makes perimeter deployment reproducible:

```bash
docker run --rm -i \
  -v /srv/documents:/data \
  -v /srv/licenses:/license:ro \
  -e GROUPDOCS_LICENSE_PATH=/license/GroupDocs.Total.lic \
  ghcr.io/groupdocs-conversion/conversion-net-mcp:26.7.2
```

* Pin the immutable version tag (`:26.7.2`) — never `:latest` — for change control.
* Mount the license read-only; like the documents, the license file never leaves the host.
* For fleets, the [installer]({{< ref "conversion/mcp/getting-started/configuration.md" >}}) emits a `docker-compose.yml` (`-EmitCompose`) with the same volume and license mapping.

## License management

Works in evaluation mode with no license present (watermarked output, 15-document per-process cap). Your existing GroupDocs.Conversion license applies — one file, mounted or referenced locally; [details]({{< ref "conversion/mcp/getting-started/licensing.md" >}}).

## What this fits — honestly

Environments with data-residency, confidentiality, or regulatory constraints (healthcare, legal, government, industrial) where the *non-negotiable* is that documents never transit third-party infrastructure. The stdio model satisfies that by construction. What it does **not** do: make claims about your overall compliance posture — certification applies to deployments, not components. Compare your three options honestly: cloud AI upload (simplest, documents leave), hosted conversion API (documents leave, but to one vendor), local MCP (documents never leave — this server).

## FAQ

**Can we run document conversion for AI agents with no cloud at all?**
Yes for the documents unconditionally; fully — including the model — if you pair the server with a self-hosted LLM.

**Does the server open any ports?**
No. Stdio only; it is a child process of your AI client (or of your agent runtime / n8n).

**How do updates work in a restricted network?**
Pull the pinned image version in a controlled window, re-tag internally, and roll it out like any other container update.
