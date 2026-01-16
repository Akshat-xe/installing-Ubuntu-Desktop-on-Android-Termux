<img src="https://i.pinimg.com/736x/9e/7b/3c/9e7b3cf486c236909de7e1140dddac24.jpg" width="100%" alt="Dark Aura Header" />


# 🔯 Phase 1: Download the Essentials
Before we start, you need the engine (Termux) and the screen (VNC Viewer).

## 1. Download Termux (The Terminal)
Use the lattest version for better stability:

👉 [Download Termux (GitHub v0.118.3)](https://github.com/termux/termux-app/releases/tag/v0.118.3)

Download the `.apk` file (usually `termux-app_v0.118.3+github-debug_universal.apk`).

## 2. Download VNC Viewer (The Screen)
Since to run Ubuntu Graphically, we need a standard viewer.

👉 [Download RealVNC Viewer (Play Store)](https://play.google.com/store/apps/details?id=com.realvnc.viewer.android)

Or search "RealVNC" in your app store.

---

# 🔯 Phase 2: The Installation (The Magic Command)
This command will download Ubuntu 22.04 and the XFCE Desktop environment automatically.

1. Open Termux.
2. Copy this entire block.
3. Paste it into Termux and hit Enter.

```bash
termux-setup-storage
gpkg update -y && pkg install wget curl proot tar -y
wget https://raw.githubusercontent.com/AndronixApp/AndronixOrigin/master/Installer/Ubuntu22/ubuntu22-xfce.sh -O ubuntu-install.sh
chmod +x ubuntu-install.sh
./ubuntu-install.sh
```
4. Important:
   - Click **Allow** on the storage popup.
   - The installation will download about 1.5GB of data. Do not close Termux until it finishes.
   - If it asks you to select a region/timezone during install, type the number for your region (e.g., 2 for America, 6 for Asia) and hit Enter.

---

# 🚀 Phase 3: How to Launch Ubuntu
Once the text stops scrolling and you get your control back, you are ready.

## Mode A: The Terminal Mode (Command Line Only)
Use this if you just want to run Python scripts, compile code, or use Git.
- **To Start:** Type `./start-ubuntu22.sh`
- **To Exit:** Type `exit`

# Mode B: The Desktop Mode (Graphical Interface)

**If you want the full graphical desktop.**

## 1. Start the VNC Server
Inside Termux (after launching Ubuntu with `./start-ubuntu22.sh`), type:

```bash
vncserver-start
```
*It will ask you to set a password the first time. Type something simple like `123456` and select "n" for view-only.*

## 2. Note the Address
The terminal will tell you the address. It is usually:
- **Display:** :1
- **Port:** 5901

## 3. Connect
Open the RealVNC Viewer app.
- Click the + button to add a new connection.
- **Address:** localhost:5901
- **Name:** Ubuntu
- Click **Connect**.
- Enter the password you just set.

## To Stop the Desktop
When you are done, go back to Termux and type:
```bash
vncserver-stop
```

---
> ⚠️ **CRITICAL CAUTION: READ OR YOU WILL BREAK IT**
> Running Ubuntu on a phone is different from a PC. Follow these rules to keep it running forever.
>
> ## ❌ NEVER DO THIS:
> - Never use `snap install [app]`
> 	*Why? Snap requires "systemd" (background services), which Android does not allow. Using Snap will fail.*
> - Never use `systemctl start [service]`
> 	*Why? Same reason. If you need to run a database (like MySQL), launch it directly using its command, not systemctl.*
>
> ## ✅ ALWAYS DO THIS:
> - To Install Apps: Use `apt`.
> 	Example: `apt install git` or `apt install firefox`
> - To Update: It is generally safer to run `apt update` and `apt upgrade` here than in Kali, but always watch the screen for errors.
>
> Follow this guide, and you will have a full Ubuntu Desktop in your pocket!
