---
title: Baremetal as a Service
description: Dedicated bare metal GPU servers with direct hardware access for maximum HPC and AI performance.
tags:
  - Baremetal
  -   - Dedicated Servers
      -   - NVIDIA H200
          -   - HPC
              -   - AI Training
                  - ---

                  Dedicated bare metal GPU servers with direct hardware access, delivering maximum performance without virtualization overhead.

                  ---

                  ## Performance

                  ### No Virtualization Overhead
                  Direct physical hardware access eliminates hypervisor overhead, providing the highest possible GPU compute performance.

                  ---

                  ### Latest GPU Hardware
                  Access NVIDIA H200 GPU servers configured as dedicated resources exclusively for your workload.

                  ---

                  ## Infrastructure

                  ### Dedicated Hardware
                  Each bare metal instance is a fully dedicated physical server with no resource sharing with other tenants.

                  ---

                  ### Tenant Networking (TAN)
                  Built-in Tenant Area Network support for high-performance networking between bare metal instances and other cloud resources.

                  ---

                  ### Cloud-Init Support
                  Supports cloud-init YAML for automated server provisioning - configure users, install packages, and run scripts at boot time.

                  ---

                  ## Networking

                  ### Multi-Firewall Support
                  Integration with enterprise firewall vendors:
                  - **Juniper** (vSRX mode)
                  - - **Fortinet** (FortiManager mode)
                    - - **Palo Alto Networks** (Panorama mode)
                     
                      - ---

                      ## Automation

                      ### Workflow Engine
                      Configurable workflow engine for automated provisioning. Default workflow: `deploy_vm`.

                      ---

                      ## Use Cases

                      Ideal for:
                      - Maximum GPU throughput for LLM training
                      - - Low-latency distributed training
                        - - Custom kernel modules or specialized drivers
                          - - Compliance requiring dedicated isolated hardware
                            - - HPC workloads requiring direct hardware access
                             
                              - ---

                              ## Billing

                              Bare metal instances are billed as dedicated reserved resources.

                              !!! info
                                  Bare metal instances are available as dedicated resources. Contact your Buzz HPC account team for pricing and availability.
                              
