# Media Service Compose

<div align="left"><sub>// Self-Hosted Media Management & Streaming Stack for Coolify</sub></div>

<br>

This repository provides Docker Compose setup that automates the deployment of a complete media management and streaming stack for coolify. The stack includes popular services like **Radarr**, **Sonarr**, **Transmission**, **Prowlarr**, and **Jellyfin**—all orchestrated in a seamless manner to offer you a hassle-free solution for media automation for self hosted solution.

<div align="center">
  <a href="#services-overview"><kbd> <br> Services Overview <br> </kbd></a>&ensp;&ensp;
  <a href="#key-features"><kbd> <br> Key Features <br> </kbd></a>&ensp;&ensp;
  <a href="#quick-start-guide"><kbd> <br> Quick Start Guide <br> </kbd></a>&ensp;&ensp;
  <a href="#automation-workflow"><kbd> <br> Automation Workflow <br> </kbd></a>&ensp;&ensp;
  <a href="#customization-configuration"><kbd> <br> Customization & Configuration <br> </kbd></a>&ensp;&ensp;
  <a href="#troubleshooting"><kbd> <br> Troubleshooting <br> </kbd></a>&ensp;&ensp;
  <a href="#contributing"><kbd> <br> Contributing <br> </kbd></a>&ensp;&ensp;
  <a href="#license"><kbd> <br> License <br> </kbd></a>&ensp;&ensp;
</div>

---

#### _<div align="left"><sub>// Services Overview</sub></div>_

Here are the core services included in this stack:

### 1. **Prowlarr**
   - **Description:** Indexer manager for Torrent and Usenet services.
   - **Port:** `9696`
   - **Purpose:** Serves as a centralized indexer manager for Radarr and Sonarr, streamlining the media search process.
   - **Health Check:** Monitors the `/ping` endpoint.

### 2. **Radarr**
   - **Description:** Movie download manager.
   - **Port:** `7878`
   - **Purpose:** Automates movie downloading, renaming, and organizing through torrents.
   - **Health Check:** Monitors the `/ping` endpoint.

### 3. **Sonarr**
   - **Description:** TV series download manager.
   - **Port:** `8989`
   - **Purpose:** Automates TV series downloading, renaming, and organizing through torrents.
   - **Health Check:** Monitors the `/ping` endpoint.

### 4. **Transmission**
   - **Description:** Torrent client.
   - **Port:** `9091`
   - **Purpose:** Manages torrent downloads for Radarr and Sonarr with ease.
   - **Health Check:** Monitors the Transmission web interface for operational health.

### 5. **Jellyfin**
   - **Description:** Media server for streaming.
   - **Port:** `8096`
   - **Purpose:** Provides a Netflix-like experience for streaming your downloaded movies and TV shows.
   - **Health Check:** Monitors the root endpoint.

---

#### _<div align="left"><sub>// Key Features</sub></div>_

- **Complete Automation:** Integrates all services to automate your media download and organization process.
- **Self-Hosting:** Full control of your media stack on your local server or VPS.
- **Health Checks:** Ensures that all services are up and running with automated health monitoring.
- **Modular & Scalable:** Easily configurable with environment variables and volume mappings for your use case.
- **Lightweight:** Optimized for minimal resource usage and fast deployment.

---

#### _<div align="left"><sub>// Quick Start Guide</sub></div>_

##### Prerequisites
1. Install **Docker** and **Docker Compose** on your machine.
2. Ensure that required ports (9696, 7878, 8989, 9091, 8096) are open and available.
3. Create a `.env` file in the root of the repository with the following variables:

```env
SERVICE_FQDN_PROWLARR=<your-domain-or-ip>
SERVICE_FQDN_RADARR=<your-domain-or-ip>
SERVICE_FQDN_SONARR=<your-domain-or-ip>
SERVICE_FQDN_TRANSMISSION=<your-domain-or-ip>
SERVICE_FQDN_JELLYFIN=<your-domain-or-ip>
TZ=Asia/Kolkata
SERVICE_USER_ADMIN=admin
SERVICE_PASSWORD_ADMIN=password
