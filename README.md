# 🦀 Jellyfin: The High Seas of Streaming! 🎥

Ahoy, media mariners! 💀 Welcome to **Jellyfin**, your open-source media **galleon** sailing the vast ocean of entertainment! 🌊 This repo helps you deploy **Jellyfin on your Synology NAS** using **Docker Compose**—so grab your spyglass and let's chart a course to **ad-free, subscription-free** streaming! 🌌

---

## 📄 The Captain's Log

This repo be inspired by the legendary [**Lixandru Marius Bogdan**](https://github.com/mariushosting) and fine-tuned for **Synology NAS buccaneers** who want to command their media **without corporate sea monsters** meddlin' in their affairs.

### **Features Fit for a Sea Dog:**

- 🎥 **Deep-Sea Streaming** – Plunder movies, TV shows, music, and photos from your very own **media reef**.
- 🏰 **Self-Hosted & Free** – No subscriptions, no scallywags **stealin' your data**!
- ⚙️ **Easy as Hoisting a Sail** – Just tweak `.env` settings and you're set to sail!
- 🔒 **Treasure Locked & Secure** – Your **private media trove** stays safe **aboard your NAS**.

📖 **[Jellyfin Ship's Manual](https://jellyfin.org/docs/)** | 📖 **[Synology Setup Scroll](https://mariushosting.com/synology-install-jellyfin-with-portainer/)**

---

## 🌊 Navigating the Waters: Network & Firewall Setup

Jellyfin needs smooth sailing to stream like a dream. This setup uses **Docker IPAM (IP Address Management)** to keep yer ship steady. Adjust yer **firewall settings** or risk getting lost in the briny deep! 🏳️

### **IPAM Configuration**

Set yer **network subnet, IP range, and gateway** in yer `.env` file:

```bash
COMPOSE_NETWORK_SUBNET="${COMPOSE_NETWORK_SUBNET:-172.24.0.0/16}"
COMPOSE_NETWORK_IP_RANGE="${COMPOSE_NETWORK_IP_RANGE:-172.24.5.0/24}"
COMPOSE_NETWORK_GATEWAY="${COMPOSE_NETWORK_GATEWAY:-172.24.5.254}"
```

### **Batton Down the Firewall!** 🔥

1. Open **Control Panel** → **Security** → **Firewall**.
2. Click **Edit Rules** → **Create New Rule**.
3. **Ports**: Select `All`
4. **Source IP**: Choose `Specific IP`, then enter:
   - **IP Address:** `172.24.0.0`
   - **Subnet mask:** `255.255.0.0`
5. **Action**: Select `Allow`, then **Apply**.

Your media vessel shall now **sail unimpeded** through the digital seas! 🌍

---

## 🚀 Hoist the Colors! Deploying Jellyfin

Follow these steps to launch yer **floating fortress of entertainment** in minutes.

### **1. Yer Storage Holds Are Ready!** 📚

Yer **config directory** is set up **automagically**! Just mount yer media and set sail:

```console
config/
├── cache/
├── config/
├── logs/
```

### **2. Copy & Edit Yer `.env` File** 📝

Rename the example file and **customize it to match yer ship's specs**:

```sh
cp example.env .env
vim .env  # Adjust as needed, ye salty dog!
```

### **3. Deploy with DSM Container Manager** 🏠

1. Open **DSM Container Manager**.
2. Navigate to **Projects** → Click **Create**.
3. Choose **Import YAML** and select yer `docker-compose.yml`.
4. Click **Next** → Review settings → Click **Apply**.

### **4. Or Use Portainer If Ye Prefer!** 🖥️

1. Open **Portainer** → Go to **Stacks**.
2. Click **Add Stack** → Name it `jellyfin`.
3. Upload yer `docker-compose.yml`.
4. Click **Deploy the Stack**.

### **5. Ready the Cannons! Access Yer Media** 🌐

Point yer browser at:

- **Jellyfin Dashboard:** `https://jellyfin.yourname.synology.me`

Finish the setup wizard, add yer media, and set sail for an **ocean of entertainment**! 📺

---

## 🦠 Exploring the Docker Compose Setup

The full **`docker-compose.yml`** file is here **should ye need to tinker with yer ship's hull**.

📑 **[View docker-compose.yml](./docker-compose.yml)**

---

## 🤿 Troubleshooting: Avoiding the Kraken's Grasp

- Check if yer **Jellyfish be afloat**:

  ```bash
  docker ps | grep ${JELLYFIN_CONTAINER_NAME}
  ```

- Inspect the **captain's logs** for any beasties:

  ```bash
  docker logs ${JELLYFIN_CONTAINER_NAME}
  ```

- Verify yer **.env** settings—one wrong number and ye could be **sailing in circles**!
- Ensure **NAS firewall rules** are letting yer ship through the fog.

---

## 🎉 That's a Wrap, Ye Old Sea Dog

Congratulations, ye've deployed **Jellyfin, the finest media vessel on the high seas!** Enjoy yer private treasure **without ads, fees, or landlubber nonsense**!

A mighty thanks to [Lixandru Marius Bogdan](https://github.com/mariushosting) for the inspiration!

🎬 Happy sailing, matey! 🌌
