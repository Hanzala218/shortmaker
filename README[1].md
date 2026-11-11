# Viral Shorts Maker - Deploy guide

## Local test
    pip install -r backend/requirements.txt   (FFmpeg bhi install ho)
    cd backend && python app.py      -> http://127.0.0.1:5000

## Live deploy (Ubuntu VPS, 4+ vCPU / 8 GB RAM recommended)
1. Domain ka A-record server IP par point karein. Ports 80 aur 443 khule hon.
2. Docker install karein: curl -fsSL https://get.docker.com | sh
3. Is folder ko server par copy karein, phir:
       cp .env.example .env     # DOMAIN aur baaki values edit karein
       docker compose up -d --build
4. https://aapka-domain par site khul jayegi (HTTPS automatic, Caddy se).
5. Logs: docker compose logs -f app

## Zaroori
- Terms of Service aur Privacy Policy page banayein (user uploads/links store hote hain, 24h baad delete).
- Public launch se pehle ACCESS_CODE ke sath beta test karein.
- CPU par 1 ghante ki video ko kai minute lagte hain; users zyada hon to GPU server aur MAX_WORKERS badhayein.
