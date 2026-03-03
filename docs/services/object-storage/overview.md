---
title: Object Storage
description: S3-compatible object storage powered by VAST Data for scalable cloud storage
tags:
  - Object Storage
  - S3
  - VAST Data
  - Bucket Storage
  - API Access
---

Fully S3-compatible object storage backed by VAST Data, providing scalable, durable cloud storage with standard S3 APIs for seamless integration.

---

## Overview

Object Storage provides enterprise-grade S3-compatible storage backed by VAST Data's high-performance platform. Store and retrieve any amount of data using standard S3 APIs, SDKs, and tools.

---

## Key Features

### S3 Compatibility

Full compatibility with Amazon S3 API:
- Standard S3 operations (PUT, GET, DELETE, LIST)
- AWS SDK support (boto3, AWS CLI, etc.)
- S3-compatible tools (s3cmd, rclone, etc.)
- OpenAI-compatible API endpoints

---

### VAST Data Backend

Powered by VAST Data's enterprise storage platform:
- High durability and availability
- Low-latency object access
- Optimized for AI/ML workloads
- Enterprise-grade data protection

---

### Browser-Based Management

Manage your storage directly from the browser:
- Upload files through web interface
- Browse buckets and objects
- Download objects
- Delete objects
- View storage statistics

---

### Automatic Provisioning

One-click deployment automatically creates:
- S3 user account
- Dedicated bucket
- Access credentials (Access Key and Secret Key)
- API endpoint configuration

---

## Use Cases

Ideal for:
- Dataset storage and versioning
- Model artifact storage
- Application data storage
- Backup and archival
- Static website hosting
- Data lakes and analytics
- Multi-application data sharing

---

## S3 API Compatibility

Supports standard S3 operations:
- **list_buckets()** - List all buckets
- **put_object()** - Upload objects
- **get_object()** - Download objects
- **list_objects_v2()** - List bucket contents
- **delete_object()** - Delete objects
- **head_object()** - Get object metadata

---

## Access Methods

### Browser Interface

Upload, browse, and manage files directly through the Buzz HPC web console.

### Command-Line Tools

Use s3cmd, AWS CLI, or other S3-compatible tools for automation and scripting.

### Programmatic Access

Integrate with applications using AWS SDKs (boto3, AWS SDK for JavaScript, etc.).

---

## Security

- Secure HTTPS endpoints
- Access Key / Secret Key authentication
- IAM policy support
- Bucket-level permissions
- Encrypted data at rest

---

## Billing

Object Storage is billed based on:
- Allocated bucket quota (GB)
- Storage duration

Charges apply from creation until deletion of the storage instance.

!!! info
    Object Storage provides S3-compatible access without egress charges within the Buzz HPC platform.

---
