# Per-Key Colors WebGUI

Static WebHID page for [kolbenhans/qmk-modules](https://github.com/kolbenhans/qmk-modules)'
`key_colors` module — per-key/per-layer RGB from the browser, no install.
Chrome/Edge/Opera only (WebHID, no Firefox/Safari).

<img width="500" height="365" alt="grafik" src="https://github.com/user-attachments/assets/bbb76253-cf4d-4f17-ad7f-bda5129314bf" />

<img width="500" height="456" alt="grafik" src="https://github.com/user-attachments/assets/032f2242-15cb-4abb-a771-9208131676a7" />

## Run locally

No build step, no dependencies — just a static file served over HTTP.

```sh
git clone https://github.com/kolbenhans/qmk-webgui.git
cd qmk-webgui
python3 -m http.server 8420
```

Open `http://127.0.0.1:8420/index.html`. `http.server` ships with Python's
standard library — nothing to install, works on any system with Python 3.
`localhost` counts as a secure context, so plain HTTP is fine here.
