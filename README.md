# Linux Server Monitoring Stack

A complete server monitoring setup built on Ubuntu 24.04, featuring Prometheus, Node Exporter, and Grafana — with full security hardening.

## Architecture
```
Node Exporter (port 9100) → Prometheus (port 9090) → Grafana (port 3000)
```

## What This Project Covers

### Monitoring
- **Node Exporter** — collects server metrics (CPU, RAM, disk, network)
- **Prometheus** — scrapes and stores metrics every 15 seconds
- **Grafana** — visualizes data with professional dashboards

### Security Hardening
- **UFW Firewall** — deny all incoming, allow only SSH (22), Prometheus (9090), Node Exporter (9100), Grafana (3000)
- **Fail2Ban** — bans IPs after 5 failed SSH attempts for 1 hour
- **SSH Hardening** — key-only authentication, no root login, no password login, no X11 forwarding

## Installation

Each component was installed manually (not via Docker) to demonstrate Linux administration skills:

1. Created dedicated service users with no login shell
2. Installed binaries to `/usr/local/bin/`
3. Wrote custom systemd unit files
4. Configured UFW firewall rules
5. Set up Fail2Ban SSH jail
6. Hardened SSH configuration

## Configuration Files

All config files are in the `configs/` directory:
- `prometheus.yml` — Prometheus scrape configuration
- `node_exporter.service` — systemd unit for Node Exporter
- `prometheus.service` — systemd unit for Prometheus
- `jail.local` — Fail2Ban SSH jail configuration

## Skills Demonstrated

- Linux system administration (Ubuntu 24.04)
- systemd service management
- Firewall configuration (UFW)
- SSH security hardening
- Monitoring stack deployment
- User and permission management

## Screenshot

![Grafana Dashboard](screenshots/grafana-dashboard.png)

## Author

Dawid Kostka — aspiring Linux System Administrator based in Vienna, Austria.
