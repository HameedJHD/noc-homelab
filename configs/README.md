# Configs

Sanitized configuration files from the lab. Comment lines and blank lines are
stripped so only active settings remain. Secrets are replaced with `CHANGE_ME`,
and MAC addresses are masked.

| Path | What it is |
|---|---|
| `proxmox/interfaces` | Host network config: bridge `vmbr0` on `nic0` |
| `proxmox/ubuntu-vendor.yaml` | cloud-init vendor snippet applied to every clone |
| `proxmox/vm-*.conf` | Proxmox VM definitions (template 9000, Zabbix 110, web 220) |
| `proxmox/zabbix_agent2.conf` | Agent on the Proxmox host (`Hostname=pve-kei`) |
| `mon-zabbix01/` | Zabbix server, agent and Nginx settings |
| `srv-web01/zabbix_agent2.conf` | Agent on the web server |

Not included: the Zabbix frontend config (`zabbix.conf.php`), which holds the
database password.