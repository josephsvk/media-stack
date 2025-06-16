

## Toto je **fork originálneho repozitára** [navilg/media-stack](https://github.com/navilg/media-stack), ktorý slúži ako **základná self-hosted media stack** (Sonarr, Radarr, qBittorrent, Prowlarr...) :contentReference[oaicite:6]{index=6}.

## 🛠 Úpravy vo vetve `joseph-overrides`

### 📂 docker-compose.override.yml
- +bazarr
- +recyclarr
- +flaresolverr
- Pridáva svoje mounty pre `config/`, `media/`, `downloads/`
- Nastavuje práva PUID/PGID podľa `TZ` a prostredia
- Pripravuje priestor pre vlastné služby (napr. backup, monitorovanie)

### 🧬 custom.env
- Definuje premenné `MEDIA_PATH`, `TZ=Europe/Prague`, `PUID`, `PGID`
- Slúži na izoláciu citlivých nastavení mimo opakovaných commitov

### 🔧 setup.sh
- Vytvára potrebné priečinky (config, media, downloads)
- Nastavuje vlastníka a skupinu súborov
- Spúšťa `docker compose up` s tvojimi nastaveniami
