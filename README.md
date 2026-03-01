# the-lab
Building a self-hosted, self-managed, over-engineered infrastructure playground, simply because I can

## Folder Structure

    the-lab
    ├── _docs/                          # Documentation for setup and management
    │   ├── basics/                     # Node setup, cluster bootstrapping, and maintenance guides
    │   ├── tasks/                      # Step-by-step guides for deploying specific tools and services
    │   ├── 1. branching-strategy.md    # Git branching strategy
    │   ├── 2. environment-infra-breakdown.md  # Environment and infrastructure overview
    │   └── 3. module-breakdown.md      # Terraform module breakdown
    ├── ansible/                        # Ansible playbooks for k3s cluster lifecycle management
    │   ├── provision/                  # Playbooks for provisioning and bootstrapping k3s nodes
    │   ├── join-cloud-nodes/           # Playbooks for joining OCI/GCP instances as k3s worker nodes
    │   └── teardown/                   # Playbooks for draining and removing nodes from the cluster
    ├── cloud-infra/                    # Terraform code for provisioning cloud resources
    │   ├── oci/                        # OCI free tier resource provisioning (compute, networking, etc.)
    │   ├── gcp/                        # GCP free tier resource provisioning
    │   └── other/                      # Any other free tier cloud provider resources
    ├── k3s-cluster/                    # Terraform code for managing homelab k3s cluster workloads
    │   ├── cluster-configs/            # Authentication and access files (e.g., kube-config)
    │   ├── cluster-templates/          # Reusable Terraform modules for k3s cluster resources
    │   ├── jenkins-jobs/               # Jenkins CI/CD pipeline configurations
    │   ├── management/                 # Terraform config for the management namespace
    │   ├── monitoring/                 # Terraform config for the monitoring namespace
    │   ├── prod-lab/                   # Terraform config for the prod-lab namespace
    │   └── dev-lab/                    # Terraform config for the dev-lab namespace
    └── README.md                       # Project overview and setup instructions

## Homelab Tools

### Management (`management` namespace)

| Tool                  | Purpose                                                                 |
| --------------------- | ----------------------------------------------------------------------- |
| Jenkins               | CI/CD pipelines for automating infrastructure deployments               |
| Harbor                | Self-hosted container image registry                                    |
| Traefik               | Ingress controller and reverse proxy for cluster traffic routing        |
| CertManager           | Automated TLS certificate management (Let's Encrypt)                    |
| ArgoCD                | GitOps-based continuous delivery for Kubernetes                         |
| Longhorn              | Distributed block storage for persistent volumes                        |
| Nginx Proxy Manager   | GUI-based reverse proxy for managing external access to services        |
| HashiCorp Vault       | Secrets management and encryption                                       |
| CrowdSec              | Collaborative intrusion detection and threat blocking                   |

### Monitoring (`monitoring` namespace)

| Tool                  | Purpose                                                                 |
| --------------------- | ----------------------------------------------------------------------- |
| Kube-Prometheus Stack      | Cluster metrics collection, alerting, and Grafana dashboards                  |
| FluentBit                  | Lightweight log forwarding from nodes and pods to OpenSearch                  |
| OpenSearch                 | Distributed log storage, search, and analytics engine                         |
| OpenSearch Dashboard       | Web UI for visualizing and querying logs stored in OpenSearch                 |
| ntopng                     | Network traffic analysis and monitoring                                       |
| OneUpTime / UptimeKuma     | Uptime monitoring, leveraging cloud-nodes for external reachability           |

### Production Homelab (`prod-lab` namespace)

| Tool                  | Purpose                                                                           |
| --------------------- | --------------------------------------------------------------------------------- |
| AdGuard Home          | Network-wide DNS-based ad and tracker blocking                                    |
| Homepage              | Self-hosted dashboard for accessing all homelab services                          |
| Actual Budget         | Self-hosted personal finance and budgeting tool                                   |
| Outline               | Self-hosted knowledge base and documentation wiki                                 |
| Nextcloud             | Self-hosted cloud storage, calendar, and collaboration platform                   |
| Arr Suite + qBittorrent | Automated media management (Sonarr, Radarr, Prowlarr, etc.) with torrent client |
| n8n                   | Self-hosted workflow automation and integration platform                          |
| Minecraft Server      | Containerized Minecraft server                                                    |

### Dev Lab (`dev-lab` namespace)

| Tool                  | Purpose                                                                                                   |
| --------------------- | --------------------------------------------------------------------------------------------------------- |
| Various               | Sandbox environment for testing and experimenting with new homelab tools before adopting them in prod-lab |

## Getting Started

To get started with the-lab repository, refer to the documentation in the `_docs` folder.