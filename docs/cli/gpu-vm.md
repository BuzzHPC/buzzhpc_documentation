---
title: CLI – GPU Virtual Machines
description: Create and manage GPU Virtual Machines from the command line using the buzz CLI
tags:
  - CLI
  - GPU VM
  - Virtual Machine
  - Command Line
---

Users can use the `buzz` CLI to create, list, inspect, and delete GPU Virtual Machines without using the web console.

**Aliases:** `gpu-vm`, `virtual-machine`

---

## List VMs

```bash
buzz vm list
```

Returns all GPU VMs across all accessible workspaces.

```bash
buzz vm list -w my-workspace
```

Filter by a specific workspace.

---

## Get VM Details

```bash
buzz vm get <name>
```

Returns full VM details including:

| Field | Description |
|---|---|
| SKU | Compute profile name |
| GPU Model | GPU hardware model |
| GPU Count | Number of GPUs |
| CPU Count | Number of vCPUs |
| Memory | RAM in GB |
| Disk | Storage in GB |
| Datacenter | Region |
| OS | Operating system |
| Username | SSH login username |
| Password | SSH login password |
| Public IP | External IP address |
| Private IP | Internal network IP |
| SSH Port | SSH port |

**Example:**

```bash
buzz vm get my-vm
```

---

## Create a VM

```bash
buzz vm create --name <name> [flags]
```

The VM is created and **deployed automatically**. Pass `--no-deploy` to create without deploying.

**Flags:**

| Flag | Description | Default |
|---|---|---|
| `-n, --name` | Name of the VM **(required)** | — |
| `--node-type` | GPU node type: `H200`, `A40` | `H200` |
| `--gpu-count` | Number of GPUs | `1` |
| `--sku` | Compute profile SKU | `no-gpu-vm` |
| `--no-deploy` | Create without deploying | `false` |
| `--wait` | Wait until the VM is ready after deploying | `false` |

**Examples:**

```bash
# Create a VM with defaults
buzz vm create --name my-vm

# Create a VM with 2x H200 GPUs
buzz gpu-vm create --name my-vm --node-type H200 --gpu-count 2

# Create without deploying
buzz vm create --name my-vm --no-deploy

# Create and wait until ready
buzz vm create --name my-vm --wait
```

---

## Delete a VM

```bash
buzz vm delete <name>
```

Before deleting, the CLI displays the current status and workspace and prompts for confirmation. Type `yes` or `y` to confirm. Pass `--force` or `-f` to skip.

```bash
buzz vm delete my-vm
buzz vm delete my-vm --force
```

!!! info
    Deleting a VM is permanent. Any data stored on the VM that has not been backed up will be lost.