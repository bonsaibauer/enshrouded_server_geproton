# Enshrouded Dedicated Server (Docker + GE-Proton) — Road to Release 2026

> Code foundation: [mornedhels/enshrouded-server](https://github.com/mornedhels/enshrouded-server) — huge thanks. His repo is a feature-rich base; this one is a simplified, beginner-focused tutorial that narrows the scope to GE-Proton + supervisor so newcomers can get a performant server running fast.

> [!IMPORTANT]
> This setup uses GE-Proton and supervisord and is regarded in the community as the best, most resource-friendly configuration for Enshrouded servers on Linux. The game ships with no native Linux binary and previously ran only via Wine with noticeable performance loss. GE-Proton lets the Windows build run fast and stable.

Greetings, Flameborn!  
Grab a potion and read on: this is the most concise guide to spin up your own Enshrouded server in Docker — tuned for low resource usage, automatic updates, backups, and clean process control via Supervisor.

![Road to Release 2026](images/road_to_release_2026.png)

## Why GE-Proton + Supervisor?
- No native Linux binary; Wine caused CPU/I/O bottlenecks.  
- GE-Proton delivers clear performance gains even on modest hardware.  
- Supervisor keeps game, updater, and backups in separate managed processes and allows targeted restarts.  
- Widely called the “best setup” for production servers in the community.

## Blog: Road to Release
**Enshrouded is two years old!** Time flies — we were nervous before hitting the release button, then the player wave hit and the rest is history. To celebrate, new Twitch Drops arrive tomorrow morning. Prefer in-game? Find them via the Huntress. All of it lands tomorrow afternoon after Patch 13.
**We reached 5M players!** That’s roughly the population of greater Frankfurt, where Keen Games is from. Every single one of you made this happen. Special shout-out to Fall Damage Georg for 27,000 fatal falls.
**Road to Release**  
Enshrouded launches this Autumn (2026). We’re not naming a specific date until everything is locked. Focus: stick the 1.0 landing. Until then, we’ll paint the picture with the picture above. Want direct commentary from Creative Director Antony? Watch the video where Community Lead CoolUsernameBro and Antony walk through the announcements.

Thanks for two years in Embervale — and for joining us on the road to 1.0!
