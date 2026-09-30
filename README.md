# NOVA MOTORS

Catálogo web de vehículos premium creado con React, Vite y Lucide React.

## Desarrollo local

```bash
npm install
npm run dev
```

Validaciones de producción:

```bash
npm run lint
npm run build
```

## Publicación en Oracle Cloud con Nginx

La VM debe tener abiertos los puertos TCP `22` y `80` en la lista de seguridad de Oracle Cloud. Después de conectarse por SSH:

```bash
sudo apt-get update
sudo apt-get install -y nginx git npm
sudo rm -rf /var/www/html/*
git clone --depth 1 https://github.com/Gaforsix777/OracleCloudPrueba.git /tmp/novamotors
cd /tmp/novamotors
npm install
npm run build
sudo cp -r dist/. /var/www/html/
sudo nginx -t
sudo systemctl reload nginx
```

La aplicación se sirve desde `/var/www/html`. Para comprobarla desde la VM:

```bash
curl http://localhost
```
