# Bitwarden on docker behind traefik

## Environment Variables
* Replace values in `.env`
```
SERVICE=bitwarden
DOMAIN_NAME=site.mydomain.com
SERVICE_PORT=80
WEBSOCKET_PORT=3012
TZ=Europe/Berlin
TOKEN=your-generated-token
```

Generate admin token:
```bash
openssl rand -base64 48
```
