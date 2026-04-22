# Joplin Server

Self-hosted sync server for Joplin notes app with PostgreSQL.

## Quick Start

```powershell
cd joplin-server
docker compose -f stack.yml up -d
```

## Access

- **URL**: http://localhost:22300
- **Login**: admin@localhost / admin

## Usage

### Start Stack (Both)

```powershell
docker compose -f stack.yml up -d
```

### Start Individual Services

```powershell
# PostgreSQL only
docker compose -f postgres.yml up -d

# Joplin only
docker compose -f joplin.yml up -d
```

### Stop/Start

```powershell
docker compose -f stack.yml down
docker compose -f stack.yml up -d
```

### View Logs

```powershell
docker compose -f stack.yml logs -f
```

## Support

- **Website**: https://joplinapp.org
- **Documentation**: https://joplinapp.org/server/
- **GitHub**: https://github.com/laurent22/joplin
- **Forum**: https://discourse.joplinapp.org
- **Discord**: https://discord.gg/2xZvsQU