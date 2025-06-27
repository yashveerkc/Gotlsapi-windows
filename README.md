# Gotlsapi-windows
---

Gotlsapi is a powerful standalone **EXE-based reverse proxy** built with FastAPI + HTTPX. It allows you to forward HTTP requests with custom headers, proxy rotation, enforced header order, and optional protocol switching (HTTP/2). Designed especially for scenarios like **API tunneling, automated checkers, or bypass flows**, it works without installing Python or any dependencies.

> 🟢 Works out of the box — just run the EXE, and you're good to go.

---

## 🚀 Features

* ✅ Supports `GET`, `POST`, `PUT`, `DELETE`, `PATCH`, and more
* 🔀 Proxy injection with `ip:port:user:pass` auto-format
* 🔒 HTTP/2 protocol switch via `x-kc-protocol` header
* 🧠 Header order enforcement for bot protection bypassing
* ⏱️ Delay support via `x-kc-delay`
* 🛠️ Fully async with `httpx.AsyncClient` for speed
* 📦 No dependencies needed — just run the EXE!

---

## 🖥️ How to Use

1. **Download** the EXE from the [Releases](https://github.com/yashveerkc/Gotlsapi-windows/releases/tag/v1.0.0) section.
   ![screenshot](![image](https://github.com/user-attachments/assets/44fef1eb-00b6-4515-8e6e-274962eb936a)
2. **Run** the program:

   ```bat
   Gotlsapi.exe
   ```
3. **Select port** (Default: `9000`).
4. Send your request through the proxy:

   ```http
   POST http://localhost:9000/
   ```

---

## 🔧 Supported Headers

| Header             | Description                                                    |
| ------------------ | -------------------------------------------------------------- |
| `x-kc-url`         | Target URL to forward the request to (can be full or relative) |
| `x-kc-proxy`       | Proxy in format `ip:port:user:pass` or full URL                |
| `x-kc-protocol`    | `2` for HTTPS (HTTP/2), otherwise uses HTTP                    |
| `x-kc-headerorder` | Force header order (comma-separated)                           |
| `x-kc-delay`       | Add delay (in ms) before forwarding request                    |

> All non-`x-kc-` headers will be forwarded as-is to the target.

---

## 📁 Example Usage (Python)

```python
import requests

headers = {
    "x-kc-url": "https://netflix.com/api/someendpoint",
    "x-kc-proxy": "ip:port:user:pass",
    "x-kc-protocol": "2",
    "x-kc-headerorder": "User-Agent,Accept,Content-Type",
    "User-Agent": "Mozilla/5.0",
    "Accept": "application/json",
}

r = requests.post("http://localhost:9000/", headers=headers, data='{}')
print(r.text)
```

---

## 🛠️ Setup Instructions

```bash
# 1. Clone the repo
$ git clone https://github.com/YOUR-USER/Gotlsapi.git

# 2. Install dependencies
$ pip install -r requirements.txt

# 3. Run locally (for development)
$ python Gotlsapi.py

# 4. Or compile with Nuitka / PyInstaller
```

---

## 📦 Build Info

* ![Python](https://img.shields.io/badge/python-3.10%2B-blue)
* Written in: Python 3.10+
* Compiled with: **PyInstaller**
* Frameworks: `FastAPI`, `httpx`, `uvicorn`

---

## 📸 Screenshots

> ✅ Working login capture:
> ![Login success](https://github.com/user-attachments/assets/840128f0-0bd6-4be5-a1c9-3e636a095608)


> 🔄 Reverse Proxy Flow:
> ![Proxy](https://github.com/user-attachments/assets/4218e7cf-01e7-4552-9664-133dc62ed636)

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).

---

## 🤝 Credits

* **Built with ❤️ by [@YashvirGaming](https://github.com/YashvirGaming) — [Telegram: @therealyashvirgaming](https://t.me/therealyashvirgaming)** ![GitHub stars](https://img.shields.io/github/stars/yashveerkc/Gotlsapi?style=social) ![Twitter Follow](https://img.shields.io/twitter/follow/yashvir__gaming?style=social)
* Thanks to all testers and contributors for feedback!


