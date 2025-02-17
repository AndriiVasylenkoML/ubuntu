# Installing Touchégg on Ubuntu  

This guide will walk you through installing and setting up **Touchégg** on Ubuntu to enable multi-touch gestures for a better touchpad experience.  

---

## Step 1: Update and Upgrade Your System  

Before installing, update and upgrade your system:  

```sh
sudo apt update && sudo apt upgrade -y
```

---

## Step 2: Install GNOME Tweaks and Extensions  

If you are using the GNOME desktop environment, install the necessary tools to manage extensions:  

```sh
sudo apt install -y gnome-tweaks gnome-shell-extensions gnome-shell-extension-manager
```

These tools will help you customize and enhance your GNOME experience.  

---

## Step 3: Add the Touchégg Repository  

Add the official **Touchégg** PPA repository:  

```sh
sudo add-apt-repository ppa:touchegg/stable
```

Press **Enter** when prompted to confirm.  

---

## Step 4: Install Touchégg  

Once the repository is added, install **Touchégg**:  

```sh
sudo apt install -y touchegg
```

---

## Step 5: Verify That Touchégg Is Running  

Check the status of the **Touchégg** service:  

```sh
systemctl status touchegg
```

If it's running, you should see output indicating that the service is **active**.  

If Touchégg is not running, start it manually:  

```sh
systemctl start touchegg
```

To enable it at startup, use:  

```sh
systemctl enable touchegg
```

---

## Step 6: Restart Your System  

For all changes to take effect, restart your system:  

```sh
reboot
```
---
## Notes
* Caffeine
* Vitals
* GSConnect
* X11 Gestures