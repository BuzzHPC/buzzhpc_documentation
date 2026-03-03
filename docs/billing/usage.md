---
title: Billing & Usage
description: Monitor resource usage, view costs, and manage billing
tags:
  - Billing
  - Usage
  - Costs
  - Metering
---

Track resource usage, monitor costs, and manage billing for your Buzz HPC account.

---

## Overview

The Billing & Usage dashboard provides real-time visibility into resource consumption and associated costs across all services.

---

## Accessing Billing & Usage

Navigate to **Billing & Usage** in the left menu.

![Billing Dashboard](img/billing/billing_dashboard.png)

---

## Usage Dashboard

### Current Period Summary

View current billing period metrics:
- Total costs to date
- GPU hours consumed
- Storage usage
- Top spending resources

### Resource Breakdown

Detailed usage by resource type:
- GPU Virtual Machines
- DevPods
- LLM Inference
- Managed Kubernetes
- Object Storage
- Shared File System

### Cost Trends

Visualize spending patterns:
- Daily cost chart
- Weekly/monthly trends
- Cost by service
- Cost by workspace

---

## Usage Reports

### Generate Reports

Create custom usage reports:

1. Select date range
2. Choose resource types
3. Select workspaces
4. Click **Generate Report**

### Export Data

Export usage data for analysis:
- CSV format
- JSON format
- PDF invoices

![Usage Reports](img/billing/usage_reports.png)

---

## Resource Metering

### GPU Resources

Billed by the hour based on:
- GPU type (H200, H100, A40)
- Number of GPUs
- Runtime duration

### Storage

Billed based on:
- Allocated capacity (GB)
- Duration

### LLM Inference

Billed per hour based on:
- GPU type and count
- Deployment duration

---

## Cost Optimization

### Recommendations

- Stop unused GPU VMs
- Delete idle LLM deployments
- Right-size storage quotas
- Use dedicated profiles for long-running workloads

### Alerts

Set up cost alerts:
- Budget thresholds
- Usage limits
- Spending notifications

---
