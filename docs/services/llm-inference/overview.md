---
title: LLM Inference
description: Deploy and serve large language models with vLLM-powered GPU inference endpoints
tags:
  - LLM Inference
  - vLLM
  - AI Models
  - HuggingFace
  - Model Deployment
---

Deploy and serve large language models from HuggingFace with dedicated GPU resources powered by vLLM for high-performance inference.

---

## Overview

LLM Inference provides a fully managed service for deploying large language models with dedicated GPU resources. Built on vLLM, the service offers low-latency, high-throughput inference with automatic scaling and optimization.

---

## Key Features

### HuggingFace Integration

Deploy any model from HuggingFace's public or gated repositories. Support for:
- Public models (no authentication required)
- Gated models (requires HuggingFace token)
- Private models (requires HuggingFace token with appropriate access)

---

### Dedicated GPU Resources

Each LLM Inference deployment receives dedicated GPU resources billed per hour:
- NVIDIA H200 GPUs
- NVIDIA H100 GPUs
- Configurable GPU count (1, 2, 4, or 8 GPUs)

---

### Built-In Chat Interface

Interact with deployed models directly through the browser with a built-in chat interface:
- Real-time model responses
- Conversation history
- Copy/export capabilities
- Online status indicators

---

### vLLM Optimization

Powered by vLLM for optimized inference performance:
- PagedAttention for efficient memory management
- Continuous batching for high throughput
- Optimized CUDA kernels
- Support for quantized models

---

## Use Cases

Ideal for:
- Interactive chatbot applications
- Real-time inference workloads
- Model evaluation and testing
- Prototyping AI applications
- Low-latency AI assistants
- Custom LLM deployments

---

## Supported Models

Deploy popular models including:
- Llama-3.1 family (8B, 70B, 405B)
- Mistral models
- GPT-J and GPT-NeoX
- Falcon models
- Cohere Command models
- Any HuggingFace-compatible model

---

## Billing

LLM Inference deployments are billed hourly based on:
- GPU type selected (H200, H100)
- Number of GPUs allocated
- Runtime duration

Billing starts when the deployment reaches "Success" status and stops when the deployment is deleted.

!!! info
    Each deployment reserves dedicated GPU resources for maximum performance and predictable latency.

---
