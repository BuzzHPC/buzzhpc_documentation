---
title: Shared File System
description: High-performance shared storage powered by VAST Data for GPU workloads
tags:
  - Shared Storage
  - VAST Data
  - NFS
  - Persistent Storage
  - GPU Workloads
---

High-performance shared file storage backed by VAST Data, enabling seamless data sharing across multiple GPU Virtual Machines and compute resources.

---

## Overview

Shared File System provides enterprise-grade network-attached storage that can be mounted to one or multiple GPU Virtual Machines simultaneously. Built on VAST Data's all-flash storage platform, it delivers the performance and reliability needed for demanding AI and HPC workloads.

---

## Key Features

### VAST Data Backend

Powered by VAST Data's high-performance storage platform:
- All-flash NVMe architecture
- Sub-millisecond latency
- High throughput for large datasets
- Enterprise-grade reliability and durability

---

### Multi-VM Access

Mount shared volumes to multiple GPU VMs concurrently:
- Centralized dataset storage
- Collaborative workflows
- Shared model repositories
- Consistent data access across environments

---

### Flexible Capacity

Configure storage quotas based on your data requirements:
- Customizable size allocations
- Pay for what you use
- Scale storage as needed

---

### Persistent Storage

Data persists independently of compute resources:
- Survive VM deletions
- Reattach to new VMs
- Long-term data retention
- Backup and snapshot support

---

## Use Cases

Ideal for:
- Shared training datasets across GPU VMs
- Centralized model checkpoints and weights
- Collaborative data science projects
- Persistent storage for AI/ML pipelines
- High-performance data lakes
- Shared code repositories and notebooks

---

## Integration with GPU VMs

Shared File System volumes can be attached to GPU Virtual Machines during creation or afterward. Multiple VMs can mount the same volume simultaneously for collaborative access.

See the **GPU VM User Guide** for instructions on mounting shared storage.

---

## Performance

VAST Data storage delivers:
- Low-latency access for GPU training workloads
- High sequential read/write throughput
- Optimized for large file operations
- Native support for AI/ML data patterns

---

## Billing

Shared File System is billed based on:
- Allocated storage quota (GB)
- Duration of storage allocation

Charges apply from creation until deletion, independent of actual data usage.

!!! info
    Storage costs are separate from compute (GPU VM) charges. You can resize quotas as your data needs change.

---
