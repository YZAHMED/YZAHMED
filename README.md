<!-- Profile README: Yaqoob Zahoor Ahmed -->
<!-- Tip: rename your repo to yzahmed/yzahmed and use this as README.md -->

<!-- Header / Hero -->
<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=venom&height=220&color=0:0ea5e9,100:22c55e&text=Yaqoob%20Zahoor%20Ahmed&fontColor=ffffff&fontSize=48&animation=fadeIn&desc=Full‑Stack%20Developer%20•%20APIs%20•%20Cloud%20•%20UML&descAlignY=75" alt="Hero Banner"/>
</p>

<p align="center">
  <a href="mailto:y.zahoorahmed@gmail.com"><img src="https://img.shields.io/badge/Email-y.zahoorahmed%40gmail.com-0ea5e9?style=for-the-badge&logo=gmail&logoColor=white"/></a>
  <a href="https://github.com/yzahmed"><img src="https://img.shields.io/badge/GitHub-@yzahmed-111827?style=for-the-badge&logo=github"/></a>
  <a href="https://linkedin.com/in/yzahmed"><img src="https://img.shields.io/badge/LinkedIn-Connect-0a66c2?style=for-the-badge&logo=linkedin"/></a>
  <img src="https://img.shields.io/badge/Status-Canadian%20PR-22c55e?style=for-the-badge"/>
</p>

---

## 👋 About Me
I’m **Yaqoob**, a postgraduate student at **Humber College (Web Development)** and a hands‑on **full‑stack developer** who enjoys building **clean APIs, scalable services, and useful developer tools**. I think in systems (and draw them too): **UML/Mermaid**, **OAuth2/PKCE flows**, and **microservice architectures** with pragmatic performance in mind.

- 🔧 **Core Stack:** C#, JavaScript/TypeScript, React, Node.js, Go (Golang)  
- 🗄️ **Data:** SQL (MySQL, SQL Server, PostgreSQL), NoSQL (MongoDB, Firebase)  
- ☁️ **Infra:** Docker, Kubernetes, Proxmox, CI/CD basics  
- 🧭 **Design:** UML (Mermaid), SDLC (Agile/Iterative), API-first  
- 🛡️ **Focus:** Security, reliability, compliance, developer productivity

> I’m open to **internships, co‑ops, and junior developer roles**.

---

## 🚀 Featured Projects

### 1) Device Generator for Testing & Debugging · <sub><sup>*Node.js, Go, Express, Concurrency*</sup></sub>
Generates **realistic (non‑identifiable)** device profiles for cross‑platform testing. Exposes a **simple REST API** so teams can request devices without reinventing generators.
- ⚙️ Node/Express validation → Go microservice with **goroutines + worker pools**
- ♾️ Practically **indefinite unique** combinations; crafted to pass system checks for robust QA
- 🎯 Use it to populate automated tests, emulate mobile‑on‑desktop, and seed environments

```http
POST /api/devices
Content-Type: application/json

{ "platform": "android", "locale": "en-CA" }
```

---

### 2) Secure Authentication URL Generator · <sub><sup>*OAuth2, PKCE, Node.js*</sup></sub>
Builds **specialized auth URLs** accepted by enterprise‑scale apps; returns valid **authorization codes** for testing secure login flows.
- 🔐 Covers **PKCE**, redirect URIs, and token exchange
- 🧪 Validates client configs and edge‑cases without manual URL crafting

---

### 3) MultiStore Order Management System · <sub><sup>*MySQL*</sup></sub>
Relational design with **triggers, views, and stored procedures** to automate operations across two collaborating stores.
- ✅ Normalization, constraints, integrity checks
- 📊 Reusable scripts + clear reporting queries

---

### 4) BootCampCool – Fan Control App · <sub><sup>*C#*</sup></sub>
Windows desktop utility for Bootcamped MacBooks.
- 🌡️ Manual/auto fan control, high‑temp alerts
- 📝 CSV logging, tray/background mode
- 🧱 Clean OOP + event‑driven design

---

### 5) TxtMaster – Text Automation Utility · <sub><sup>*JavaScript, Node.js*</sup></sub>
Productivity toolkit for **text transformation** and batch formatting with a modular rules engine.

---

### 6) Tax Calculator Chrome Extension · <sub><sup>*JavaScript, Chrome APIs*</sup></sub>
In‑page **real‑time** tax calculations during online transactions with DOM parsing and configurable rules.

---

### 7) Markdown Portfolio · <sub><sup>*React, Node.js*</sup></sub>
A clean, responsive portfolio powered by Markdown content + React components.  
🔗 Live: https://yzahmed.github.io/markdown-portfolio/

---

## 🧠 I Think in Diagrams (Mermaid)

<details>
  <summary><b>Auth (PKCE) sequence</b> – click to expand</summary>

```mermaid
sequenceDiagram
  autonumber
  participant Client as Client App
  participant AS as Auth Server
  participant RS as Resource Server

  Client->>Client: Generate code_verifier + code_challenge
  Client->>AS: /authorize?client_id&redirect_uri&code_challenge
  AS-->>Client: redirect with authorization_code
  Client->>AS: /token (code + code_verifier)
  AS-->>Client: access_token (+ refresh_token)
  Client->>RS: GET /resource (Bearer access_token)
  RS-->>Client: 200 OK (data)
```
</details>

<details>
  <summary><b>Device Generation (high‑level)</b> – click to expand</summary>

```mermaid
flowchart LR
  A[Client Request] -->|validate| B(Node.js API)
  B -->|enqueue| C[Worker Pool]
  C --> D(Go Service)
  D -->|goroutines| E{Generate Device Profile}
  E -->|unique, non-identifiable| F[(Store/Return)]
  F --> G[Response JSON]
```
</details>

---

## 🧰 Toolbox
**Languages/Frameworks:** C#, JavaScript/TypeScript, React, Node.js, Go, Java (learning), Python (basic)  
**Databases:** MySQL, SQL Server, PostgreSQL, MongoDB, Firebase  
**Infra:** Docker, Kubernetes, Proxmox, Oracle Cloud (Free Tier)  
**Design & Process:** UML (Mermaid), SDLC (Agile/Iterative), OAuth2/PKCE  
**Other:** Git/GitHub, Visual Studio, VS Code, Figma, MS Office

---

## 📊 GitHub at a Glance
<p align="left">
  <img height="160" src="https://github-readme-stats.vercel.app/api?username=yzahmed&show_icons=true&theme=transparent&hide_border=true" alt="GitHub Stats"/>
  <img height="160" src="https://github-readme-stats.vercel.app/api/top-langs/?username=yzahmed&layout=compact&theme=transparent&hide_border=true" alt="Top Languages"/>
</p>

---

## 📫 Connect
- 🐙 GitHub: https://github.com/yzahmed  
- 💼 LinkedIn: https://linkedin.com/in/yzahmed  
- ✉️ Email: y.zahoorahmed@gmail.com

> **Note:** I’m a **Canadian Permanent Resident (PR)** and open to internships, co‑ops, and junior dev roles.
