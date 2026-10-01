# Drive personal (Nextcloud en tu PC)

## Requisitos
- Docker Desktop (Windows/Mac) o Docker Engine (Linux)
- ≥ 20 GB libres en disco (recomendado 30 GB+)
- Cuenta gratuita de Cloudflare y un dominio (para acceso desde internet)

## Uso
1. `cp .env.example .env` y edita contraseñas.
2. Cloudflare Zero Trust → Networks → Tunnels → Create tunnel → copia el token a `TUNNEL_TOKEN`.
   En *Public hostname*: `drive.tudominio.com` → `HTTP` → `nextcloud:80`.
3. `docker compose up -d`
4. Local: http://localhost:8080 — Internet: https://drive.tudominio.com

## Sin dominio (solo red local o VPN)
Borra el servicio `tunnel`. Para acceso remoto privado usa Tailscale.

## Cuota de 20 GB
Ajustes → Usuarios → Cuota → 20 GB (o más). Sin cuota, usa todo el disco.

## Notas
- La PC debe estar encendida y con internet.
- Haz respaldo periódico de `data/`.
- Activa 2FA en Nextcloud (app "Two-Factor TOTP").
