# Managed Kubernetes (CLI)

Manage Managed Kubernetes (MKS) clusters using the `buzz k8s` command.

**Aliases:** `kubernetes`, `k8s`, `mks`, `cluster`

## Commands

| Command | Description |
|---------|-------------|
| `buzz k8s create` | Create and deploy a cluster |
| `buzz k8s list` | List all clusters |
| `buzz k8s get <name>` | Get cluster details |
| `buzz k8s delete <name>` | Delete a cluster |
| `buzz k8s labels <name>` | List labels on a cluster |
| `buzz k8s label <name> key=value` | Add or remove a label |

## Create

```bash
buzz k8s create --name my-cluster
buzz k8s create --name my-cluster --node-type A40 --nodes 2
buzz k8s create --name my-cluster --node-type H200 --nodes 4
buzz k8s create --name my-cluster --wait
buzz k8s create --name my-cluster --no-deploy
```

### Flags

| Flag | Default | Description |
|------|---------|-------------|
| `--name`, `-n` | required | Cluster name |
| `--sku` | `mks-oneclick` | SKU: `mks-oneclick`, `mks-k8s-ca-qc-2`, `mks-k8s` |
| `--node-type` | `H200` | GPU node type: `H200`, `A40`, `H100`, `CPU` |
| `--nodes` | `1` | Number of nodes |
| `--no-deploy` | | Create without deploying |
| `--wait` | | Wait until cluster is ready |

## List

```bash
buzz k8s list
buzz mks ls
```

## Get

```bash
buzz k8s get my-cluster
buzz k8s describe my-cluster
```

Sample output:

```
FIELD           VALUE
Name            my-cluster
Project         my-project
Workspace       default
Status          success
SKU             mks-oneclick
GPU Type        H200
Nodes           2
Cluster Name    my-cluster-abc123
Kubeconfig URL  https://...
Node List       node1,node2
```

## Delete

```bash
buzz k8s delete my-cluster
buzz k8s delete my-cluster --force   # skip confirmation
```

The CLI shows the current status and workspace before prompting for confirmation. Type `yes` or `y` to proceed.

## Labels

Labels are key/value pairs attached to a cluster. They appear in the console under the cluster's Labels tab and can be used for organization, cost allocation, and filtering.

### List Labels

```bash
buzz k8s labels my-cluster
```

```
KEY     VALUE
------  -----------
env     production
team    ml
```

### Add a Label

```bash
buzz k8s label my-cluster env=production
buzz k8s label my-cluster team=ml
```

### Remove a Label

```bash
buzz k8s label my-cluster env=production --remove
```
