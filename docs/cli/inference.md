---
title: CLI – LLM Inference
description: Deploy and manage LLM Inference endpoints from the command line using the buzz CLI
tags:
  - CLI
  - LLM
  - Inference
  - vLLM
  - Command Line
---

Users can use the `buzz` CLI to deploy, list, inspect, and delete LLM inference endpoints powered by vLLM without using the web console. Any HuggingFace model is supported, including gated and private models.

**Aliases:** `llm`, `vllm`, `ai`

---

## List Inference Endpoints

```bash
buzz inference list
```

Returns all LLM inference endpoints across all accessible workspaces.

```bash
buzz llm list -w my-workspace
```

Filter by a specific workspace.

---

## Get Endpoint Details

```bash
buzz inference get <name>
```

Returns full details including status, SKU, GPU type, GPU count, model ID, endpoint URL, and API token.

**Example:**

```bash
buzz llm get my-llm
```

---

## Create an Inference Endpoint

```bash
buzz inference create --name <name> --model <huggingface-model-id> [flags]
```

The endpoint is created and **deployed automatically**. Pass `--no-deploy` to create without deploying.

**Flags:**

| Flag | Description | Default |
|---|---|---|
| `-n, --name` | Name of the endpoint **(required)** | — |
| `-m, --model` | HuggingFace model ID **(recommended)** | `facebook/opt-125m` |
| `--node-type` | GPU node type | `H200` |
| `--gpu-count` | Number of GPUs — use >1 for tensor parallelism | `1` |
| `--hf-token` | HuggingFace token for gated/private models | — |
| `--extra-args` | Extra vLLM CLI arguments | — |
| `--sku` | SKU: `inference-vllm-v1` (H200) or `inference-vllm-v1-h100` (A40/H100) | `inference-vllm-v1` |
| `--no-deploy` | Create without deploying | `false` |
| `--wait` | Wait until the endpoint is ready after deploying | `false` |

**Examples:**

```bash
# Deploy Llama 3.1 8B
buzz llm create --name my-llm --model meta-llama/Llama-3.1-8B-Instruct

# Deploy a gated model with HuggingFace token
buzz llm create --name my-llm --model meta-llama/Llama-3.1-8B-Instruct --hf-token hf_xxx

# Deploy a large model with tensor parallelism across 4 GPUs
buzz llm create --name big-model --model meta-llama/Llama-3.1-70B-Instruct --gpu-count 4

# Deploy with custom vLLM args
buzz llm create --name my-llm --model facebook/opt-125m --extra-args '--max-model-len 8192'

# Create without deploying
buzz ai create --name my-llm --model facebook/opt-125m --no-deploy

# Create and wait until ready
buzz llm create --name my-llm --model facebook/opt-125m --wait
```

!!! info
    Use `--gpu-count` greater than 1 to enable tensor parallelism for large models that do not fit on a single GPU.

---

## Delete an Inference Endpoint

```bash
buzz inference delete <name>
```

Before deleting, the CLI displays the current status and workspace and prompts for confirmation. Type `yes` or `y` to confirm. Pass `--force` or `-f` to skip.

```bash
buzz llm delete my-llm
buzz ai delete my-llm --force
```