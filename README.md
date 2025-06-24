# 🚀 Dockerized Multi-Service System with NGINX Reverse Proxy

This project demonstrates a containerized system with:

- 🟢 **Service 1:** Go API (Port `8001`)
- 🔵 **Service 2:** Python Flask API with `uv` (Port `8002`)
- 🔁 **NGINX Reverse Proxy:** Unified access via `localhost:8080`

Everything runs inside Docker containers using isolated bridge networking.

---

## 📦 Setup Instructions

⚡️ Clone the project and run:

```bash
docker-compose up --build
```

Then access:

✅ [http://localhost:8080/service1/ping](http://localhost:8080/service1/ping)\
✅ [http://localhost:8080/service1/hello](http://localhost:8080/service1/hello)\
✅ [http://localhost:8080/service2/ping](http://localhost:8080/service2/ping)\
✅ [http://localhost:8080/service2/hello](http://localhost:8080/service2/hello)

Check logs anytime:

```bash
docker-compose logs -f nginx
```

Run automated tests:

```bash
bash test.sh
```

---

## 🌐 How Routing Works

- `/service1 →` Routed to Go API container
- `/service2 →` Routed to Python Flask container
- NGINX centralizes all traffic on `localhost:8080`

---

## 🏱️ Bonus Features

✅ **Detailed Request Logging:**
- Logs include timestamp, path, status, bytes, and duration

✅ **Security Hardening with 3 Key Headers:**
- `X-Content-Type-Options: nosniff` -- Prevents MIME sniffing attacks
- `X-Frame-Options: DENY` -- Blocks clickjacking via iframes
- `X-XSS-Protection: 1; mode=block` -- Enables basic browser XSS protection

✅ **Automated Health Checks:**
- Both services monitored via `/ping` endpoint healthchecks

✅ **Test Automation:**
- `test.sh` script validates routes post-deployment

✅ **Lightweight, Production-Ready Images:**
- Uses slim/Alpine-based images for efficiency

---

## 🛡️ Quick Security Insight: What are These Headers?

1. Stops browsers from guessing file types, reducing XSS risks.

2. Prevents your app from being embedded in iframes, blocking clickjacking attacks.

3. Activates basic browser XSS filters for an extra layer of defense.

---

## ✅ One-Liner Summary

*"A secure, containerized microservice system with NGINX reverse proxy, centralized logging, essential security headers, health checks, and automated testing optimized for clean deployment."*

---
