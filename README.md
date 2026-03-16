# BuzzHPC Documentation

Official product documentation for the **BuzzHPC Cloud Platform** — a high-performance GPU cloud built for AI, ML, and compute-intensive workloads.

📖 **[View the docs →](https://buzzhpc.github.io/buzzhpc_documentation/)**

---

## What is BuzzHPC?

BuzzHPC is a GPU cloud platform that gives teams on-demand access to high-performance compute infrastructure. From individual developer pods to full Kubernetes clusters, BuzzHPC provides the tools to build, train, and deploy AI workloads at scale.

---

## What's in this documentation?

### Compute
How to provision and manage GPU-backed compute resources:
- **Developer Pods** — containerised GPU environments with SSH access for development and prototyping
- **GPU Virtual Machines** — full virtual machines with dedicated GPU, CPU, memory, and public IP
- **Managed Kubernetes** — one-click Kubernetes clusters provisioned on full GPU nodes
- **Baremetal** — dedicated bare metal GPU servers

### Services
Managed services that run on the platform:
- **LLM Inference** — deploy any HuggingFace model as a vLLM-powered inference endpoint
- **Jupyter Notebooks** — browser-accessible GPU notebooks with a public URL
- **Object Storage** — S3-compatible storage backed by VAST Data
- **Shared Filesystem** — NFS volumes mountable across pods and VMs

### CLI
The `buzz` command-line tool for managing all resources from the terminal:
- Installation for macOS, Linux, and Windows
- Authentication and configuration
- Full command reference for every resource type

### Terraform
Infrastructure-as-code for all BuzzHPC resource types using the official Terraform provider.

### Administration & Access Control
User management, roles, audit trails, and billing.

---

## Links

- **Documentation site:** https://buzzhpc.github.io/buzzhpc_documentation/
- **BuzzHPC Console:** https://cloud.buzzhpc.ai
- **buzz CLI releases:** https://github.com/BuzzHPC/buzz-cli/releases
