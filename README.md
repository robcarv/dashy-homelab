# Dashy Homelab

Dashboard configuration for Robert's home server cluster.

**Dashy v4.2.4** running on both Pi4 and Pi501.

**Dashboards:**
- Pi501:8200 (local network)
- Pi4:8200 (local network)

**Portfolio:** https://robcarv.github.io

**Radio:** https://dublincalling.duckdns.org/public/dublincalling

## Infrastructure Overview

### Pi4
- Pi-hole (DNS Ad-blocker)
- Dashy (Dashboard)
- Nginx Proxy Manager (SSL Reverse Proxy)
- Wallos (Subscription Management)
- Glances (System Monitoring)
- Duplicati (Backups)

### Pi5
- AzuraCast (Dublin Calling Radio)
- Uptime Kuma (Service Monitoring)
- Changedetection (Website Monitoring)
- qBittorrent (Download Client)
- Glances (System Monitoring)

### Pi501
- Dashy (Dashboard)
- Hermes Agent (AI CLI Agent)
- Speedtest Tracker (Network Monitoring)
- Discount Bandit (Deal Monitor)
- Nginx Proxy Manager (Reverse Proxy)

### TrueNAS Scale
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
