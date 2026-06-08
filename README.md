# 🏠 Dashy Homelab

Dashboard configuration for Robert's home server cluster.

## Services

### Pi 4 · 192.168.68.102
- Pi-hole (DNS Ad-blocker)
- Dashy (this dashboard)
- Uptime Kuma (monitoring)
- Duplicati (backups)

### Pi 5 · 192.168.68.108
- AzuraCast (radio streaming)
- Whisparr (media manager)
- Prowlarr (indexer manager)
- qBittorrent (torrent client)
- ChangeDetection (website monitoring)

### Pi 501 · 192.168.68.117
- Hermes Agent (AI assistant)
- Dashy (dashboard mirror)

### TrueNAS · 192.168.68.124
- NVMe Storage Pool (10.9TB)
- Jellyfin (media streaming)
- Immich (photo backup)
- Tailscale (VPN)

## Structure

- `conf.yml` — Main DashY configuration file
- `public/` — Assets and backups

## Usage

Edit `conf.yml` and restart Dashy:

```bash
docker restart Dashy
```

Or copy to the RPi4:

```bash
scp conf.yml robert@192.168.68.102:/home/robert/Documents/Docker/dashy/public/
ssh robert@192.168.68.102 'docker restart Dashy'
```
