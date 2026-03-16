---
title: CLI – Managed Kubernetes
description: Create and manage Managed Kubernetes clusters from the command line using the buzz CLI
tags:
  - CLI
  - Kubernetes
  - MKS
  - Command Line
---

Users can use the `buzz` CLI to create, list, inspect, and delete Managed Kubernetes clusters without using the web console.

**Aliases:** `k8s`, `mks`, `cluster`

!!! info
    Managed Kubernetes clusters are provisioned on full GPU nodes. You specify the node type and number of nodes — not individual GPU count.

---

## List Clusters

```bash
buzz k8s list
```

Returns all Kubernetes clusters across all accessible workspaces.

```bash
buzz k8s list -w my-workspace
```

Filter by a specific workspace.

---

## Get Cluster Details

```bash
buzz k8s get <name>
```

Returns full cluster details including status, SKU, GPU node type, node count, cluster name, and kubeconfig URL.

**Example:**

```bash
buzz k8s get my-cluster
```

---

## Create a Cluster

```bash
buzz kubernetes create --name <name> [flags]
```

The cluster is created and **deployed automatically**. Pass `--no-deploy` to create without deploying.

**Flags:**

| Flag | Description | Default |
|---|---|---|
| `-n, --name` | Name of the cluster **(required)** | — |
| `--node-type` | GPU node type: `H200`, `A40`, `H100`, `CPU` | `H200` |
| `--nodes` | Number of nodes | `1` |
| `--sku` | SKU: `mks-oneclick` (default), `mks-k8s-ca-qc-2`, `mks-k8s` | `mks-oneclick` |
| `--no-deploy` | Create without deploying | `false` |

**Examples:**

```bash
# Create a single-node H200 cluster
buzz k8s create --name my-cluster

# Create a 2-node A40 cluster
buzz k8s create --name my-cluster --node-type A40 --nodes 2

# Create a 4-node H200 cluster
buzz k8s create --name prod-cluster --node-type H200 --nodes 4

# Create without deploying
buzz k8s create --name my-cluster --no-deploy
```

---

## Delete a Cluster

```bash
buzz k8s delete <name>
```

Prompts for confirmation before deleting. Pass `--force` or `-f` to skip.

```bash
buzz cluster delete my-cluster
buzz k8s delete my-cluster --force
```

!!! info
    Deleting a cluster is permanent and will remove all workloads running on it.
