# 🏠 Dashy Homelab

Dashboard configuration for Robert's home server cluster.
**Dashy v4.2.4** running on both Pi4 (102) and Pi501-117.

**Portfolio**: https://robcarv.github.io
**Architecture**: https://robcarv.github.io/homelab-architecture

## 📋 Services

### Pi4 · 192.168.68.102
- Pi-hole (DNS Ad-blocker)
- Dashy (this dashboard)
- Nginx Proxy Manager (SSL reverse proxy)
- Wallos (subscription management)
- Glances (monitoring)

### Pi5-108 · 192.168.68.108
- AzuraCast (Dublin Calling radio)
- qBittorrent (download client)
- ClamAV (antivirus scanner)
- DuckDNS (dynamic DNS)
- IPRoyal (passive income)
- Duplicati (removed — not in use)
- Glances (monitoring)

### Pi501-117 · 192.168.68.117
- Dashy (dashboard mirror)
- Prowlarr (indexer manager)
- Radarr (movie manager)
- UptimeKuma (55+ service monitors)
- ChangeDetection (website change monitor)
- Speedtest Tracker
- Nginx Proxy Manager
- Wallos
- Glances
- Portainer agent

### TrueNAS · 192.168.68.124
- NVMe Storage Pool (10.9TB)
- Jellyfin (media server — 88 movies)
- CIFS Shares (shared storage)

## 🗂️ Structure

```
dashy/
├── conf.yml              # Main Dashy configuration
├── docker-compose.yml    # Compose for Dashy container
├── public/
│   └── conf.yml          # Deployed config (bind mount)
├── scripts/
│   ├── torrent_health.py      # Health check for torrents
│   ├── torrent_antivirus.sh   # ClamAV scan wrapper
│   ├── backup_pipeline.sh     # Full backup + health report
│   └── guardian.sh            # Load/memory monitor (cron 5min)
└── README.md
```

## 🚀 Usage

### Edit and update Dashy

```bash
# Edit conf.yml, then restart on both Pis:
cd ~/Documents/Docker/dashy && docker compose restart

# Sync to Pi4:
scp public/conf.yml robert@192.168.68.102:/home/robert/Documents/Docker/dashy/public/
ssh robert@192.168.68.102 'cd /home/robert/Documents/Docker/dashy && docker compose restart'
```

## 🔄 Auto-Update Flow

```
NewsBot (cron 08:00, 20:00)
  → Coleta RSS → Resume → Telegram
  → Exporta news.json → Push GitHub
  → Portfolio atualiza

Health Report (cron backup)
  → Métricas dos 3 Pis
  → health.json → Push GitHub
  → Portfolio atualiza

Backup (Seg/Qua/Sex 03:30)
  → ClamAV → Rsync → Health report → Git push
```
