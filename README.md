# AI-BOM Toolkit

A toolkit and visualizer for **AI Bill of Materials** (AI-BOM). Pipe any CycloneDX AI-BOM JSON into the `aibom` CLI and get an interactive constellation graph.

[![npm](https://img.shields.io/npm/v/aibom)](https://www.npmjs.com/package/aibom)
[![license](https://img.shields.io/npm/l/aibom)](packages/aibom/LICENSE)
[![codecov](https://img.shields.io/codecov/c/gh/lirantal/aibom/main)](https://codecov.io/gh/lirantal/aibom)
[![CI](https://img.shields.io/github/actions/workflow/status/lirantal/aibom/ci.yml?branch=main&label=CI&logo=github)](https://github.com/lirantal/aibom/actions/workflows/ci.yml?query=branch%3Amain)
[![Known Vulnerabilities](https://snyk.io/test/github/lirantal/aibom/badge.svg)](https://snyk.io/test/github/lirantal/aibom)
[![Security Responsible Disclosure](https://img.shields.io/badge/Security-Responsible%20Disclosure-yellow)](packages/aibom/SECURITY.md)

TL;DR how to use AI-BOM:

```sh
snyk aibom --experimental --json | npx aibom --view
```

_What it does: Snyk generates a CycloneDX AI-BOM as JSON, which is piped into the `aibom` CLI. The `--view` flag opens an interactive HTML visualization of your AI bill of materials in the browser._

<img width="1280" height="1280" alt="screenshot-rocks Large" src="https://github.com/user-attachments/assets/82f356c3-b41c-4aec-8d41-613b1e4d0bbd" />

## Deployed Version

The AI-BOM Visualizer project is also deployed live here for public use: [https://ai-bom-visualizer.vercel.app](https://ai-bom-visualizer.vercel.app)

## Quickstart for AI BOM Visualizer package

To visualize your AI-BOM in your own local environment, pipe a valid CycloneDX JSON data to the `aibom` npm CLI utility as follows:

```sh
cat data.json | npx aibom --view
```

If you're using Snyk to create an AI-BOM:

```sh
snyk aibom --experimental --json | npx aibom --view
```

## Quickstart for Developers of AI BOM Visualizer website

```bash
npm install
npm run dev      # http://localhost:5173
npm run build    # → dist/index.html (single file, all assets inlined)
npm run preview  # preview production build
```

Default BOM comes from **`data.json`** at project root (injected into the HTML at build time); edit it and rebuild to change the default graph. See [docs/project.md](docs/project.md) for build and data source details. To build a data-free viewer for another project to inject their BOM later, use **`npm run build:template`** — see [docs/html-template.md](docs/html-template.md).

## Features

| Feature | Description |
|--------|-------------|
| [Constellation layout](docs/feature/constellation-layout.md) | Radial/orbital graph, rings by type, dashboard cards, legend |
| [Search](docs/feature/search.md) | Fuzzy filter by name/type; ⌘K / Ctrl+K to focus |
| [Zoom](docs/feature/zoom.md) & [Zoom to fit](docs/feature/zoom-to-fit.md) | Pan/zoom canvas; fit-all and reset |
| [Show JSON](docs/feature/show-json.md) | Raw CycloneDX panel + copy to clipboard |
| [Upload JSON](docs/feature/json-upload.md) | Load another AI-BOM file from disk |
| [Components legend](docs/feature/components-legend.md) | Collapsible type legend |
| [Dashboard stats](docs/feature/dashboard-cards-stats.md) | Component counts by type |
| [Logo](docs/feature/logo.md) | Evo by Snyk branding in header |

## Tech

React, TypeScript, Vite, Tailwind. Single-file output via [vite-plugin-singlefile](https://github.com/richardtallent/vite-plugin-singlefile).
