Tools for flattening websites:
https://www.httrack.com/page/2/

Chrome for XP
https://www.mediafire.com/file/vrowb21urbwx4ah/GoogleChrome-v49.0.2623.112-full-offline-win-installer.zip
https://winclassic.net/thread/109/google-chrome-windows-xp-vista

In the CHrome shortcut add at the end of the target line, behind the "  --ignore-certificate-errors --disable-infobars



Here’s how to configure your Hyper-V test lab to simulate a simple, segmented network where:

* **`vapour` (Kali) and `ringworm` (XP)** live on `192.168.1.0/24`
* **`chagas` (XP)** lives on **`10.10.10.0/24`** and is behind a *mock firewall* but still has internet access

---

### ✅ Step-by-Step Plan to Configure Networking for `chagas`

#### **1. Create a New Virtual Switch in Hyper-V for the 10.10.10.0/24 Network**

1. Open **Hyper-V Manager**
2. Go to **Virtual Switch Manager**
3. Select **New virtual network switch**
4. Choose **Internal** (this will isolate the network but still allow host communication)
5. Name it something like `Internal10Net`
6. Click **Apply** and **OK**

---

#### **2. Assign the New Switch to `chagas`**

1. Open settings for the `chagas` VM
2. Go to **Network Adapter**
3. Change the **Virtual Switch** to `Internal10Net`
4. Apply settings and reboot `chagas`

---

#### **3. Set a Static IP for `chagas` on the 10.10.10.0/24 Network**

On the `chagas` Windows XP box:

* IP Address: `10.10.10.5`
* Subnet: `255.255.255.0`
* Gateway: `10.10.10.1` *(we’ll configure this next)*
* DNS: Google’s DNS (`8.8.8.8` or any)

---

#### **4. Add Internet Access to `chagas` via NAT on Host**

You’ll now route internet access to `chagas` through your **host machine** using **NAT**:

##### A. On your Windows host:

1. Open **PowerShell as Admin**

2. Find the name of your new internal switch:

   ```powershell
   Get-NetAdapter
   ```

   Note the name (e.g., `vEthernet (Internal10Net)`)

3. Set a static IP on that interface:

   ```powershell
   New-NetIPAddress -IPAddress 10.10.10.1 -PrefixLength 24 -InterfaceAlias "vEthernet (Internal10Net)"
   ```

4. Create a NAT object to allow routing:

   ```powershell
   New-NetNat -Name "Nat10Net" -InternalIPInterfaceAddressPrefix 10.10.10.0/24
   ```

Get-NetAdapter
New-NetIPAddress -IPAddress 10.10.10.1 -PrefixLength 24 -InterfaceAlias "vEthernet (Internal10Net)"
New-NetNat -Name "Nat10Net" -InternalIPInterfaceAddressPrefix 10.10.10.0/24
---

#### **5. Optional: Setup Simple Mock Firewall**

If you'd like to demonstrate "firewall bypass", you can:

* Use another lightweight Linux VM (like Alpine or Ubuntu Server)
* Install `iptables` and block all inbound traffic except HTTP (port 80)
* Place this VM between `vapour` and `chagas`, routing traffic through it *(advanced, but powerful)*

But for simplicity, you might just **role-play the "firewall"** as part of your scenario since `ringworm` already simulates public exposure.

---

### ✅ Final Topology Summary

| VM       | IP Address   | Network       | Role                 |
| -------- | ------------ | ------------- | -------------------- |
| vapour   | 192.168.1.10 | External      | Kali Threat Actor    |
| ringworm | 192.168.1.20 | External      | Public XP target     |
| chagas   | 10.10.10.5   | Internal10Net | "Internal" XP w/ Web |
| Host NIC | 10.10.10.1   | Internal10Net | NAT Gateway          |

Would you like help installing a web server on `chagas`, such as a vulnerable version of XAMPP?

Would you like a quick guide to pivoting from ringworm to chagas using Metasploit?


wget \
  --mirror \
  --convert-links \
  --adjust-extension \
  --page-requisites \
  --no-parent \
  --no-check-certificate \
  --user-agent="Mozilla/5.0 (Windows NT 5.1; rv:52.0) Gecko/20100101 Firefox/52.0" \
  https://wmmc.com


wget \
  --page-requisites \
  --convert-links \
  --adjust-extension \
  --no-parent \
  --no-check-certificate \
  --level=1 \
  --user-agent="Mozilla/5.0 (Windows NT 5.1; rv:52.0) Gecko/20100101 Firefox/52.0" \
  https://wmmc.com


