# Azure DevOps

> Manages your team's Azure DevOps projects through this assistant — work items, repositories, pull requests, pipelines, and wikis — without opening a browser. Needs your organisation name and an access token.

The bundle zip (**84.5 MB**) is stored in this repository at **`703d23d8-4397-470b-ad62-18e0d38a4cd9.zip`**.

This repository is part of the **Forjinn-Desk** MCP bundle collection. An MCP bundle is a self-contained server that a host application launches and communicates with over the MCP (Model Context Protocol) protocol.

## Repo metadata

| Field | Value |
| --- | --- |
| Registry ID | `703d23d8-4397-470b-ad62-18e0d38a4cd9` |
| Status in registry | active |
| Bundle size | 84.5 MB |
| Distribution | committed to this repo |

## Environment variables

| Variable | Value / note |
| --- | --- |
| `ADO_ORG` | `your-org` |
| `ADO_PAT` | `base64-encoded Personal Access Token` |
| `LOG_LEVEL` | `info` |

## MCP launch configuration

The host replaces `__INSTALL_DIR__` (install dir) and `__PYTHON__` (bundled Python) at runtime.

```json
{
  "command": "__INSTALL_DIR__\\node\\node.exe",
  "args": [
    "__INSTALL_DIR__\\dist\\index.js",
    "__ADO_ORG__",
    "--authentication",
    "pat"
  ],
  "env": {
    "PERSONAL_ACCESS_TOKEN": "__ADO_PAT__",
    "LOG_LEVEL": "info"
  }
}
```


## Install / usage

1. Get the bundle:
   - download `703d23d8-4397-470b-ad62-18e0d38a4cd9.zip` from this repo (Code → Download ZIP, or `git clone`).
2. Extract to your target installation directory (config paths expect contents at the install-dir root).
3. Set the environment variables listed above.
4. Launch using the MCP config JSON (or let a host client manage it automatically).

> Bundles may include vendored runtimes (bundled Python, Node, or native executables). Builds are Windows x64.
