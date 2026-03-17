# LLM Inference (CLI)

Manage LLM Inference services using the `buzz inference` command.

**Aliases:** `inference`, `infer`, `llm`

## Commands

| Command | Description |
|---------|-------------|
| `buzz inference create` | Create and deploy an Inference service |
| `buzz inference list` | List all Inference services |
| `buzz inference get <name>` | Get Inference service details |
| `buzz inference delete <name>` | Delete an Inference service |

## Create

```bash
buzz inference create --name my-llm --model llama3-70b
buzz llm create --name my-llm --model mistral-7b
buzz inference create --name my-llm --no-deploy
buzz inference create --name my-llm --wait
```

### Flags

| Flag | Default | Description |
|------|---------|-------------|
| `--name`, `-n` | required | Service name |
| `--model` | | Model to deploy |
| `--sku` | | SKU override |
| `--no-deploy` | | Create without deploying |
| `--wait` | | Wait until service is ready |

## List

```bash
buzz inference list
buzz llm ls
```

## Get

```bash
buzz inference get my-llm
buzz llm describe my-llm
```

## Delete

```bash
buzz inference delete my-llm
buzz inference delete my-llm --force
```
