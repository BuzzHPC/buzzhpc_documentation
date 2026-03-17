---
title: CLI – Developer Pods
description: Create and manage Developer Pods from the command line using the buzz CLI
tags:
  - CLI
  - DevPods
  - Command Line
---

Users can use the `buzz` CLI to create, list, inspect, and delete Developer Pods without using the web console.

**Aliases:** `pod`, `pods`, `devpods`

---

## List Pods

```bash
buzz devpod list
```

Returns all Developer Pods across all accessible workspaces.

```bash
buzz devpod list -w my-workspace
```

Filter by a specific workspace.

---

## Get Pod Details

```bash
buzz devpod get <name>
```

Returns full details for a pod including status, GPU type, GPU count, pod image, SSH command, and connection credentials.

**Example:**

```bash
buzz devpod get my-pod
```

---

## Create a Pod

```bash
buzz devpod create --name <name> [flags]
```

The pod is created and **deployed automatically**. Pass `--no-deploy` to create without deploying.

**Flags:**

| Flag | Description | Default |
|---|---|---|
| `-n, --name` | Name of the DevPod **(required)** | — |
| `--node-type` | GPU node type | `H200` |
| `--gpu-count` | Number of GPUs | `1` |
| `--sku` | SKU: `managed-developer-pods-v2-ca-qc-2` (H200) or `managed-developer-pods-v2` (A40/H100) | `managed-developer-pods-v2-ca-qc-2` |
| `--no-deploy` | Create resource without deploying | `false` |
| `--wait` | Wait until the pod is ready after deploying | `false` |

**Examples:**

```bash
# Create a pod with defaults (1x H200 GPU)
buzz devpod create --name my-pod

# Create a pod with 2x H100 GPUs
buzz pod create --name my-pod --node-type H100 --gpu-count 2

# Create without deploying
buzz devpod create --name my-pod --no-deploy

# Create and wait until ready
buzz devpod create --name my-pod --wait
```

---

## Delete a Pod

```bash
buzz devpod delete <name>
```

Before deleting, the CLI displays the current status and workspace and prompts for confirmation. Type `yes` or `y` to confirm. Pass `--force` or `-f` to skip.

```bash
buzz devpod delete my-pod
buzz devpod delete my-pod --force
```

!!! info
    Deleting a pod is permanent and cannot be undone.