# gohcloud
This repository contains the setup and projects for my home server, **gohcloud**.

## Motivation
The primary reason for creating a home server was to host my personal cloud storage and manage various other self-hosted projects efficiently.

---

## Server Specifications
For this setup, I'm using a compact mini-PC with the following specs:

- **Processor**: Intel Core i5-1220P (10 cores / 12 threads)
- **Memory**: 24 GB LPDDR5 RAM
- **Boot Drive**: 256 GB SSD
- **Storage Drive**: 1 TB SSD

> *Note*: This type of mini-PC can easily be purchased from Amazon or similar retailers.

---

## Server Setup
I installed [OpenMediaVault](https://www.openmediavault.org/) (OMV) as the operating system to replace Windows. This setup leverages OMV’s capabilities for NAS (Network Attached Storage) management and provides a streamlined Docker environment.

To manage and deploy my projects, I use the **OMV Docker Compose [plugin](https://wiki.omv-extras.org/doku.php?id=omv6:omv6_plugins:docker_compose)**, which simplifies Docker management and deployment within OpenMediaVault.

---

## Cloud Storage
For personal cloud storage, I am using **Nextcloud**. It allows me to securely store and access my documents and media, providing full control over my data.

### Remote Access to gohcloud
When I’m outside my home network, I connect to gohcloud using [Tailscale](https://tailscale.com/), which provides a secure VPN connection. This setup allows me to:

- Access and manage my server remotely
- Retrieve documents and media from Nextcloud seamlessly

### Configuring Tailscale for Nextcloud Access
To enable Nextcloud access from outside the network, Tailscale needs to advertise the appropriate routes as a subnet router. Set the following in Tailscale to define the necessary routes:

```bash
TS_ROUTES=192.168.x.x/24
