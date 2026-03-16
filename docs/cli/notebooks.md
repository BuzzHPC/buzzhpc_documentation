---
title: CLI – Jupyter Notebooks
description: Create and manage Jupyter Notebooks from the command line using the buzz CLI
tags:
  - CLI
  - Notebooks
  - Jupyter
  - Command Line
---

Users can use the `buzz` CLI to create, list, inspect, and delete Jupyter Notebook instances without using the web console.

**Aliases:** `nb`, `jupyter`

!!! info
    Each notebook is automatically assigned a public URL at `https://<name>.notebook.buzzperformancecloud.com`. The notebook name becomes the URL subdomain.

---

## List Notebooks

```bash
buzz notebook list
```

Returns all Notebooks across all accessible workspaces, including their public URL.

```bash
buzz notebook list -w my-workspace
```

Filter by a specific workspace.

---

## Get Notebook Details

```bash
buzz notebook get <name>
```

Returns full details including status, SKU, GPU count, GPU type, container image, access URL, and authentication token.

**Example:**

```bash
buzz notebook get my-nb
```

---

## Create a Notebook

```bash
buzz notebook create --name <name> [flags]
```

The notebook is created and **deployed automatically**. Pass `--no-deploy` to create without deploying.

**Flags:**

| Flag | Description | Default |
|---|---|---|
| `-n, --name` | Name of the notebook — also sets the URL subdomain **(required)** | — |
| `--node-type` | GPU node type | `H200` |
| `--gpu-count` | Number of GPUs | `1` |
| `--image` | Jupyter container image | `jupyter/minimal-notebook:latest` |
| `--sku` | SKU: `jupyter-notebook-v4-ca-qc-2` (H200) or `jupyter-notebook-v4` (A40/H100) | `jupyter-notebook-v4-ca-qc-2` |
| `--no-deploy` | Create without deploying | `false` |

**Examples:**

```bash
# Create a notebook with defaults
buzz notebook create --name my-nb

# Create with 2x H100 GPUs and scipy image
buzz jupyter create --name my-nb --node-type H100 --gpu-count 2 --image jupyter/scipy-notebook:latest

# Create without deploying
buzz notebook create --name my-nb --no-deploy
```

After deployment, access your notebook at:
```
https://my-nb.notebook.buzzperformancecloud.com
```

---

## Delete a Notebook

```bash
buzz notebook delete <name>
```

Prompts for confirmation before deleting. Pass `--force` or `-f` to skip.

```bash
buzz nb delete my-nb
buzz notebook delete my-nb --force
```
