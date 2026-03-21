# 🚀 CORE ERP – Public API Documentation (V3.0)

Questa documentazione descrive le API pubbliche della piattaforma **CORE ERP Multi‑Tenant**, incluse le estensioni per il modulo di **Social Monitoring & Engagement Analytics**.

---

## 📑 Indice

- [Autenticazione](#autenticazione)
- [API Keys](#api-keys)
- [Rate Limiting](#rate-limiting)
- [Endpoints](#endpoints)
  - [Customers](#customers)
  - [Invoices](#invoices)
  - [Products](#products)
  - [Stock](#stock)
  - [Accounting](#accounting)
  - [Social Monitoring](#social-monitoring)
- [Errori](#errori)
- [Webhooks (coming soon)](#webhooks-coming-soon)
- [Best Practices](#best-practices)

---

## 🔐 Autenticazione

L’autenticazione avviene tramite **API Key** generata dal pannello del tenant.

### Header richiesto

X-API-KEY: 1f92a8c1-xxxx-xxxx-xxxx-xxxxxxxxxxxx
</code></pre>

<hr>

<h2 id="ratelimit">🚦 Rate Limiting</h2>
<p>
  Ogni tenant ha un limite di:
</p>

<pre><code>100 richieste / minuto</code></pre>

<p>
  In caso di superamento viene restituito:
</p>

<pre><code>{
  "error": "rate_limit_exceeded",
  "retry_after": 60
}
</code></pre>

<hr>

<h2 id="endpoints">📌 Endpoints Principali</h2>

<h3>👥 Customers</h3>

<div class="endpoint">
  <span class="method">GET</span> /api/v1/customers
</div>
<p>Restituisce la lista clienti del tenant.</p>

<div class="endpoint">
  <span class="method">POST</span> /api/v1/customers
</div>
<p>Crea un nuovo cliente.</p>

<pre><code>{
  "name": "Mario Rossi",
  "email": "mario@example.com",
  "vat": "IT12345678901",
  "payment_terms": 30
}
</code></pre>

---

<h3>🧾 Invoices</h3>

<div class="endpoint">
  <span class="method">GET</span> /api/v1/invoices
</div>

<div class="endpoint">
  <span class="method">POST</span> /api/v1/invoices
</div>

<pre><code>{
  "customer_id": "uuid",
  "items": [
    { "product_id": "uuid", "qty": 2 }
  ]
}
</code></pre>

---

<h3>📦 Products</h3>

<div class="endpoint">
  <span class="method">GET</span> /api/v1/products
</div>

<div class="endpoint">
  <span class="method">POST</span> /api/v1/products
</div>

<pre><code>{
  "name": "Prodotto A",
  "sku": "A-001",
  "initial_stock": 50
}
</code></pre>

---

<h3>📉 Stock Movements</h3>

<div class="endpoint">
  <span class="method">GET</span> /api/v1/stock
</div>

<div class="endpoint">
  <span class="method">POST</span> /api/v1/stock/in
</div>

<div class="endpoint">
  <span class="method">POST</span> /api/v1/stock/out
</div>

---

<h3>📘 Accounting</h3>

<div class="endpoint">
  <span class="method">GET</span> /api/v1/accounting/ledger
</div>

<div class="endpoint">
  <span class="method">POST</span> /api/v1/accounting/entry
</div>

<pre><code>{
  "type": "debit",
  "amount": 120.50,
  "description": "Pagamento fattura"
}
</code></pre>

---

<h3>📣 Social Monitoring & Engagement</h3>

<p>
  Il modulo Social Monitoring permette di tracciare le performance dei canali social per ogni tenant.
</p>

<div class="endpoint">
  <span class="method">GET</span> /api/v1/social/channels
</div>
<p>Restituisce la lista dei canali social collegati al tenant.</p>

<div class="endpoint">
  <span class="method">GET</span> /api/v1/social/metrics
</div>
<p>Restituisce le metriche aggregate per periodo.</p>

<pre><code>
GET /api/v1/social/metrics?from=2025-01-01&to=2025-01-31&channel=instagram
</code></pre>

<p>Risposta esempio:</p>
<pre><code>{
  "channel": "instagram",
  "from": "2025-01-01",
  "to": "2025-01-31",
  "metrics": {
    "likes": 1240,
    "comments": 210,
    "shares": 85,
    "clicks": 430,
    "impressions": 18200,
    "reach": 9400
  }
}
</code></pre>

<div class="endpoint">
  <span class="method">POST</span> /api/v1/social/events
</div>
<p>Endpoint per importare eventi social (se usato in modalità push da integrazioni esterne).</p>

<pre><code>{
  "channel": "facebook",
  "external_id": "post_123",
  "type": "like",
  "count": 10,
  "timestamp": "2025-01-15T10:30:00Z"
}
</code></pre>

<hr>

<h2 id="errors">❗ Errori</h2>

<h3>Formato errore standard</h3>
<pre><code>{
  "error": "invalid_request",
  "message": "Missing field: customer_id"
}
</code></pre>

<h3>Errori comuni</h3>
<ul>
  <li><code>unauthorized</code> – API Key mancante o invalida</li>
  <li><code>rate_limit_exceeded</code></li>
  <li><code>not_found</code></li>
  <li><code>validation_error</code></li>
</ul>

<hr>

<h2 id="webhooks">📡 Webhooks (Coming Soon)</h2>
<p>
  La piattaforma supporterà eventi come:
</p>

<ul>
  <li><code>invoice.created</code></li>
  <li><code>invoice.paid</code></li>
  <li><code>stock.low</code></li>
  <li><code>customer.created</code></li>
  <li><code>social.metrics.updated</code></li>
</ul>

<hr>

<h2 id="best">🧠 Best Practices</h2>

<ul>
  <li>Rigenerare periodicamente le API Keys</li>
  <li>Usare sempre HTTPS (Cloudflare SSL)</li>
  <li>Limitare le chiamate batch e rispettare il rate limit</li>
  <li>Non esporre mai la Secret Key lato client</li>
  <li>Correlare metriche social con KPI di fatturato per analisi avanzate</li>
</ul>

<hr>

<p style="margin-top:2rem; color:#64748b;">
  CORE ERP Multi-Tenant – © BigBastik
</p>

</body>
</html>
