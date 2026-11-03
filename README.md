# NOC Homelab

A Proxmox-based lab that simulates day-to-day Network Operations Center work:
monitoring, alerting, incident triage, and documentation.

Built as preparation for a Network Operations Center (5G) role.

## Status

| Phase | Description | Status |
|---|---|---|
| 1 | Proxmox layout, cloud-init template, snapshots | Done |
| 2 | Zabbix monitoring + alerting | In progress |
| 3 | Network simulation (VLANs, SNMP, syslog) | Planned |
| 4 | Ticketing (osTicket/GLPI) and runbooks | Planned |
| 5 | 5G core (Open5GS + UERANSIM) | Stretch goal |

## Environment

- Host: Proxmox VE 9.2, Intel i5-8500 (6 cores), ~19 GB RAM, 1 TB SSD (LVM-thin)
- Guests: ID scheme by role (100s infra, 200s services, 300s network sim, 400s 5G, 9000+ templates)

| ID | Name | Role |
|---|---|---|
| 10 | fw-opnsense01 | Primary Edge Firewall / Core Router |
| 110 | mon-zabbix01 | Zabbix 7.0 LTS server (PostgreSQL, Nginx) |
| 220 | srv-web01 | Monitored web server |
| 9000 | tpl-ubuntu-2404 | Ubuntu 24.04 cloud-init template |

## What I did and learned

- [Phase 1: Proxmox foundation](docs/01-proxmox-foundation.md)
- [Phase 2: Zabbix monitoring](docs/02-zabbix-monitoring.md)
- [Troubleshooting log](docs/troubleshooting/)
- [Incident reports](docs/incidents/)
- [Runbooks](docs/runbooks/)

## Roadmap

(Short list of what's next.)