# 🔓 Free Fire MAX SSL Unpinned v2.115.1  

> A de-SSL-pinned build of **Free Fire MAX v2.115.1** for network analysis, modding, educational and research purposes **ONLY**.

---

## ⚠️ Disclaimer  
**This repository does NOT host any copyrighted game assets or code.**  
The APK provided in the [Releases][releases] section is **ONLY the re-signed, SSL-unpinned version** of the **official v2.115.1** build.  
Use at your own risk. **Do NOT use on your main account** – bans are possible.  
We are **not responsible** for any damages or ToS violations.

---

## 📦 Download  
| File | Size | SHA-256 |
|------|------|---------|
| [free-fire-max-2.115.1-ssl-unpinned.apk][releases] | ≈ 700 MB | Check release notes |

---

## 🛠️ What Was Changed  

| Step | Description |
|------|-------------|
| 1 | Pulled original `base.apk` from **v2.115.1** (ARM64) |
| 2 | Decompiled with **apktool** |
| 3 | Patched **OkHttp**, **Cronet** & **Unity lib** to disable cert-pinning |
| 4 | Re-built, **zip-aligned** and **re-signed** with a debug key |
| 5 | Tested on Android 12 & 13 (root + non-root) |

---

## 🚀 Quick Start  

1. **Uninstall** any existing Free Fire MAX.  
2. Install `free-fire-max-2.115.1-ssl-unpinned.apk`.  
3. Launch and **complete resource download**.  
4. Route traffic through **Burp / mitmproxy / Fiddler** (set proxy or use VPN mode).  
5. Import the proxy’s CA cert into **User store** (Android 7+) or **System store** (root).

---

## 🔍 Verifying  

```bash
# Check signature
apksigner verify --verbose free-fire-max-2.115.1-ssl-unpinned.apk

# Confirm zip-align & pinning removed
aapt dump badging free-fire-max-2.115.1-ssl-unpinned.apk | grep version
