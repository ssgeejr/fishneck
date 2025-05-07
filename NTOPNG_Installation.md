

## 🛠️ Step 1: Update Your System

First, open a terminal in Kali and run:

```bash
sudo apt update && sudo apt upgrade -y
```

This ensures your system is up to date.

---

## 📦 Step 2: Install ntopng

Install `ntopng` directly from the Kali repository:

```bash
sudo apt install ntopng -y
```

> 🔍 This installs `ntopng`, required dependencies, and `redis`, which ntopng uses to store temporary data.

---

## ⚙️ Step 3: Configure ntopng (Basic Setup)

Edit the ntopng config file to define what interface to monitor and set basic settings.

```bash
sudo nano /etc/ntopng/ntopng.conf
```

Use these basic example settings:

```
-i=1
-w=3000
```

**Explanation:**

* `-i=1` means monitor interface `eth0` or `enp0s3` (usually interface 1, but double-check with `ip a`)
* `-w=3000` means the web interface will run on port 3000

To find your network interface name, use:

```bash
ip a
```

Replace `-i=1` with your actual interface, like `-i=enp0s3` if needed.

---

## 🚀 Step 4: Start ntopng Service

```bash
sudo systemctl start ntopng
```

Enable it to start at boot:

```bash
sudo systemctl enable ntopng
```

Check that it’s running:

```bash
sudo systemctl status ntopng
```

---

## 🌐 Step 5: Access the ntopng Web Interface

Open a browser and go to:

```
http://localhost:3000
```

Or from another machine on the network:

```
http://<Kali_IP>:3000
```

Log in with:

* **Username:** `admin`
* **Password:** `admin`

You’ll be asked to **change the password** on first login.

---

## 📊 Step 6: Explore the Dashboard

Once logged in, you’ll see:

* **Traffic Overview**
* **Top Talkers**
* **Protocol Usage**
* **Live Hosts**
* **Alerts (if threats or anomalies are detected)**

Click around to view:

* Real-time bandwidth
* Devices on the network
* Who is talking to whom
* What protocols are in use (HTTP, DNS, SSH, etc.)

---

## 🧠 Optional: Save Traffic History

By default, ntopng stores limited data. If you want **persistent storage**, configure Redis or enable disk logging.

Let me know if you'd like to do that next or export reports.

---

## ✅ Summary

| Step | Action                             |
| ---- | ---------------------------------- |
| 1    | Update Kali Linux                  |
| 2    | Install `ntopng`                   |
| 3    | Configure network interface & port |
| 4    | Start the ntopng service           |
| 5    | Access the web interface           |
| 6    | Explore network data in real time  |

---

Would you like help configuring alerts, using NetFlow, or integrating with Zeek or Suricata next?
