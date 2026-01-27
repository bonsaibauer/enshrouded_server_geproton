[![Repository](https://img.shields.io/badge/Repository-enshrouded__server__geproton-blue?style=flat&logo=github)](https://github.com/bonsaibauer/enshrouded_server_geproton)
![License](https://img.shields.io/badge/License-MIT-blue)
![Visitors](https://visitor-badge.laobi.icu/badge?page_id=bonsaibauer.enshrouded_server_geproton)

[![Report Problem](https://img.shields.io/badge/Report-new_Problem_or_Issue-critical?style=flat&logo=github)](https://github.com/bonsaibauer/enshrouded_server_geproton/issues/new)

![GitHub Stars](https://img.shields.io/github/stars/bonsaibauer/enshrouded_server_geproton?style=social)
![GitHub Forks](https://img.shields.io/github/forks/bonsaibauer/enshrouded_server_geproton?style=social)

# Enshrouded Dedicated Server (Docker + GE-Proton) — Road to Release 2026

> Code foundation: [mornedhels/enshrouded-server](https://github.com/mornedhels/enshrouded-server) — huge thanks. His repo is a feature-rich base; this repository [bonsaibauer/enshrouded_server_geproton](https://github.com/bonsaibauer/enshrouded_server_geproton) is a simplified, beginner-focused tutorial that narrows the scope to GE-Proton + supervisor so newcomers can get a performant server running fast.

> [!IMPORTANT]
> This setup uses GE-Proton and supervisord and is regarded in the community as the best, most resource-friendly configuration for Enshrouded servers on Linux. The game ships with no native Linux binary and previously ran only via Wine with noticeable performance loss. GE-Proton lets the Windows build run fast and stable.

Greetings, Flameborn!  
Grab a potion and read on: this is the most concise guide to spin up your own Enshrouded server in Docker — tuned for low resource usage, automatic updates, backups, and clean process control via Supervisor.

![Road to Release 2026](images/road_to_release_2026.png)

## Full Settings + Example Config

- All server/gameplay fields are documented in [`docs/enshrouded_server.md`](docs/enshrouded_server.md).
- A complete sample with every setting populated ships in [`ressources/enshrouded_server.json`](ressources/enshrouded_server.json).
- The repo Docker assets live in [`ressources/`](ressources); run builds via `docker compose -f ressources/docker-compose.yml up -d`.

---
# 1. Installing Docker (Ubuntu 24.04 and Other Linux Systems)

Docker allows you to run applications in isolated containers. It's ideal for deploying an Enshrouded dedicated server because it ensures consistency, portability, and easy management.

This guide will walk you through installing Docker on Ubuntu 24.04. These steps also work on most other Linux distributions with minor adjustments.

### Step 1: Update Your Package Index

Before installing anything, update your system to ensure all packages are current.

`Debian/Ubuntu`
```
sudo apt update && sudo apt upgrade -y
```
- `sudo apt update`: Refreshes the package index.
- `sudo apt upgrade -y`: Upgrades installed packages automatically.

> `Fedora`
> ```
> sudo dnf upgrade --refresh
> ```
> 
> `Arch Linux`
> ```
> sudo pacman -Syu
> ```

### Step 2: Install Required Dependencies

Docker relies on a few helper packages. Install them with:

```bash
sudo apt install apt-transport-https ca-certificates curl software-properties-common lsb-release gnupg -y
```

- `apt-transport-https`: Allows `apt` to use HTTPS.
- `ca-certificates`: Ensures your system trusts SSL certificates.
- `curl`: Command-line tool for downloading files.
- `software-properties-common`: Adds support for `add-apt-repository`.
- `lsb-release`: Provides OS version info.
- `gnupg`: Required for managing GPG keys.

### Step 3: Add Docker’s Official GPG Key

Docker signs its packages for security. Add their GPG key:

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

### Step 4: Add Docker’s APT Repository

Configure your system to use Docker’s stable software repository:

```bash
echo   "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg]   https://download.docker.com/linux/ubuntu   $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

### Step 5: Install Docker Engine

Update your package index again and install Docker:

```bash
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io -y
```

- `docker-ce`: Docker Community Edition
- `docker-ce-cli`: Docker command-line interface
- `containerd.io`: Container runtime used by Docker

Verify Docker is running:

```bash
sudo systemctl status docker
```

Press `q` to exit the status screen.