# CORE ERP Multi-Tenant – Technical Overview (V3.0)

CORE ERP è una **piattaforma ERP multi-tenant** progettata come **SaaS cloud platform**, con:

- isolamento logico per tenant,
- edge security Cloudflare,
- API pubblica con API Keys,
- automazioni contabili e logistiche,
- audit logging forense,
- modulo di **Social Monitoring & Engagement Analytics**.

> Questo repository è una **vetrina tecnica**.  
> Il codice sorgente dell’applicazione non è pubblico.

---

## 🌍 Link Ufficiale

🔗 **Piattaforma:** https://gestionale.bigbastik.de  
📘 **Documentazione API:** `./docs/index.html`

---

## 🛡️ Core Engine & Authentication

- Multi-Domain Handshake su `bigbastik.de`
- JWT Session Interceptor (React)
- RBAC: Superadmin, Admin, User
- Ghost Impersonation per accesso controllato ai tenant

---

## 🌐 Edge Security (Cloudflare)

- WAF, Anti-DDoS, Bot Management
- Universal SSL/TLS per ogni tenant
- Subdomain Orchestration su `*.bigbastik.de`
- IP backend mascherato

---

## 🏗️ Backend Architecture

- Node.js + Express + PostgreSQL
- Controllers modulari (auth, admin, invoices, customers, warehouse, accounting, tenants)
- Isolamento dati via `tenant_id` (UUID)
- Servizi dedicati:
  - Accounting & Ledger
  - Credit Recovery Automation
  - PDF Engine
  - Stock Guard
  - Audit Logging

---

## 📊 Frontend & Dashboard

- React 18 + Vite
- Tailwind CSS + Lucide Icons
- ThemeContext per brand identity per-tenant
- KPI globali per sottodominio
- Layout responsive mobile-first

---

## 🔑 Public API Engine

- API Keys per tenant (Client ID + Secret Key)
- Storage hash HMAC/SHA256
- API Middleware Tracker
- Rate Limiting per tenant
- Documentazione Swagger/OpenAPI (`/api/v1/docs`)

---

## 📣 Social Monitoring & Engagement Analytics

Modulo dedicato al monitoraggio delle performance social per ogni tenant:

- Raccolta metriche da canali social (es. Facebook, Instagram, LinkedIn, X)
- Tracciamento di:
  - like, commenti, condivisioni, click
  - reach, impression, CTR
- Dashboard di correlazione:
  - campagne social ↔ fatturato
  - engagement ↔ LTV clienti
- API dedicate per importare/aggiornare dati social

---

## 🧱 Tech Stack

**Frontend:** React 18, Vite, Tailwind CSS  
**Backend:** Node.js, Express  
**Database:** PostgreSQL  
**Security:** JWT, Cloudflare WAF, SSL/TLS  
**Storage:** PostgreSQL, LocalStorage (sessioni)

---

## 📩 Contatti

Per collaborazioni o integrazioni:  
👉 *https://bigbastik.de - bigbastik@protonmail.ch*

