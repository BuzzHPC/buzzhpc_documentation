# Getting Started with the Buzz CLI

The `buzz` CLI lets you create and manage BuzzHPC cloud resources directly from your terminal — no browser required.

## Installation

=== "macOS (Apple Silicon)"
    ```bash
    curl -sSL https://github.com/BuzzHPC/buzz-cli/releases/latest/download/buzz-cli_Darwin_arm64.tar.gz | tar xz
    sudo mv buzz-cli /usr/local/bin/buzz
    ```

=== "macOS (Intel)"
    ```bash
    curl -sSL https://github.com/BuzzHPC/buzz-cli/releases/latest/download/buzz-cli_Darwin_amd64.tar.gz | tar xz
    sudo mv buzz-cli /usr/local/bin/buzz
    ```

=== "Linux (x86_64)"
    ```bash
    curl -sSL https://github.com/BuzzHPC/buzz-cli/releases/latest/download/buzz-cli_Linux_amd64.tar.gz | tar xz
    sudo mv buzz-cli /usr/local/bin/buzz
    ```

=== "Linux (ARM64)"
    ```bash
    curl -sSL https://github.com/BuzzHPC/buzz-cli/releases/latest/download/buzz-cli_Linux_arm64.tar.gz | tar xz
    sudo mv buzz-cli /usr/local/bin/buzz
    ```

=== "Windows"
    Download the latest `buzz-cli_Windows_amd64.zip` from [GitHub Releases](https://github.com/BuzzHPC/buzz-cli/releases/latest), extract it, and add `buzz-cli.exe` to your PATH (rename to `buzz.exe` for convenience).

=== "Install Script"
    ```bash
    curl -sSL https://raw.githubusercontent.com/BuzzHPC/buzz-cli/main/install.sh | bash
    ```

## Configuration

### Interactive Setup

Run `buzz configure` to interactively set your API key and default project:

```bash
buzz configure
```

This creates `~/.buzzhpc/config` with your settings.

### Environment Variables

```bash
export BUZZHPC_API_KEY=your-api-key
export BUZZHPC_PROJECT=your-project-name
export BUZZHPC_WORKSPACE=your-workspace-name   # optional
```

### Config File

`~/.buzzhpc/config`:
```yaml
api_key: your-api-key
project: your-project-name
workspace: your-workspace-name
```

### Priority Order

Flags > Environment Variables > Config File

## Authentication

Get your API key from the [BuzzHPC Console](https://console.buzzhpc.ai) under your account settings.

```bash
buzz --api-key YOUR_KEY devpod list
```

## Quick Start

```bash
# Configure once
buzz configure

# Create a DevPod with 1x H200 GPU
buzz devpod create --name my-pod --wait

# List all resources
buzz devpod list
buzz vm list
buzz k8s list

# Get detailed info
buzz devpod get my-pod
```

## Global Flags

| Flag | Short | Description |
|------|-------|-------------|
| `--api-key` | | BuzzHPC API key |
| `--project` | `-p` | Project name |
| `--workspace` | `-w` | Workspace name |
| `--base-url` | | API base URL (advanced) |

## Non-Interactive Mode

The CLI detects when running in CI/CD or scripts (no TTY) and will fail immediately instead of prompting, so pipelines never hang.

```bash
# Always works in CI
BUZZHPC_API_KEY=... BUZZHPC_PROJECT=... buzz devpod create --name ci-pod --no-deploy
```
