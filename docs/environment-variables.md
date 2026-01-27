# Environment Variables Quick Reference

Use these as `environment` entries in `docker-compose.yml` (e.g., under `services.enshrouded.environment`) or pass them to `docker run -e KEY=VALUE`.

---

## Environment Variables

| Setting | Description | Example / Default Value | Options / Notes |
|---------|-------------|-------------------------|-----------------|
| **SERVER_NAME** | Display name in the server browser | Enshrouded Server | Any string |
| **SERVER_SLOT_COUNT** | Max concurrent players | 16 | 1–16 |
| **SERVER_QUERYPORT** | Steam query/gameplay UDP port | 15637 | Integer |
| **SERVER_IP** | Bind address inside the container | 0.0.0.0 | IP |
| **SERVER_SAVE_DIR** | Savegame folder | ./savegame | Relative or absolute path |
| **SERVER_LOG_DIR** | Log folder | ./logs | Relative or absolute path |
| **SERVER_VOICE_CHAT_MODE** | Voice scope | Global | Proximity / Global |
| **SERVER_ENABLE_VOICE_CHAT** | Toggle voice chat | true | true / false |
| **SERVER_ENABLE_TEXT_CHAT** | Toggle text chat | true | true / false |
| **PUID** / **PGID** | UID/GID for mounted volume | 4711 / 4711 | Integers |
| **UPDATE_CRON** | Schedule update checks | 0 * * * * | Cron syntax |
| **UPDATE_CHECK_PLAYERS** | Skip updates if players online | true | true / false |
| **BACKUP_CRON** | Backup frequency (zips latest save) | 0 0 * * * | Cron syntax |
| **BACKUP_DIR** | Backup target folder | ./backups | Relative or absolute path |
| **BACKUP_MAX_COUNT** | Retention (0 = keep all) | 14 | Count of archives |
| **RESTART_CRON** | Scheduled restarts (empty to disable) | 0 3 * * * | Cron syntax |
| **RESTART_CHECK_PLAYERS** | Skip restart if players online | true | true / false |
| **GAME_BRANCH** | Steam branch to use | public | Steam branch name |
| **STEAMCMD_ARGS** | Extra SteamCMD arguments | validate | Any args |
| **log_level** | Supervisor/syslog verbosity | 50 | Lower = more verbose |

---

## Recommended Schedule (matching defaults)

| Task | Cron | Notes |
|------|------|-------|
| Update check | 0 * * * * | Hourly; skipped when `UPDATE_CHECK_PLAYERS=true` and players are online |
| Backup | 0 0 * * * | Daily archive of the latest save; keep last 14 via `BACKUP_MAX_COUNT` |
| Restart | 0 3 * * * | Daily restart at 03:00; skipped when `RESTART_CHECK_PLAYERS=true` and players are online |

> Password-based access is deprecated upstream; use server roles instead.
