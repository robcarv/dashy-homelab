# Dashy Homelab

Dashboard configuration for Robert's home server cluster.

**Dashy v4.2.4** running on both Pi4 (192.168.68.102) and Pi501 (192.168.68.117).

**Dashboards:**
- Pi501: http://192.168.68.117:8200
- Pi4: http://192.168.68.102:8200

**Portfolio:** https://robcarv.github.io

**Radio:** https://dublincalling.duckdns.org/public/dublincalling

## Infrastructure Overview

### Pi4 - 192.168.68.102
- Pi-hole (DNS Ad-blocker)
- Dashy (Dashboard)
- Nginx Proxy Manager (SSL Reverse Proxy)
- Wallos (Subscription Management)
- Glances (System Monitoring)
- Duplicati (Backups)

### Pi5 - 192.168.68.108
- AzuraCast (Dublin Calling Radio)
- Uptime Kuma (Service Monitoring)
- Changedetection (Website Monitoring)
- qBittorrent (Download Client)
- Glances (System Monitoring)

### Pi501 - 192.168.68.117
- Dashy (Dashboard)
- Hermes Agent (AI CLI Agent)
- Speedtest Tracker (Network Monitoring)
- Discount Bandit (Deal Monitor)
- Nginx Proxy Manager (Reverse Proxy)

### TrueNAS Scale - 192.168.68.124
- NVMe Pool 10.9TB
- Jellyfin (Media Server)
- Immich (Photo Management)
- Tailscale (VPN)
- SMB Shares: Media, CloudBackup

## Key Config

- Theme: Dracula
- Custom CSS: 4-column grid for large screens, 3-column for medium
- Status Check Interval: 60 seconds
- Font Awesome icons enabled
- Glances monitoring widgets (CPU, RAM, Temp, Disk) for all 3 Pis

## Related Repositories

- [robcarv/robcarv](https://github.com/robcarv/robcarv) - Profile with full infrastructure docs
- [news_colletector](https://github.com/robcarv/news_colletector) - RSS news collector with TTS
- [azura-cast-customizations](https://github.com/robcarv/azura-cast-customizations) - AzuraCast theme
