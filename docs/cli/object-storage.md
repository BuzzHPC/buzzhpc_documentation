---
title: CLI – Object Storage
description: Create and manage S3-compatible Object Storage buckets from the command line using the buzz CLI
tags:
  - CLI
  - Object Storage
  - S3
  - Command Line
---

Users can use the `buzz` CLI to create, list, inspect, and delete S3-compatible Object Storage buckets without using the web console.

**Aliases:** `s3`, `obs`, `bucket`

---

## List Buckets

```bash
buzz object-storage list
```

Returns all Object Storage buckets across all accessible workspaces.

```bash
buzz s3 list -w my-workspace
```

Filter by a specific workspace.

---

## Get Bucket Details

```bash
buzz object-storage get <name>
```

Returns full bucket details including status, SKU, datacenter, quota, bucket name, S3 endpoint URL, access key, and secret key.

**Example:**

```bash
buzz s3 get my-bucket
```

!!! info
    The `get` command is the easiest way to retrieve your S3 credentials and endpoint URL after a bucket has been deployed.

---

## Create a Bucket

```bash
buzz object-storage create --name <name> [flags]
```

The bucket is created and **deployed automatically**. Pass `--no-deploy` to create without deploying.

**Flags:**

| Flag | Description | Default |
|---|---|---|
| `-n, --name` | Name of the bucket **(required)** | — |
| `-s, --size` | Storage quota in GB | `10` |
| `--sku` | SKU: `object-storage-vast-ca-qc-2` (CA-QC-2) or `object-storage-vast` (CA-QC-1) | `object-storage-vast-ca-qc-2` |
| `--no-deploy` | Create without deploying | `false` |

**Examples:**

```bash
# Create a 10 GB bucket (default)
buzz s3 create --name my-bucket

# Create a 100 GB bucket
buzz s3 create --name my-bucket --size 100

# Create a large dataset bucket in CA-QC-1
buzz bucket create --name datasets --sku object-storage-vast --size 500

# Create without deploying
buzz s3 create --name my-bucket --no-deploy
```

---

## Delete a Bucket

```bash
buzz object-storage delete <name>
```

Prompts for confirmation before deleting. Pass `--force` or `-f` to skip.

```bash
buzz s3 delete my-bucket
buzz bucket delete my-bucket --force
```

!!! info
    Deleting a bucket is permanent and will remove all stored data. This action cannot be undone.
