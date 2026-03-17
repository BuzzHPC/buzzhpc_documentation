# GPU Virtual Machines (CLI)

Manage GPU Virtual Machines using the `buzz vm` command.

**Aliases:** `vm`, `gpu-vm`, `virtual-machine`

## Commands

| Command | Description |
|---------|-------------|
| `buzz vm create` | Create and deploy a GPU VM |
| `buzz vm list` | List all GPU VMs |
| `buzz vm get <name>` | Get VM details |
| `buzz vm delete <name>` | Delete a GPU VM |

## Create

```bash
buzz vm create --name my-vm
buzz gpu-vm create --name my-vm --node-type H200 --gpu-count 2
buzz vm create --name my-vm --no-deploy
buzz vm create --name my-vm --wait
```

### Flags

| Flag | Default | Description |
|------|---------|-------------|
| `--name`, `-n` | required | VM name |
| `--sku` | `no-gpu-vm` | SKU |
| `--node-type` | `H200` | GPU node type: `H200` |
| `--gpu-count` | `1` | Number of GPUs |
| `--no-deploy` | | Create without deploying |
| `--wait` | | Wait until VM is ready |

## List

```bash
buzz vm list
buzz gpu-vm ls
```

## Get

```bash
buzz vm get my-vm
buzz vm describe my-vm
```

Sample output:

```
FIELD          VALUE
Name           my-vm
Project        my-project
Workspace      default
Status         success
SKU            h200-1gpu-vm
GPU Model      H200
GPU Count      1
CPU Count      16
Memory         128 GB
Disk (GB)      500
Datacenter     ca-qc-2
OS             Ubuntu 22.04
Username       ubuntu
Password       ••••••••
Private IP     10.0.1.100
Public IP      203.0.113.5
SSH Port       22
SSH Command    ssh ubuntu@203.0.113.5 -p 22
```

## Delete

```bash
buzz vm delete my-vm
buzz vm delete my-vm --force   # skip confirmation
```

The CLI shows the current VM status and workspace before prompting for confirmation.
