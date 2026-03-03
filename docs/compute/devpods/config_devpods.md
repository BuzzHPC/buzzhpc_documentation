---
title: DevPods User Guide
description: Step-by-step guide for creating and using DevPods on Buzz HPC.
tags:
  - DevPods
  - Self Service
---

Users can configure, deploy, and remotely access GPU-enabled developer pods.

---

## Create DevPod

Navigate to **Compute > DevPods** in the left menu, then click **+ Create**.

![DevPods List](img/devpods/view_devpods.png)

---

## Select Compute Profile

Choose a compute profile. Two profile types are available:

- **Serverless** profiles - On-demand GPU access (e.g., Serverless Developer Pods - CA-QC-2)
- **Dedicated** profiles - Reserved GPU capacity (e.g., Serverless Developer Pods - CA-QC-1, Dedicated)

Then select the workspace for the DevPod.

![Select Profile](img/devpods/create_devpod_profile.png)

---

## Configure DevPod

### Basic Configuration

- **DevPod Name** *(required)* - Enter a unique name (e.g., `my-devpod-1`)
- **Description** *(optional)* - Add a description

![Basic Configuration](img/devpods/create_devpod_basic.png)

---

### Container Configuration

Select the **Pod Image** for the DevPod environment. Available options:
- **Ubuntu 24-04** (default) - Ubuntu 24.04 LTS with GPU drivers

![Container Configuration](img/devpods/create_devpod_container.png)

---

### SSH Access

- **Autogenerate SSH Key** - Set to **Yes** (default) for auto-generated SSH key pair, or **No** to use your own key.
- **Public Key** - Paste your SSH public key if not auto-generating.

![SSH Access](img/devpods/create_devpod_ssh.png)

---

### Pod Resources

| Field | Description |
|-------|-------------|
| **GPU Type** | NVIDIA GPU model (H200, NVIDIA A40, NVIDIA H100 - depends on profile) |
| **GPU Count** | Number of GPUs |
| **CPU** | CPU in millicores. Default: 1000m |
| **Memory** | Memory in MiB. Default: 1024 MiB |

![Pod Resources](img/devpods/create_devpod_resources.png)

---

### Billing Information

After selecting GPU type and count, billing information and quota limits are displayed.

!!! info
    DevPods are metered by the hour.

![Billing Information](img/devpods/create_devpod_billing.png)

Click **Create** to provision the DevPod.

---

## View DevPods

All DevPods are listed under **Compute > DevPods**:

| Column | Description |
|--------|-------------|
| **Name** | DevPod identifier |
| **Workspace** | Associated workspace |
| **Profile** | Compute profile used |
| **Status** | Success, Pending, Failed, or Cancelled |
| **Created At** | Creation time |
| **Actions** | Edit or Delete |

![View DevPods](img/devpods/view_devpods.png)

---

## DevPod Detail View

Click on a DevPod name to see its details including Name, Workspace, Compute Profile, Compute Type, Status, Reason, and Action.

![DevPod Detail](img/devpods/devpod_detail.png)

---

## Specification Panel

Shows the resource configuration:

| Field | Description |
|-------|-------------|
| **GPU Type** | GPU model allocated (e.g., A40) |
| **GPU Count** | Number of GPUs |
| **Pod Image** | Container image (e.g., ubuntu-24-04-ssh-pod:v1) |
| **Autogenerate SSH Key** | true or false |
| **CPU** | CPU allocation in millicores |
| **Memory** | Memory allocation in MiB |
| **Public Key** | SSH public key (or "Not set") |

![Specification](img/devpods/devpod_specification.png)

---

## Stats Panel

Provides SSH connection details:

| Field | Description |
|-------|-------------|
| **Profile Name** | Compute profile identifier |
| **Create Private Key File** | View, copy, or download the auto-generated SSH private key |
| **SSH Command** | Pre-built SSH command for immediate connection |

### Connecting via SSH

```bash
ssh -i <devpod-name>-ssh.key ubuntu@<ip-address> -p <port>
```

Set correct permissions before connecting:

```bash
chmod 600 <devpod-name>-ssh.key
ssh -i <devpod-name>-ssh.key ubuntu@<ip-address> -p <port>
```

![Stats Panel](img/devpods/devpod_stats.png)

---

## Re-publish DevPod

Click **Re-publish** to re-apply the DevPod configuration or recover from a failed state.

---

## Delete DevPod

Click the **delete icon** (red trash bin) in the Actions column to delete a DevPod.

!!! warning
    Deleting a DevPod is permanent. Ensure you have saved any important work before deleting.

---
