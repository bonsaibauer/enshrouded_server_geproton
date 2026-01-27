# Enshrouded Dedicated Server (Docker + GE-Proton) — Road to Release 2026

> Code foundation: [mornedhels/enshrouded-server](https://github.com/mornedhels/enshrouded-server) — huge thanks. His repo is a feature-rich base; this repository [bonsaibauer/enshrouded_server_geproton](https://github.com/bonsaibauer/enshrouded_server_geproton) is a simplified, beginner-focused tutorial that narrows the scope to GE-Proton + supervisor so newcomers can get a performant server running fast.

> [!IMPORTANT]
> This setup uses GE-Proton and supervisord and is regarded in the community as the best, most resource-friendly configuration for Enshrouded servers on Linux. The game ships with no native Linux binary and previously ran only via Wine with noticeable performance loss. GE-Proton lets the Windows build run fast and stable.

Greetings, Flameborn!  
Grab a potion and read on: this is the most concise guide to spin up your own Enshrouded server in Docker — tuned for low resource usage, automatic updates, backups, and clean process control via Supervisor.

## Why GE-Proton + Supervisor?
- No native Linux binary; Wine caused CPU/I/O bottlenecks.  
- GE-Proton delivers clear performance gains even on modest hardware.  
- Supervisor keeps game, updater, and backups in separate managed processes and allows targeted restarts.  
- Widely called the “best setup” for production servers in the community.

![Road to Release 2026](images/road_to_release_2026.png)
