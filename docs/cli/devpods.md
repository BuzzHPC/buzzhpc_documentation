# Developer Pods (CLI)

Manage GPU-backed Developer Pods using the `buzz devpod` command.

**Aliases:** `devpod`, `pod`, `pods`, `devpods`

## Commands

| Command | Description |
|---------|-------------|
| `buzz devpod create` | Create and deploy a DevPod |
| `buzz devpod list` | List all DevPods |
| `buzz devpod get <name>` | Get DevPod details |
| `buzz devpod delete <name>` | Delete a DevPod |

## Create

```bash
buzz devpod create --name my-pod
buzz pod create --name my-pod --node-type H100 --gpu-count 2
buzz devpod create --name my-pod --wait
buzz devpod create --name my-pod --no-deploy
```

### Flags

| Flag | Default | Description |
|------|---------|-------------|
| `--name`, `-n` | required | DevPod name |
| `--sku` | `managed-developer-pods-v2-ca-qc-2` | SKU (H200 region default) |
| `--node-type` | `H200` | GPU node type |
| `--gpu-count` | `1` | Number of GPUs |
| `--no-deploy` | | Create without deploying |
| `--wait` | | Wait until DevPod is ready |

## List

```bash
buzz devpod list
buzz pod ls
```

## Get

```bash
buzz devpod get my-pod
buzz devpod describe my-pod
```

Sample output:

```
FIELD        VALUE
Name         my-pod
Project      my-project
Workspace    default
Status       success
GPU Count    1
GPU Type     H200
Pod Image    pytorch:2.3
SSH Command  ssh -i ~/.ssh/id_buzz user@10.0.1.45 -p 22
```

If an SSH private key is available, the CLI will print the command to save it.

## Delete

```bash
buzz devpod delete my-pod
buzz devpod delete my-pod --force   # skip confirmation
```

Before deleting, the CLI shows the pod's current status, GPU configuration, and workspace.
