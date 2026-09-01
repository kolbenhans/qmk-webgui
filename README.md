# Per-Key Colors WebGUI

A lightweight **WebHID interface for QMK's `key_colors` module**, allowing per-key and per-layer RGB colors to be configured directly from a web browser.

## Screenshots

<p align="center">
  <img width="500" height="365" alt="grafik" src="https://github.com/user-attachments/assets/bbb76253-cf4d-4f17-ad7f-bda5129314bf" />
</p>

<p align="center">
  <img width="500" height="456" alt="grafik" src="https://github.com/user-attachments/assets/032f2242-15cb-4abb-a771-9208131676a7" />
</p>

No installation, build system, or additional software is required.

The WebGUI is currently used by:

* [SofleRGB](https://github.com/kolbenhans/SofleRGB)
* [ymdk-id75v3rp-RGB](https://github.com/kolbenhans/ymdk-id75v3rp-RGB)

Both projects use the [`key_colors`](https://github.com/kolbenhans/qmk-modules) QMK module.

---

## Features

* 🎨 **Per-key RGB colors**
* 🗂️ **Per-layer color configuration**
* 💡 **Brightness control**
* ✨ **Blink effects**
* 🔌 **Direct keyboard communication via WebHID**
* 🌐 **Runs entirely in the browser**
* 📦 **No build step**
* 🧩 **No external dependencies**

Configuration is written directly to the keyboard through the QMK HID interface.

---

## Browser Support

The WebGUI uses the **WebHID API**.

Currently supported browsers include:

* **Google Chrome**
* **Microsoft Edge**
* **Opera**

**Firefox and Safari do not currently support WebHID.**

For the most reliable experience, use a current Chromium-based browser.

---

## Run Locally

There is no build process and no dependency installation required.

Clone the repository:

```bash
git clone https://github.com/kolbenhans/qmk-webgui.git
cd qmk-webgui
```

Start a simple local HTTP server:

```bash
python3 -m http.server 8420
```

Then open:

```text
http://127.0.0.1:8420/index.html
```

Python's built-in `http.server` is sufficient — nothing else needs to be installed.

> `localhost` is considered a secure context by browsers, so HTTPS is not required for local use.

---

## Usage

1. Connect a compatible QMK keyboard via USB.
2. Open the WebGUI in a supported browser.
3. Allow the browser to access the keyboard when prompted.
4. Select the desired layer.
5. Configure the colors and RGB settings.
6. Write the configuration to the keyboard.

The keyboard must run firmware containing the [`key_colors`](https://github.com/kolbenhans/qmk-modules) QMK module.

The WebGUI itself does not contain any keyboard-specific firmware code; it communicates with the module through QMK's HID interface.

---

## How It Works

```text
┌──────────────────────┐
│      Web Browser     │
│                      │
│     Per-Key RGB      │
│       WebGUI         │
└──────────┬───────────┘
           │
           │ WebHID
           ▼
┌──────────────────────┐
│      QMK Firmware    │
│                      │
│     key_colors       │
│       module         │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│      RGB Matrix      │
│                      │
│   Per-Key / Layer    │
│       Colors         │
└──────────────────────┘
```

The browser communicates directly with the keyboard using WebHID. No intermediate application or server is required.

The local HTTP server is only needed to serve the static page in a browser-compatible context.

---

## Related Projects

### QMK Module

The firmware-side implementation is provided by:

[**kolbenhans/qmk-modules**](https://github.com/kolbenhans/qmk-modules)

### SofleRGB

Custom Vial-QMK firmware for the Sofle RGB with per-key RGB configuration:

[**kolbenhans/SofleRGB**](https://github.com/kolbenhans/SofleRGB)

### ID75v3RP RGB

Custom Vial-QMK firmware for the Idobao × YMDK ID75v3RP:

[**kolbenhans/ymdk-id75v3rp-RGB**](https://github.com/kolbenhans/ymdk-id75v3rp-RGB)

---

## Project Structure

```text
qmk-webgui/
├── vendor/
├── index.html
└── README.md
```

The application is intentionally kept as a small static web application.

---

## License

See [`LICENSE`](LICENSE) for license information.
