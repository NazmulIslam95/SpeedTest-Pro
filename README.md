# ⚡ SpeedTest Pro

**SpeedTest Pro** is a sleek, real‑time internet speed testing web application.  
It measures **ping**, **download speed**, and **upload speed** with live‑updating radial gauges and a modern glassmorphism UI.  

🔗 **Live Demo**: [https://speedtest-me.netlify.app/](https://speedtest-me.netlify.app/)  
📦 **GitHub Repository**: [https://github.com/NazmulIslam95/SpeedTest-Pro](https://github.com/NazmulIslam95/SpeedTest-Pro)

---

## ✨ Features

- **Live real‑time metering** – Download & upload speeds update continuously during the test.
- **Dual radial speed gauges** – Separate animated dials for download (blue) and upload (orange).
- **Instant ping measurement** – Low‑latency test using lightweight HEAD requests.
- **Comprehensive metrics panel** – Displays ping (ms), download (Mbps), upload (Mbps).
- **Network info** – Shows your public IP address, server/ISP, and connection type (4G, 5G, Wi‑Fi…).
- **Test cancellation** – Abort any ongoing test with a single click.
- **Fully responsive** – Works seamlessly on desktop, tablet, and mobile devices.
- **Glassmorphism + animated background** – Frosted glass effect with a moving wave pattern.
- **Fallback mechanisms** – Multiple endpoints guarantee reliable results.

---

## 🛠️ Technologies Used

- **HTML5** – Semantic elements, inline SVG for gauges.
- **CSS3** – Flexbox, Grid, CSS animations, backdrop‑filter, media queries.
- **JavaScript (ES6+)** – Fetch API, `AbortController`, `ReadableStream`.
- **External APIs**:
  - [ipify.org](https://www.ipify.org/) – Public IP address retrieval.
  - [Cloudflare Speed Test API](https://speed.cloudflare.com/__down) – Download speed test.
  - [httpbin.org](https://httpbin.org/post) – Upload test fallback.
  - Google favicon – Ping measurement via `HEAD` requests.

---

## ⚙️ How It Works

1. **Ping** – Sends three `HEAD` requests to `https://www.google.com/favicon.ico` and averages the latency.
2. **Download**  
   - *Primary*: Streams a 10 MB file from Cloudflare’s endpoint, measuring speed live with `ReadableStream`.  
   - *Fallback*: Downloads a random large image and calculates overall throughput.
3. **Upload**  
   - *Primary*: Uploads a 2.5 MB binary blob to `https://httpbin.org/post` and measures total time.  
   - *Fallback*: Uses Cloudflare’s upload endpoint or simulates progressive speed updates.
4. **Network Info** – Public IP via ipify; connection type via `navigator.connection.effectiveType`.

All tests run sequentially and the UI updates in real time.

---

## 🚀 Getting Started

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/NazmulIslam95/SpeedTest-Pro.git
   cd SpeedTest-Pro
   ```

2. **Open the application**  
   - Simply open `index.html` in your browser, **or**  
   - Serve it locally:
     ```bash
     python3 -m http.server 8000
     ```
     Then visit `http://localhost:8000`

3. **Start testing** – Click the **START SPEED TEST** button.

---

## 🎨 Customization

### Change max gauge speed (default 300 Mbps)

Edit `script.js` and adjust the `maxSpeed` parameter:

```js
updateGauge(downloadGaugeFill, speedMbps, 500); // new max = 500 Mbps
```

### Modify test file sizes

- **Download test** – Change `bytes` parameter in Cloudflare URL (`10_000_000` → new size in bytes).
- **Upload test** – Change `payloadSize = 2_500_000` (bytes).

### Styling

All CSS is in `style.css`. Change gradients, wave color, glassmorphism intensity as needed.

---

## 🌐 Browser Support

| Browser          | Minimum Version | Notes                                  |
|------------------|----------------|----------------------------------------|
| Chrome           | 70+            | Full support                           |
| Firefox          | 65+            | Full support                           |
| Safari           | 14+            | Requires `ReadableStream` support      |
| Edge             | 79+            | Full support                           |
| Mobile browsers  | Latest         | Optimised for touch and small screens  |

> Internet Explorer is **not supported**.

---

## 📁 Project Structure

```
SpeedTest-Pro/
├── index.html
├── style.css
├── script.js
├── assets/favicon/
└── README.md
```

---

## 🙏 Credits & Acknowledgements

- **[ipify.org](https://www.ipify.org/)** – Public IP API.
- **[Cloudflare](https://speed.cloudflare.com/)** – Download & upload speed endpoints.
- **[httpbin.org](https://httpbin.org/)** – HTTP request testing service.
- Google – Favicon for ping measurements.
- Fonts: [Inter](https://fonts.google.com/specimen/Inter) & [JetBrains Mono](https://www.jetbrains.com/lp/mono/) from Google Fonts.

---

## 📄 License

MIT License – free to use, modify, and distribute.

---

## 🤝 Contributing

Contributions are welcome! Please open an [issue](https://github.com/NazmulIslam95/SpeedTest-Pro/issues) or submit a pull request.

---

**Built with ⚡ by [Nazmul Islam](https://github.com/NazmulIslam95)**
