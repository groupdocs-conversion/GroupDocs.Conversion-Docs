---
id: mcp-on-premise-document-conversion
url: conversion/mcp/use-cases/on-premise-document-conversion
title: "Running GroupDocs MCP servers on-premise: architecture and security model"
linkTitle: On-premise deployment
weight: 5
description: "Run document conversion for AI agents fully on-premise: the GroupDocs.Conversion MCP server uses local stdio transport with no external endpoints — suitable for regulated environments where documents cannot leave the network."
keywords: on-premise MCP server, self-hosted document conversion AI, local MCP server no cloud, air-gapped AI document processing
productName: GroupDocs.Conversion MCP Server
toc: True
structuredData:
    showOrganization: True
    howTo:
        name: "Running GroupDocs MCP servers on-premise: architecture and security model"
        description: "Run document conversion for AI agents fully on-premise: the GroupDocs.Conversion MCP server uses local stdio transport with no external endpoints — suitable for regulated environments where documents cannot leave the network."
        steps:
        - name: "Run the pinned image inside the perimeter"
          text: "Start the GroupDocs.Conversion MCP server from its versioned Docker image as a child process of the AI client."
        - name: "Mount only the folders the agent may reach"
          text: "Map the document folder read-write and the license folder read-only."
        - name: "Choose the license mode"
          text: "Use a license file for fully offline operation; metered licensing needs outbound egress for usage reports."
---

Run document conversion for AI agents **fully on-premise**: the GroupDocs.Conversion MCP server uses local stdio transport with **no external endpoints, no inbound ports, and no telemetry** — suitable for regulated environments where documents cannot leave the network. This page is the one to send your security reviewer.

{{< alert style="info" >}}
The commands and config snippets on this page are for the **.NET** build of the server — the only platform available today. Installation and client setup: [MCP server for .NET]({{< ref "conversion/net/mcp/_index.md" >}}). Other platforms will expose the same tools with their own launch command; everything else on this page applies unchanged.
{{< /alert >}}

## The architecture in one picture

```text
+--------------+          +--------------------+         +------------------+
|  AI client   |  stdio   | MCP server process | reads / | local filesystem |
| (Claude, VS  | <----->  | (GroupDocs engine) | <-----> | storage / output |
| Code, agent) | JSON-RPC |   child process    |  writes |     folders      |
+--------------+          +--------------------+         +------------------+
```

* **Transport:** the AI client *starts the server as a child process* and communicates over standard input/output. The server never listens on a network socket — there is nothing to firewall, nothing to expose.
* **Data path:** agent → local server → local filesystem. Documents are read from and written to the folders you configure; no document content is transmitted anywhere.
* **Network use:** only at install time (pulling the package from nuget.org or the image from ghcr.io/docker.io). At runtime the server makes no outbound calls with a license file; metered licensing reports usage and needs egress — see [License management](#license-management). In an air-gapped segment, pre-pull the image or pre-cache the package and pin the version.
* **Telemetry:** none. The server does not phone home, and the engine processes documents in-process.

Note the distinction that matters for review: the **documents** stay local unconditionally. The **prompts** go wherever your AI client's model runs — with a cloud-hosted assistant, your instruction text ("convert invoice.pdf") reaches the model, but the invoice itself never does. Pair the server with a locally-hosted model and the entire loop stays inside the perimeter.

## Docker deployment inside the perimeter

The container is self-contained (all native dependencies bundled, `linux/amd64` + `linux/arm64`), which makes perimeter deployment reproducible:

```bash
docker run --rm -i \
  -v /srv/documents:/data \
  -v /srv/licenses:/license:ro \
  -e GROUPDOCS_LICENSE_PATH=/license/GroupDocs.Conversion.lic \
  ghcr.io/groupdocs-conversion/conversion-net-mcp:26.9.0
```

* Pin the immutable version tag (`:26.9.0`) — never `:latest` — for change control.
* Mount the license read-only; like the documents, the license file never leaves the host.
* For fleets, the [installer]({{< ref "conversion/net/mcp/configuration.md" >}}) emits a `docker-compose.yml` (`-EmitCompose`) with the same volume and license mapping.

## License management

Works in evaluation mode with no license present (watermarked output, 15-document per-process cap). Two ways to license it, and the choice has a network consequence:

* **License file** — read from local disk by the local process. Fully offline; the right answer for air-gapped deployments. Your existing GroupDocs.Conversion license applies.
* **Metered (pay-per-use)** — reports *usage* to GroupDocs servers, so it needs outbound egress. Document content is never part of that report, but the connection must be allowed.

Both are covered in [Licensing]({{< ref "conversion/mcp/getting-started/licensing.md" >}}).

## What this fits — honestly

Environments with data-residency, confidentiality, or regulatory constraints (healthcare, legal, government, industrial) where the *non-negotiable* is that documents never transit third-party infrastructure. The stdio model satisfies that by construction. What it does **not** do: make claims about your overall compliance posture — certification applies to deployments, not components. Compare your three options honestly: cloud AI upload (simplest, documents leave), hosted conversion API (documents leave, but to one vendor), local MCP (documents never leave — this server).

## FAQ

**Can we run document conversion for AI agents with no cloud at all?**
Yes for the documents unconditionally; fully — including the model — if you pair the server with a self-hosted LLM.

**Does the server open any ports?**
No. Stdio only; it is a child process of your AI client (or of your agent runtime / n8n).

**How do updates work in a restricted network?**
Pull the pinned image version in a controlled window, re-tag internally, and roll it out like any other container update.
