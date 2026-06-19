# Dashy Homelab

Dashboard configuration for Robert's home server cluster.

**Dashy v4.2.4** running on both Pi4 and Pi501.

**Dashboards:**
- Pi501:8200 (local network)
- Pi4:8200 (local network)

**Portfolio:** https://robcarv.github.io

**Radio:** https://dublincalling.duckdns.org/public/dublincalling

## Sections (19)

| # | Section | Type |
|---|---------|------|
| 1 | Dublin Calling - Now Playing | Custom HTML/JS |
| 2 | Time & Weather | Clock + Weather widgets |
| 3 | Quick Tools | Links (CyberChef, JSON, Regex, etc.) |
| 4 | Social & News | Links (YouTube, LinkedIn, News) |
| 5 | Pi 4 | Services (Portainer, Pi-hole, NPM, Duplicati) |
| 6 | Pi 5 | Services (AzuraCast, Uptime Kuma, Changedetection) |
| 7 | TrueNAS | Services (Web UI, Jellyfin, Tailscale, SMB) |
| 8 | Pi 501 | Services (Dashy, Hermes, Speedtest, NPM) |
| 9 | IBM QE FTM | IBM work links (Jenkins, OpenShift, GitHub EE, RQM) |
| 10 | CPU Cores | Glances widget (3 Pis) |
| 11 | Memory Usage | Glances widget (3 Pis) |
| 12 | Temperature | Glances widget (3 Pis) |
| 13 | Disk Space | Glances widget (3 Pis) |
| 14 | CPU History | Glances widget (3 Pis) |
| 15 | Network Traffic | Glances widget (3 Pis) |
| 16 | System Alerts | Glances widget (3 Pis) |
| 17 | System Info | Uptime & Kernel widget (3 Pis) |
| 18 | Service Status | Stat-ping widgets (4 services) |
| 19 | Radio Schedule | Dublin Calling schedule |

## Widgets Used

- **Glances** (7 sections): `gl-current-cores`, `gl-current-mem`, `gl-cpu-temp`, `gl-disk-space`, `gl-cpu-history`, `gl-network-interfaces`, `gl-alerts` — all with `useProxy: true` + `apiVersion: 3`
- **System Info**: `system-info` via Glances proxy
- **Stat Ping**: `stat-ping` for critical service health checks
- **Clock + Weather**: `clock`, `weather`
- **Custom HTML/JS**: Now Playing radio widget with `<audio>` player

## Key Config

- Theme: Dracula
- Custom CSS: 4-column grid for large screens, 3-column for medium
- Status Check Interval: 60 seconds
- Font Awesome icons enabled
- Glances monitoring widgets (CPU, RAM, Temp, Disk) for all 3 Pis

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
- Tailscale (VPN)
- SMB Shares: Media, CloudBackup

## IBM QE FTM Section

22 links organized by category:
- **CI/CD**: QA Automation Jenkins, FTM Regression PL
- **Code**: GitHub Enterprise, FTM Dev Playbook
- **Quality**: Jazz RQM, Zenhub QA
- **Monitoring**: Instana, Bobalytics, FTM QA Dashboard
- **Platforms**: 5 OpenShift clusters
- **Tools**: Artifactory, UrbanCode Deploy
- **Internal**: w3, IBM Learning, IBM Docs, Fix Central, Concur

## Related Repositories

- [robcarv/robcarv](https://github.com/robcarv/robcarv) - Profile with full infrastructure docs
- [news_colletector](https://github.com/robcarv/news_colletector) - RSS news collector with TTS
- [azura-cast-customizations](https://github.com/robcarv/azura-cast-customizations) - AzuraCast theme
