MAP: 06_APP_QB_ORACLE
==============
De volledige broncode van de QB Oracle app (Quality Builds).

Live app: https://app.qualitybuilds.nl
VPS: Hetzner | IP: 5.75.154.99 | Ubuntu 22.04

Bestanden:
- server.py            → Flask backend (alle API endpoints, 82963 bytes, bijgewerkt 10-05-2026)
- app.html             → mobiele veld-app (Maurice + Bryan, 92056 bytes, bijgewerkt 10-05-2026)
- config.json          → lokale config | ⚠️ BEVAT SMTP WACHTWOORD – Fase 2 secrets-architectuur plannen
- config_vps.json      → VPS config (wordt als config.json geupload) | ⚠️ idem
- manifest.json        → PWA configuratie
- sw.js                → service worker (offline gebruik)
- favicon.png          → app favicon
- logo.png             → QB logo header
- icon-192.png         → PWA icon
- icon-512.png         → PWA icon groot
- START_ORACLE_LOKAAL.bat → lokale Flask dev-server starten (poort 5050, test)
- 07_REPORTING_AND_BI/ → QB GODMODE Dashboard (HTML)
- SCREENSHOTS_REVIEW/  → dagelijkse UI review screenshots (per datum)
- API - SOAP e-Boekhouden BryandeVries.png → SOAP API referentiekaart

Deploy-map (deploy/):
  • UPLOAD.cmd               = DUBBELKLIK VOOR ELKE DEPLOY (hoofd-commando)
  • UPLOAD.ps1               = onderliggend PowerShell deploy-script
  • SYNC_WR_HISTORISCH.cmd   = eenmalig: sync historische WR PDFs naar VPS
  • SYNC_WR_HISTORISCH.ps1   = onderliggend script voor WR sync
  • EENMALIGE_SETUP.cmd      = één keer uitvoeren voor PowerShell-config
  • MIGRATIE_SSH_KEY.cmd     = SSH-key setup (eenmalig)
  • SSH_KEY_SETUP.md         = SSH-key handleiding
  • SSL_INSTELLEN.bat        = SSL-cert aanvragen (via SSH-key)
  • PULL_VPS_DATA.cmd        = VPS data ophalen (debug)
  • deploy.sh                = VPS init-script | ⚠️ bevat SMTP wachtwoord hardcoded

Deployen:
  1. Eenmalig: dubbelklik deploy/EENMALIGE_SETUP.cmd
  2. Eenmalig: volg deploy/SSH_KEY_SETUP.md
  3. Elke deploy: dubbelklik deploy/UPLOAD.cmd

Herstarten VPS: ssh root@5.75.154.99 → systemctl restart qb-oracle
