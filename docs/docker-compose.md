# Docker Compose Environment Quick Reference

These variables can be placed under `services.enshrouded.environment` in your `docker-compose.yml`.

| Variable | Default / Example | What it controls |
|----------|-------------------|------------------|
| `SERVER_NAME` | `Enshrouded Server` | Display name in the server browser |
| `SERVER_SLOT_COUNT` | `16` | Max concurrent players (1–16) |
| `SERVER_QUERYPORT` | `15637` | Steam query/gameplay UDP port |
| `SERVER_IP` | `0.0.0.0` | Bind address inside the container |
| `SERVER_SAVE_DIR` | `./savegame` | Savegame folder (relative or absolute) |
| `SERVER_LOG_DIR` | `./logs` | Log folder (relative or absolute) |
| `SERVER_VOICE_CHAT_MODE` | `Proximity` | Voice scope (`Proximity` \| `Global`) |
| `SERVER_ENABLE_VOICE_CHAT` | `true` | Toggle voice chat (`true`/`false`) |
| `SERVER_ENABLE_TEXT_CHAT` | `true` | Toggle text chat (`true`/`false`) |
| `PUID` / `PGID` | `4711` / `4711` | UID/GID for file permissions on the mounted volume |
| `UPDATE_CRON` | `*/30 * * * *` | Schedule update checks (cron syntax) |
| `UPDATE_CHECK_PLAYERS` | `true` | Skip updates when players are online |
| `BACKUP_CRON` | `*/30 * * * *` | Backup frequency (zip latest save). Keep ≥10 minutes |
| `BACKUP_DIR` | `./backups` | Backup target folder |
| `BACKUP_MAX_COUNT` | `7` | Retention (0 = keep all) |
| `RESTART_CRON` | `0 3 * * *` | Scheduled restarts (set empty to disable) |
| `RESTART_CHECK_PLAYERS` | `true` | Skip restart if players are online |
| `GAME_BRANCH` | `public` | Steam branch to use |
| `STEAMCMD_ARGS` | `validate` | Extra SteamCMD arguments |
| `log_level` | `50` | Supervisor/syslog verbosity (lower = more verbose) |

> Password-based access is deprecated upstream; use server roles instead.
