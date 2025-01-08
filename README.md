# Media Service Compose

This repository contains a pre-configured `docker-compose.yml` file to set up a complete media management and streaming stack. It leverages popular tools like Prowlarr, Radarr, Sonarr, Transmission, and Jellyfin, all orchestrated via Docker Compose. This stack is designed to automate media downloads, organization, and streaming.

---

## Table of Contents
1. [Services](#services)
2. [Features](#features)
3. [Setup Instructions](#setup-instructions)
4. [Usage](#usage)
5. [Customizations](#customizations)
6. [Automation Workflow](#automation-workflow)

---

## Services

### 1. **Prowlarr**
   - **Description:** Indexer manager for Torrent and Usenet services.
   - **Port:** `9696`
   - **Purpose:** Centralized indexer management for Radarr and Sonarr.
   - **Health Check:** Monitors the `/ping` endpoint.

### 2. **Radarr**
   - **Description:** Movie download manager.
   - **Port:** `7878`
   - **Purpose:** Automates movie downloading, renaming, and organization.
   - **Health Check:** Monitors the `/ping` endpoint.

### 3. **Sonarr**
   - **Description:** TV series download manager.
   - **Port:** `8989`
   - **Purpose:** Automates TV series downloading, renaming, and organization.
   - **Health Check:** Monitors the `/ping` endpoint.

### 4. **Transmission**
   - **Description:** Torrent client.
   - **Port:** `9091`
   - **Purpose:** Manages torrent downloads for Radarr and Sonarr.
   - **Health Check:** Monitors the Transmission web interface.

### 5. **Jellyfin**
   - **Description:** Media server for streaming content.
   - **Port:** `8096`
   - **Purpose:** Provides a Netflix-like interface for streaming your media library.
   - **Health Check:** Monitors the root endpoint.

---

## Features

- **Automation:** Seamlessly integrates media downloaders and a media server for end-to-end automation.
- **Health Checks:** Ensures service uptime and reports issues.
- **Customizable:** Easily adaptable through environment variables and volume mappings.
- **Lightweight:** Optimized for local or server deployment.

---

## Setup Instructions

### Prerequisites
1. Docker and Docker Compose installed on your system.
2. Ensure that required ports (9696, 7878, 8989, 9091, 8096) are not in use.
3. Configure your environment variables:
   ```env
   SERVICE_FQDN_PROWLARR=<your-domain-or-ip>
   SERVICE_FQDN_RADARR=<your-domain-or-ip>
   SERVICE_FQDN_SONARR=<your-domain-or-ip>
   SERVICE_FQDN_TRANSMISSION=<your-domain-or-ip>
   SERVICE_FQDN_JELLYFIN=<your-domain-or-ip>
   TZ=Asia/Kolkata
   SERVICE_USER_ADMIN=admin
   SERVICE_PASSWORD_ADMIN=password
