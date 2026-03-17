# Jupyter Notebooks (CLI)

Manage Jupyter Notebook services using the `buzz notebook` command.

**Aliases:** `notebook`, `nb`, `jupyter`

## Commands

| Command | Description |
|---------|-------------|
| `buzz notebook create` | Create and deploy a Notebook |
| `buzz notebook list` | List all Notebooks |
| `buzz notebook get <name>` | Get Notebook details |
| `buzz notebook delete <name>` | Delete a Notebook |

## Create

```bash
buzz notebook create --name my-notebook
buzz nb create --name my-notebook --no-deploy
buzz notebook create --name my-notebook --wait
```

### Flags

| Flag | Default | Description |
|------|---------|-------------|
| `--name`, `-n` | required | Notebook name |
| `--sku` | | SKU override |
| `--no-deploy` | | Create without deploying |
| `--wait` | | Wait until Notebook is ready |

## List

```bash
buzz notebook list
buzz nb ls
```

## Get

```bash
buzz notebook get my-notebook
buzz nb describe my-notebook
```

Sample output:

```
FIELD      VALUE
Name       my-notebook
Project    my-project
Workspace  default
Status     success
SKU        jupyter-notebook
URL        https://my-notebook.notebooks.buzzhpc.ai
```

## Delete

```bash
buzz notebook delete my-notebook
buzz nb delete my-notebook --force
```
