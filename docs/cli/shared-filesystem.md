---
title: CLI – Shared Filesystem
description: Create and manage Shared NFS Filesystems from the command line using the buzz CLI
tags:
  - CLI
  - Shared Filesystem
  - NFS
  - Command Line
---

Users can use the `buzz` CLI to create, list, inspect, and delete Shared Filesystems (NFS) without using the web console. Shared Filesystems can be mounted across multiple pods and VMs simultaneously.

**Aliases:** `nfs`, `fs`, `shared-filesystem`

---

## List Filesystems

```bash
buzz shared-fs list
```

Returns all Shared Filesystems across all accessible workspaces.

```bash
buzz fs list -w my-workspace
```

Filter by a specific workspace.

---

## Get Filesystem Details

```bash
buzz shared-fs get <name>
```

Returns full details including status, size, server IP, mount path, and a ready-to-use mount command.

**Example:**

```bash
buzz fs get my-fs
```

Once deployed, mount the filesystem on any Linux host:

```bash
mount -t nfs <server-ip>:<mount-path> /mnt
```

The exact mount command is shown in the output of `buzz fs get <name>`.

---

## Create a Filesystem

```bash
buzz shared-fs create --name <name> [flags]
```

The filesystem is created and **deployed automatically**. Pass `--no-deploy` to create without deploying.

**Flags:**

| Flag | Description | Default |
|---|---|---|
| `-n, --name` | Name of the filesystem **(required)** | — |
| `-s, --size` | Volume size in GB | `50` |
| `--no-deploy` | Create without deploying | `false` |

**Examples:**

```bash
# Create a 50 GB filesystem (default)
buzz shared-fs create --name my-fs

# Create a 500 GB dataset volume
buzz nfs create --name datasets --size 500

# Create a large model weights volume
buzz fs create --name model-weights --size 200

# Create without deploying
buzz shared-fs create --name my-fs --no-deploy
```

---

## Delete a Filesystem

```bash
buzz shared-fs delete <name>
```

Prompts for confirmation before deleting. Pass `--force` or `-f` to skip.

```bash
buzz nfs delete my-fs
buzz fs delete my-fs --force
```

!!! info
    Deleting a shared filesystem is permanent. Ensure all pods and VMs have unmounted the filesystem before deleting to avoid errors.
