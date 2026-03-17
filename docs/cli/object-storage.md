# Object Storage (CLI)

Manage S3-compatible Object Storage buckets using the `buzz object-storage` command.

**Aliases:** `object-storage`, `obs`, `s3`, `bucket`

## Commands

| Command | Description |
|---------|-------------|
| `buzz object-storage create` | Create and deploy Object Storage |
| `buzz object-storage list` | List all Object Storage services |
| `buzz object-storage get <name>` | Get Object Storage details |
| `buzz object-storage delete <name>` | Delete Object Storage |

## Create

```bash
buzz object-storage create --name my-bucket
buzz s3 create --name my-bucket --no-deploy
buzz object-storage create --name my-bucket --wait
```

### Flags

| Flag | Default | Description |
|------|---------|-------------|
| `--name`, `-n` | required | Bucket name |
| `--sku` | | SKU override |
| `--no-deploy` | | Create without deploying |
| `--wait` | | Wait until storage is ready |

## List

```bash
buzz object-storage list
buzz s3 ls
```

## Get

```bash
buzz object-storage get my-bucket
buzz s3 describe my-bucket
```

Sample output:

```
FIELD            VALUE
Name             my-bucket
Project          my-project
Workspace        default
Status           success
SKU              object-storage
Endpoint         https://my-bucket.s3.buzzhpc.ai
Access Key       AKIAIOSFODNN7EXAMPLE
Secret Key       wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
```

## Delete

```bash
buzz object-storage delete my-bucket
buzz s3 delete my-bucket --force
```
