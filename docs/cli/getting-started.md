---
title: CLI – Getting Started
description: Install and configure the buzz CLI to manage BuzzHPC resources from the command line
tags:
  - CLI
  - Command Line
  - buzz
---

Users can use the `buzz` CLI to create, manage, and delete BuzzHPC resources directly from the command line — without using the web console. All resource types are supported: Developer Pods, GPU Virtual Machines, Managed Kubernetes clusters, Jupyter Notebooks, LLM Inference endpoints, Object Storage buckets, and Shared Filesystems.

---

## Installation

=== "macOS"

    **One-line installer (recommended):**

    ```bash
    curl -fsSL https://raw.githubusercontent.com/BuzzHPC/buzz-cli/main/install.sh | sh
    ```

    **Manual download:**

    Download the appropriate archive from the [latest release](https://github.com/BuzzHPC/buzz-cli/releases/latest):

    | Chip | File |
    |---|---|
    | Apple Silicon (M1/M2/M3/M4) | `buzz_*_darwin_arm64.tar.gz` |
    | Intel | `buzz_*_darwin_amd64.tar.gz` |

    ```bash
    tar -xzf buzz_*_darwin_*.tar.gz
    sudo mv buzz /usr/local/bin/buzz
    ```

=== "Linux"

    **One-line installer (recommended):**

    ```bash
    curl -fsSL https://raw.githubusercontent.com/BuzzHPC/buzz-cli/main/install.sh | sh
    ```

    **Manual download:**

    Download the appropriate archive from the [latest release](https://github.com/BuzzHPC/buzz-cli/releases/latest):

    | Architecture | File |
    |---|---|
    | x86_64 | `buzz_*_linux_amd64.tar.gz` |
    | ARM64 | `buzz_*_linux_arm64.tar.gz` |

    ```bash
    tar -xzf buzz_*_linux_*.tar.gz
    sudo mv buzz /usr/local/bin/buzz
    ```

=== "Windows"

    Download `buzz_*_windows_amd64.zip` from the [latest release](https://github.com/BuzzHPC/buzz-cli/releases/latest), extract it, and add `buzz.exe` to your PATH.

---

## Verify Installation

```bash
buzz --version
```

---

## Authentication

Set your API key as an environment variable — it will be used automatically for every command:

```bash
export BUZZHPC_API_KEY=your-api-key
```

!!! info
    Your API key can be found in the BuzzHPC console under Administration. Never share or commit your API key to source control.

Alternatively, pass the key directly on any command:

```bash
buzz --api-key your-api-key vm list
```

---

## Configuration

| Environment Variable | Description |
|---|---|
| `BUZZHPC_API_KEY` | Your BuzzHPC API key **(required)** |
| `BUZZHPC_PROJECT` | Default project name (auto-detected if not set) |
| `BUZZHPC_WORKSPACE` | Default workspace (optional — defaults to all workspaces) |
| `BUZZHPC_BASE_URL` | Override the API base URL (advanced) |

---

## Configuration File

Instead of setting environment variables every time, save your settings to `~/.buzzhpc/config` using the interactive configure command:

```bash
buzz configure
```

This prompts for your API key, project, and base URL, then saves them to `~/.buzzhpc/config`:

```yaml
api_key: your-api-key
project: my-project
base_url: ""
```

Settings are loaded automatically on every command. Priority order (highest wins): flags > environment variables > config file.

---

## Global Flags

These flags are available on every command:

```
--api-key string     BuzzHPC API key (or set BUZZHPC_API_KEY)
--base-url string    API base URL (or set BUZZHPC_BASE_URL)
-p, --project string     Project name (or set BUZZHPC_PROJECT)
-w, --workspace string   Workspace name (or set BUZZHPC_WORKSPACE)
-h, --help               Help for any command
-v, --version            Print CLI version
```

---

## Available Commands

| Command | Aliases | Description |
|---|---|---|
| `buzz devpod` | `pod`, `pods`, `devpods` | Manage Developer Pods |
| `buzz vm` | `gpu-vm`, `virtual-machine` | Manage GPU Virtual Machines |
| `buzz kubernetes` | `k8s`, `mks`, `cluster` | Manage Managed Kubernetes clusters |
| `buzz notebook` | `nb`, `jupyter` | Manage Jupyter Notebooks |
| `buzz inference` | `llm`, `vllm`, `ai` | Manage LLM Inference endpoints |
| `buzz object-storage` | `s3`, `obs`, `bucket` | Manage Object Storage buckets |
| `buzz shared-fs` | `nfs`, `fs`, `shared-filesystem` | Manage Shared Filesystems |
| `buzz configure` | — | Save API key and settings to ~/.buzzhpc/config |

Each command supports four subcommands: `list`, `get`, `create`, `delete`.

All create commands support:

- `--wait` — poll until the resource is fully ready (or failed) before returning
- `--no-deploy` — create the resource without deploying it

---

## Workspaces

By default, `list` commands return resources from **all workspaces** the API key has access to. Use `-w` to filter to a specific workspace:

```bash
buzz vm list                   # all workspaces
buzz vm list -w my-workspace    # specific workspace
```

Create, get, and delete commands will prompt you to specify a workspace if you have more than one. Pass `-w` to skip the prompt:

```bash
buzz devpod create --name my-pod -w my-workspace
```

---

## Next Steps

- [Developer Pods](devpods.md)
- [GPU Virtual Machines](gpu-vm.md)
- [Managed Kubernetes](kubernetes.md)
- [Jupyter Notebooks](notebooks.md)
- [LLM Inference](inference.md)
- [Object Storage](object-storage.md)
- [Shared Filesystem](shared-filesystem.md)