# Joplin Server (SQLite)

Self-hosted sync server for Joplin notes app.

## Quick Start

```powershell
cd joplin-server-sqlite
docker compose up -d
```

## Access

- **URL**: http://localhost:22300
- **Admin Login**: admin@localhost / admin

## Usage

### Stop/Start

```powershell
# Stop
docker compose down

# Start
docker compose up -d

# Restart
docker compose restart
```

### View Logs

```powershell
docker compose logs -f
```

### Configuration

Edit `docker-compose.yml` to customize:
- Port: `22300`
- APP_BASE_URL: Set to your public domain for production

## Data

SQLite database is stored in the container. For production, consider:
- Adding a volume mount for persistence
- Using PostgreSQL instead (see Joplin docs)

## Connecting Clients

In Joplin Desktop/Mobile app:
1. Go to **Synchronisation** > ** Joplin Server**
2. Enter: `http://localhost:22300`
3. Login with your credentials

## Default Admin

- Email: admin@localhost
- Password: admin

**Change the default password after first login!**

## Unraid Template

An Unraid XML template is included: `joplin-server-sqlite.xml`

Generated using comp2unraid.

### Install on Unraid

1. Copy the XML to your Unraid server:
   ```
   /boot/config/plugins/dockerMan/templates-user/joplin-server-sqlite.xml
   ```

2. In Unraid Web UI, go to **Docker** > **Add Container**
3. Select template from dropdown

### Template Variables

| Variable | Default | Description |
|----------|--------|------------|
| WebUI Port | 22300 | Web UI port |
| APP_PORT | 22300 | Joplin app port |
| APP_BASE_URL | http://localhost:22300 | Base URL for sync |

## Support

- **Website**: https://joplinapp.org
- **Documentation**: https://joplinapp.org/server/
- **GitHub**: https://github.com/laurent22/joplin
- **Forum**: https://discourse.joplinapp.org
- **Discord**: https://discord.gg/2xZvsQU

## Troubleshooting

```powershell
# Check if running
docker ps | findstr joplin

# View logs
docker compose logs

# Rebuild and restart
docker compose down
docker compose pull
docker compose up -d
```