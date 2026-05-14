---
id: command-line-interface
url: conversion/python-net/getting-started/command-line-interface
title: Command Line Interface
linkTitle: Command Line Interface
second_title: Convert documents from the terminal with the groupdocs-conversion CLI
weight: 6
keywords: command line, CLI, terminal, groupdocs-conversion, convert documents, shell, pipeline, CI, batch conversion, document info, supported formats, GroupDocs.Conversion, python
description: "Convert documents straight from the terminal with the groupdocs-conversion command-line tool — no Python script required. Inspect documents, list supported formats, and apply a license, all from the shell."
productName: GroupDocs.Conversion for Python via .NET
hideChildren: False
toc: True
---

Installing the `groupdocs-conversion-net` package also puts a `groupdocs-conversion` console script on your `PATH`. It is a thin wrapper over the Python API, built for the cases where spinning up a Python script is overkill — shell pipelines, Make rules, CI steps, and one-off conversions.

## Prerequisites

The CLI ships inside the package, so no extra installation is needed. Make sure `groupdocs-conversion-net` is installed (see the [Quick Start Guide]({{< ref "conversion/python-net/getting-started/quick-start-guide.md" >}})), then verify the console script is available:

```bash
groupdocs-conversion --version
```

You should see the package version printed, for example `groupdocs-conversion 26.5.0`.

{{< alert style="info" >}}
If the `groupdocs-conversion` command is not found, the package's script directory may not be on your `PATH`. You can always invoke the CLI through the Python module form instead: `python -m groupdocs.conversion`. The two are equivalent.
{{< /alert >}}

## Commands

The CLI exposes four subcommands. Run `groupdocs-conversion --help` for the full flag listing, or `groupdocs-conversion <command> --help` for a specific subcommand.

### convert

Convert a document to another format. The target format is inferred from the output file extension; pass `--format` to override it.

```bash
# Extension picks the target format
groupdocs-conversion convert business-plan.docx business-plan.pdf

# Override the format when the output name doesn't carry a usable extension
groupdocs-conversion convert business-plan.docx output.bin --format pdf

# Convert a single page (1-indexed) — useful for raster targets
groupdocs-conversion convert annual-review.pdf page1.png --page 1 --count 1

# Open a password-protected source
groupdocs-conversion convert protected.docx protected.pdf --password "secret"
```

| Option | Description |
| :- | :- |
| `--format` | Target format token (overrides the output extension). |
| `--password` | Password for a protected source document. |
| `--page` | First page to convert, 1-indexed. |
| `--count` | Number of pages to convert. |

On success the command prints the output path and exits with code `0`.

### info

Print basic information about a document — format, size, page count, and creation date when available.

```bash
groupdocs-conversion info annual-review.pdf
```

```text
format:         pdf
size:           291788
pages_count:    10
```

Use `--password` for protected sources.

### list-formats

List every target format the engine can produce for a given input document, split into primary and secondary targets.

```bash
groupdocs-conversion list-formats business-plan.docx
```

Use `--password` for protected sources.

### list-all-formats

Print the full source-to-target conversion matrix known to the engine — every input format and the targets it can be converted to.

```bash
groupdocs-conversion list-all-formats
```

This command takes no input file.

## Global options

These options apply to every command:

| Option | Description |
| :- | :- |
| `--license PATH` | Apply a license file before running the command. |
| `--version` | Print the CLI version and exit. |
| `--help` | Show usage help and exit. |

Apply a license up front by placing `--license` before the subcommand:

```bash
groupdocs-conversion --license GroupDocs.Conversion.lic convert business-plan.docx business-plan.pdf
```

{{< alert style="info" >}}
The CLI also honours the `GROUPDOCS_LIC_PATH` environment variable — if it is set, the license is applied automatically and you can omit `--license`. See the [Licensing]({{< ref "conversion/python-net/getting-started/licensing-and-subscription.md" >}}) topic for details.
{{< /alert >}}

## Format tokens

`convert` maps the output extension — or the `--format` value, lowercased — to the matching convert options and file type. The supported tokens are:

| Category | Tokens |
| :- | :- |
| PDF | `pdf` |
| Word processing | `doc`, `docx`, `rtf`, `odt`, `txt`, `md` |
| Spreadsheet | `xls`, `xlsx`, `xlsm`, `ods`, `csv`, `tsv` |
| Presentation | `ppt`, `pptx`, `pptm`, `odp` |
| Web | `html`, `htm`, `mhtml` |
| Image | `jpg`, `jpeg`, `png`, `bmp`, `gif`, `tiff`, `tif`, `webp`, `svg` |
| eBook | `epub`, `mobi`, `azw3` |

An unknown token causes the command to exit with code `2` and print the list of accepted tokens.

## Exit codes

| Code | Meaning |
| :- | :- |
| `0` | Success. |
| `2` | User error — unknown format token or missing input file. |
| `1` | Runtime error — the underlying .NET exception message is printed to standard error. |

These codes make the CLI easy to branch on in shell scripts and CI pipelines.

## When to use the Python API instead

The CLI covers the common single-document conversion cases. For anything beyond that — per-page callbacks, in-memory streams, watermark, font, or cell-range options, and multi-document container hierarchies — use the Python API directly. It exposes a richer surface than the CLI flags. See the [Developer Guide]({{< ref "conversion/python-net/developer-guide" >}}) for the full feature set.

## Next Steps

- [Quick Start Guide]({{< ref "conversion/python-net/getting-started/quick-start-guide.md" >}}): Convert your first document with the Python API.
- [Supported File Formats]({{< ref "conversion/python-net/getting-started/supported-document-formats.md" >}}): Review the full list of supported file types.
- [Licensing]({{< ref "conversion/python-net/getting-started/licensing-and-subscription.md" >}}): Apply a license to remove evaluation limits.
- [Technical Support]({{< ref "conversion/python-net/technical-support" >}}): Contact support if you encounter issues.
