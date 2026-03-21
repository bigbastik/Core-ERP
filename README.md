# 🚀 CORE ERP Multi‑Tenant  
Piattaforma ERP modulare, scalabile e multi‑tenant con architettura SaaS, edge security Cloudflare, API pubblica, automazioni contabili/logistiche e Social Monitoring.

---

## 🌍 Richiedi Subito Un Istanza di prova
🔗 **https://gestionale.bigbastik.de**

---

## 🧩 Moduli Principali

### 🔐 Autenticazione & Multi‑Tenancy
- Multi‑Domain Handshake (login centralizzato)
- JWT Session Interceptor
- RBAC: Superadmin / Admin / User
- Ghost Impersonation (accesso ai tenant senza credenziali)

### 🛡️ Edge Security (Cloudflare)
- WAF, Anti‑DDoS, Bot Management
- Universal SSL/TLS
- Subdomain Orchestration
- IP backend mascherato

### 🏗️ Backend Architecture
- Node.js + Express + PostgreSQL
- Controllers modulari
- Isolamento dati via `tenant_id`
- Servizi dedicati:
  - Accounting & Ledger
  - Credit Recovery Automation
  - PDF Engine
  - Stock Guard
  - Audit Logging

### 📊 Dashboard & Frontend
- React 18 + Vite
- Tailwind CSS + Lucide Icons
- ThemeContext per brand identity per‑tenant
- KPI globali per sottodominio
- Layout responsive mobile‑first

### 🔑 Public API Engine
- API Keys per tenant (Client ID + Secret Key)
- Storage hash HMAC/SHA256
- API Middleware Tracker
- Rate Limiting per tenant
- Documentazione Swagger/OpenAPI

### 📣 Social Monitoring & Engagement Analytics
- Raccolta metriche social (Instagram, Facebook, LinkedIn, X)
- Interazioni: like, commenti, condivisioni, click
- KPI: reach, impression, CTR
- Correlazione campagne social ↔ fatturato
- API dedicate per importare eventi social

---

## 📘 Documentazione API  
🔗 **https://bigbastik.github.io/Core-ERP/docs/ondex.html**

---

## 🧱 Tech Stack
- **Frontend:** React 18, Vite, Tailwind CSS  
- **Backend:** Node.js, Express  
- **Database:** PostgreSQL  
- **Security:** JWT, Cloudflare WAF, SSL/TLS  
- **Storage:** PostgreSQL, LocalStorage 
