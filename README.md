# Jellyfin 🎥

Jellyfin is a powerful open-source media server that allows you to manage and stream your movies, music, and photos. This repository contains a Docker Compose configuration for deploying Jellyfin on Synology NAS.

---

## Overview 📝

This repository adapts the guides from [**Lixandru Marius Bogdan**](https://github.com/mariushosting) to provide a complete Docker Compose deployment for Jellyfin. It simplifies setup and management, enabling seamless streaming and media organization on Synology NAS.

### **Features:**

- 🎥 **Media Streaming** – Stream movies, TV shows, music, and photos.
- 🏠 **Self-hosted & Open Source** – Maintain full control over your media without relying on cloud services.
- ⚙️ **Customizable Configuration** – Use environment variables for easy setup.
- 🔒 **Secure Deployment** – Leverages host networking and user permissions for a secure configuration.

For setup instructions, visit:

- 📖 **[Jellyfin Setup Guide](https://jellyfin.org/docs/)**
- 📖 **[Portainer Guide](https://mariushosting.com/synology-install-jellyfin-with-portainer/)**

---

## Configuring IPAM and Network Firewall 🌍

This project uses **Docker IPAM (IP Address Management)** to manage container networking. To ensure smooth communication, you may need to configure your **firewall** to allow access based on the defined subnet.

### **IPAM Configuration**

You can configure the following settings in your [`.env`](example.env) file:

```bash
# Define the subnet range for the network
COMPOSE_NETWORK_SUBNET="${COMPOSE_NETWORK_SUBNET:-172.24.0.0/16}"

# Define the IP range for containers
COMPOSE_NETWORK_IP_RANGE="${COMPOSE_NETWORK_IP_RANGE:-172.24.5.0/24}"

# Define the network gateway
COMPOSE_NETWORK_GATEWAY="${COMPOSE_NETWORK_GATEWAY:-172.24.5.254}"
```

### **Updating Firewall Settings on Synology NAS** 🔥

To allow communication for this Docker network, update the **Synology Firewall** settings:

1. Open **Control Panel** → **Security** (under Connectivity).
2. Navigate to the **Firewall** tab → Click **Edit Rules**.
3. Click **Create** to add a new rule:
   - **Ports**: Select `All`
   - **Source IP**: Select `Specific IP`
   - Click `Select` → Choose `Subnet`
   - Enter `172.24.0.0` for **IP Address** and `255.255.0.0` for **Subnet mask/Prefix length**
   - **Action**: Select `Allow`
4. Click **OK** to apply the changes.

This ensures that containers using this Docker network can communicate without restrictions.

For more details, check the **[Docker Compose IPAM documentation](https://docs.docker.com/compose/compose-file/06-networks/#ipam)**.

---

## Deployment 🚀

This guide walks you through deploying Jellyfin using **DSM Container Manager** (recommended for Synology NAS). You can also use **Portainer** if you prefer a different UI.

### **1. Folders Are Pre-Created** 📂

No need to manually create folders—this project automatically sets them up in the `config` directory:

```console
config/
├── cache/
├── config/
├── logs/
```

### **2. Copy and Edit the Environment File** 📜

A sample [`example.env`](example.env) environment file is already included! Simply copy it and update the values as needed:

```sh
cp example.env .env
vim .env  # Edit with your settings
```

### **3. Deploy Using DSM Container Manager** 🏠

1. Open **DSM Container Manager**.
2. Navigate to **Projects** → Click **Create**.
3. Select **Import YAML** and browse to the `docker-compose.yml` file in the project root.
4. Click **Next** → Review settings → Click **Apply**.

### **4. Alternative Deployment with Portainer** 🖥️

If you prefer **Portainer**, follow these steps:

1. Go to **Stacks** in Portainer.
2. Click **Add Stack** → Name it `jellyfin`.
3. Browse to the `docker-compose.yml` file in the project root.
4. Click **Deploy the Stack**.

### **5. Access the Web Interfaces** 🌐

Once deployed, open your browser and access the service:

- **Jellyfin**: `https://jellyfin.yourname.synology.me`

Follow the instructions to complete your Jellyfin setup! 🏆

---

## Docker Compose Configuration 🐳

The full `docker-compose.yml` file is included in the **project root**. Check it out if you want to tweak or customize your deployment.

📄 **[View docker-compose.yml](./docker-compose.yml)**

---

## Troubleshooting 🛠️

- Verify container status:

  ```bash
  docker ps | grep ${JELLYFIN_CONTAINER_NAME}
  ```

- Check container logs for errors:

  ```bash
  docker logs ${JELLYFIN_CONTAINER_NAME}
  ```

- Confirm that the environment variables in your `.env` file are correctly set.
- Review your NAS firewall settings to ensure required traffic is allowed.

---

## Conclusion 🎉

You have successfully deployed Jellyfin using Docker Compose. Enjoy managing and streaming your media collection with ease.

Special thanks to Lixandru Marius Bogdan for the guides and inspiration behind this setup.
