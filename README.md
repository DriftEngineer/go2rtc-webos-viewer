# go2rtc webOS Viewer

A lightweight, native webOS application (`.ipk`) designed for LG OLED TVs (tested on LG C4) to stream and monitor RTSP/ONVIF security cameras via [go2rtc](https://github.com/AlexxIT/go2rtc) using a TV remote control.

---

## ✨ Features

- **In-App Configuration:** Interactive setup screen to enter your `go2rtc` server IP address directly on the TV using the remote control. Saves configuration automatically in `localStorage`.
- **Auto-Discovery:** Automatically fetches and lists all configured camera streams from the go2rtc API (`/api/streams`).
- **TV Remote Navigation (Spatial Navigation):** Fully controllable using standard D-Pad arrows (Up, Down, Left, Right) and OK/Enter.
- **Focus-Driven Lazy Loading (MSE):** Optimizes TV performance by loading a live **MSE (Media Source Extensions)** stream **only on the currently focused tile**. Inactive tiles display light JPEG snapshots, preventing memory and WebSocket exhaustion on webOS.
- **Fullscreen Mode with On-Screen Controls:** Expand any camera to full screen with **OK / Enter**. Includes an accessible on-screen return button compatible with Magic Remote and spatial navigation.
- **webOS Optimized:** Tailored for LG webOS Chromium limitations to ensure reliable playback without crashing.

---

## 📋 Requirements

- A running **go2rtc** instance with your cameras configured.
- Ensure your streams support or fallback properly to **MSE / FMP4** (which is standard for go2rtc's built-in web players).

---

## 🚀 Installation & Setup

### 1. Build the `.ipk` Package
Use the official webOS CLI (`webos-cli`) to package and install the application onto your LG TV in Developer Mode:

```bash
# Package the application
ares-package .

# Install onto your TV (replace with your target name/device)
ares-install com.domain.go2rtc-viewer_1.0.0_all.ipk
