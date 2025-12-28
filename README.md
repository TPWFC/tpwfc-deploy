# TPWFC Deploy

Centralized deployment orchestration for TPWFC infrastructure.

## Services

| Service | Image | Port | Domain |
|---------|-------|------|--------|
| tpwfc-web | ghcr.io/tpwfc/tpwfc-web | 3000 | beta.tpwfc.com |
| tpwfc-discord-server | ghcr.io/tpwfc/tpwfc-discord-server | 3333 | server.tpwfc.com |
| cloudflared | cloudflare/cloudflared | - | - |

## Deployment

### Full Stack Deploy

Run the `Deploy All Services` workflow from GitHub Actions.

### Individual Service Deploy

- **Web only**: Push to `TPWFC/TPWFC` main branch
- **Server only**: Push to `TPWFC/tpwfc-bots` main branch

## Required Secrets

Add these to the `production` environment:

| Secret | Description |
|--------|-------------|
| `GH_TOKEN` | GitHub PAT for ghcr.io |
| `DEPLOY_HOST` | Server IP/hostname |
| `DEPLOY_USER` | SSH username |
| `DEPLOY_SSH_KEY` | Private SSH key |
| `CLOUDFLARE_TUNNEL_TOKEN` | Cloudflare tunnel token |
| `PAYLOAD_SECRET` | Payload CMS secret |
| `DISCORD_TOKEN` | Discord bot token |
