# Shared Filesystem (CLI)

Manage NFS-backed Shared Filesystems using the `buzz shared-fs` command.

**Aliases:** `shared-fs`, `nfs`, `shared-filesystem`, `fs`

## Commands

| Command | Description |
|---------|-------------|
| `buzz shared-fs create` | Create and deploy a Shared Filesystem |
| `buzz shared-fs list` | List all Shared Filesystems |
| `buzz shared-fs get <name>` | Get filesystem details |
| `buzz shared-fs delete <name>` | Delete a Shared Filesystem |

## Create

```bash
buzz shared-fs create --name my-fs --size 50
buzz nfs create --name datasets --size 500
buzz fs create --name model-weights --size 200
buzz shared-fs create --name my-fs --no-deploy
buzz shared-fs create --name my-fs --wait
```

### Flags

| Flag | Default | Description |
|------|---------|-------------|
| `--name`, `-n` | required | Filesystem name |
| `--size`, `-s` | `50` | Volume size in GB |
| `--no-deploy` | | Create without deploying |
| `--wait` | | Wait until filesystem is ready |

## List

```bash
buzz shared-fs list
buzz nfs ls
```

## Get

```bash
buzz shared-fs get my-fs
buzz fs describe my-fs
```

Sample output:

```
FIELD          VALUE
Name           my-fs
Project        my-project
Workspace      default
Status         success
SKU            shared-filesystem
Size (GB)      500
Server IP      10.0.2.10
Mount Path     /exports/my-fs
Mount Command  mount -t nfs 10.0.2.10:/exports/my-fs /mnt
```

## Delete

```bash
buzz shared-fs delete my-fs
buzz nfs delete my-fs --force   # skip confirmation
```
