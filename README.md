# Observability Stack with Prometheus, Loki & Grafana

## 📌 Project Overview
Repository ini merupakan implementasi observability stack menggunakan Docker Compose untuk melakukan monitoring metrics dan logging pada server Linux.

Project ini dibuat sebagai latihan praktik untuk memahami konsep monitoring modern yang umum digunakan pada environment DevOps dan Infrastructure.

Stack ini menggabungkan:
- Prometheus → Metrics monitoring
- Loki → Log aggregation
- Promtail → Log collector
- Grafana → Visualization dashboard

---

## 🎯 Project Goals
- Memantau performa sistem menggunakan metrics
- Mengumpulkan log container & system
- Menyediakan dashboard monitoring terpusat
- Memahami arsitektur observability modern

---

## 🏗️ Architecture Overview

Host System / Docker Containers  
        ↓  
     Promtail  
        ↓  
        Loki  
        ↓  
      Grafana  

System Metrics  
      ↓  
  Prometheus  
      ↓  
    Grafana Dashboard  

---

## ⚙️ Services Explanation

### ✅ Prometheus — Metrics Collection
Digunakan untuk mengumpulkan metrics sistem seperti:
- CPU Usage
- Memory Usage
- Disk Usage
- Container metrics

Access:
http://localhost:9090

---

### ✅ Loki — Log Aggregation
Loki berfungsi sebagai centralized logging system yang menyimpan log dari host dan container Docker.

Access:
http://localhost:3100

---

### ✅ Promtail — Log Agent
Promtail bertugas mengumpulkan log dari:

- `/var/log`
- Docker container logs

Kemudian mengirim log tersebut ke Loki.

Mounted paths:
- /var/log
- /var/lib/docker/containers

---

### ✅ Grafana — Visualization Dashboard
Grafana digunakan untuk visualisasi metrics dan log monitoring dalam bentuk dashboard interaktif.

Access:
http://localhost:3000

Default Login:
- username: admin
- password: admin

---

## 🧰 Technology Stack
- Docker
- Docker Compose
- Prometheus
- Grafana
- Loki
- Promtail
- Linux Monitoring

---

## 🚀 How to Run

Clone repository:

```bash
git clone https://github.com/WannSkyy/docker-observability-stack
cd docker-observability-stack
docker compose up -d
