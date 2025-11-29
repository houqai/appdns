# AppDNS 🌐

**AppDNS** is a free, fast, and reliable Dynamic DNS (DDNS) service designed for home labs, servers, and IoT devices. It allows you to access your devices remotely using a custom subdomain, even if your IP address changes.

> � **Live Service:** [https://appdns.cloud](https://appdns.cloud)

---

## ✨ Features

*   **🔒 Secure:** Authentication via GitHub OAuth. No passwords to remember.
*   **⚡ Fast:** Powered by DigitalOcean DNS infrastructure with low propagation times.
*   **🌍 IPv4 & IPv6:** Full support for A and AAAA records.
*   **🛠 Simple API:** Update your IP with a single GET request.
*   **📦 Generous Limits:** Create up to 5 subdomains for free.
*   **📱 Modern UI:** Clean, responsive dashboard to manage your domains.

---

## 🚀 How It Works

1.  **Sign In:** Log in securely with your GitHub account.
2.  **Create:** Choose a unique subdomain (e.g., `my-server.appdns.cloud`).
3.  **Connect:** Get your unique token and configure your device to update its IP.

---

## 🔌 API Documentation

Updating your IP address is as simple as sending a web request. You can use `curl`, `wget`, or any cron job.

### Update Endpoint

```http
GET /update?domain=<your-subdomain>&token=<your-token>&ip=<optional-ip>
```

| Parameter | Type | Description |
| :--- | :--- | :--- |
| `domain` | `string` | **Required.** Your full subdomain (e.g., `test.appdns.cloud`). |
| `token` | `string` | **Required.** The unique token found in your dashboard. |
| `ip` | `string` | *Optional.* IPv4 address. If omitted, detects request IP. |
| `ipv6` | `string` | *Optional.* IPv6 address. |

### Examples

**Update with detected IP (Simplest):**
```bash
curl "https://appdns.cloud/update?domain=test.appdns.cloud&token=a1b2c3d4"
```

**Update with specific IP:**
```bash
curl "https://appdns.cloud/update?domain=test.appdns.cloud&token=a1b2c3d4&ip=1.2.3.4"
```

---

*Built with ❤️ for the community.*
