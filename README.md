<hr />

<p align="center">
  <em>🪼 Drop a ⭐️ in the reef if this Jellyfin made your media swim smoother!</em>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Reef%20Ready-Docker-blue?logo=docker" alt="Reef Ready" />
  <img src="https://img.shields.io/badge/Currents%20Encrypted-WireGuard%20%7C%20PIA-green?logo=protonvpn" alt="Currents Encrypted" />
  <img src="https://img.shields.io/github/license/scottgigawatt/jellyfin?label=Open%20Waters%20License&color=blue" alt="Open Waters License" />
  <img src="https://img.shields.io/github/last-commit/scottgigawatt/jellyfin?label=Last%20Splash&logo=git" alt="Last Splash" />
  <img src="https://img.shields.io/github/repo-size/scottgigawatt/jellyfin?label=Coral%20Cache" alt="Coral Cache" />
  <img src="https://img.shields.io/badge/Sea--Tested-Synology%20%7C%20macOS-blue" alt="Sea-Tested" />
  <img src="https://img.shields.io/badge/Current%20Supply-Flowing-orange" alt="Current Supply" />
</p>

<hr />

# Jellyfin 🪼🎥

Welcome to Jellyfin—a deep dive into running your own private streaming sanctuary on Synology NAS or any Docker-ready harbor! Think of it as your underwater media lab for organizing and enjoying your... perfectly legitimate media collection. 🌊

## Overview 📋

> 🪼 **Because sometimes you need your "personal backups" ready for binge-watching.**

This project sets up Jellyfin using Docker Compose, perfect for hosting your personal sea of movies, TV shows, and more. Whether you're cataloging classics or totally legal copies of cinema, this setup lets you swim laps around the paid streaming sharks.

Take a deeper dive into the Docker Compose configuration by checking out the files in this repository:

- 📄 [View docker-compose.yml](./docker-compose.yml)

Special thanks to [Lixandru Marius Bogdan](https://github.com/mariushosting) 🧭🐟 for charting the early currents and guide this Jellyfin reef to life.

## What's in the Tank? 🛠️

Here's your crew of trusty sea creatures—ready to keep your Jellyfin reef alive and thriving:

| Tool                | Description                                                   | More Info                                           |
|---------------------|---------------------------------------------------------------|-----------------------------------------------------|
| **Jellyfin** 🪼     | The pearl of your media reef. Your media, your rules.          | [Official Site](https://jellyfin.org/)              |

> [!TIP]
> 🪼 This project deploys Jellyfin as a standalone jellyfish gliding through your media reef.
>
> Want to build a full undersea kingdom or explore more... intimate depths? Just glance below for companion voyages. 👇🌊

<p align="center">
  <a href="https://github.com/scottgigawatt/plundarr">
    <img src="https://img.shields.io/badge/🦜%20Plundarr%20-%20Media%20Automation%20Tools%20☠️🏴‍☠️-7e3f98?style=for-the-badge&labelColor=4b286d" alt="Plundarr" />
  </a>
  <a href="https://github.com/scottgigawatt/boudoirr">
    <img src="https://img.shields.io/badge/🔥%20Boudoirr%20-%20Private%20Pleasures%20Stack%20🖤🥀-ff69b4?style=for-the-badge&labelColor=880e4f" alt="Boudoirr" />
  </a>
</p>

## Setting Sail 🚀

### 🛠️ Cloning the Project

Pull the project down to your device like a swift current:

```sh
git clone https://github.com/scottgigawatt/jellyfin.git /volume1/docker/jellyfin
```

> [!NOTE]
> 🌎 Adjust the target folder depending on your ocean floor—Synology 🖥️, macOS 🍎, Linux 🐧—whatever floats your boat 🚤.

### 🐟 Setting Environment Variables

Every underwater lab needs the right pressure settings. Copy the example `.env` file and tweak it to fit your sea conditions:

- 📄 [View example.env](example.env)

```sh
cp example.env .env

# Edit as needed
vim .env
```

> [!TIP]
> Want to override environment variables on the fly like a speedy marlin? Splash them into the command line:
>
> ```bash
> JELLYFIN_TAG="latest" docker-compose up -d
> ```

### 📚 Essential Pre-Dive Checklist

> [!IMPORTANT]
> 🪼 _Before diving deep, make sure your gear is set…_

Read the [Docker Project Setup](./SETUP.md) guide. It covers all the crucial setup steps like networking currents, fine-tuning Synology-specific settings, firewall tweaks, and deploying with DSM Container Manager.

Highlighted swim lanes:

- 🌐🔧 [Configuring Docker Networking](./SETUP.md#configuring-docker-networking-)
- 🖥️⚙️ [Synology Configuration](./SETUP.md#synology-configuration-)
  - 🔥🛡️ [Updating Firewall Settings](./SETUP.md#updating-firewall-settings-)
  - 📦🚀 [Deploying With Container Manager](./SETUP.md#deploying-with-container-manager-)

Skipping this could leave you tangled in a kelp forest—don't risk it.

## Where This Swims 🐬

This Jellyfin setup has been fully tested on Synology DS1522+ and DS916+ running DSM 7.2. But this setup isn't just for Synology! It should float just fine on macOS, Linux, or any other system that runs Docker.

If you have gills (or Docker Compose), you can swim with us.

## Open Waters License 🌊

Licensed under the Apache 2 License—open waters, open code. 📄

---

```
            _.-=-._
         o~`  '  > `.
         `.  ,       :          Jellyfin Reef 🪼🌊
          `"-.__/    `.    ~ Drift deeper into your media ocean ~
                `--.___~
      ~~~ ~~~~   ~~~~~ ~~~ ~~~~~ ~~~~ ~~~ ~~~ ~~~~ ~~~
     ~ ~  ~~~ ~~~~  ~~~~ ~~~ ~~~  ~~~~ ~~~ ~~~ ~~~~ ~
```

Contributions, pull requests, and bubble-blowing contests welcome. Happy streaming and may your ocean of media always stay crystal clear! 🪼📺
