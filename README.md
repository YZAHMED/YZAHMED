<!-- GitHub Profile README · Yaqoob Ahmed · Site Reliability Engineer & Systems Engineer -->

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&height=220&color=0:0d1117,50:58a6ff,100:3fb950&text=Yaqoob%20Ahmed&fontColor=ffffff&fontSize=54&animation=fadeIn&desc=Site%20Reliability%20Engineer%20%C2%B7%20Systems%20Engineer&descAlignY=72&descSize=18" alt="Yaqoob Ahmed — Site Reliability Engineer & Systems Engineer"/>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/%E2%97%8F_Open_to_opportunities-3fb950?style=for-the-badge&labelColor=0d1117" alt="Open to opportunities"/>
  <img src="https://img.shields.io/badge/Canada-58a6ff?style=for-the-badge&labelColor=0d1117" alt="Canada"/>
  <img src="https://img.shields.io/badge/Remote--friendly-d29922?style=for-the-badge&labelColor=0d1117" alt="Remote-friendly"/>
  <img src="https://img.shields.io/badge/Open_to_global_relocation-58a6ff?style=for-the-badge&labelColor=0d1117" alt="Open to global relocation"/>
</p>

<p align="center">
  <a href="https://yaqoobahmed.com"><img src="https://img.shields.io/badge/Portfolio-yaqoobahmed.com-58a6ff?style=for-the-badge&logo=cloudflarepages&logoColor=white&labelColor=0d1117"/></a>
  <a href="https://yaqoobahmed.com/resume"><img src="https://img.shields.io/badge/Resume-PDF%20%26%20HTML-c9d1d9?style=for-the-badge&logo=readthedocs&logoColor=white&labelColor=0d1117"/></a>
  <a href="mailto:work@yaqoobahmed.com"><img src="https://img.shields.io/badge/Email-work@yaqoobahmed.com-d29922?style=for-the-badge&logo=protonmail&logoColor=white&labelColor=0d1117"/></a>
  <a href="https://github.com/yzahmed"><img src="https://img.shields.io/badge/GitHub-@yzahmed-c9d1d9?style=for-the-badge&logo=github&logoColor=white&labelColor=0d1117"/></a>
</p>

<p align="center">
  <a href="https://ssl.yaqoobahmed.com"><img src="https://img.shields.io/badge/Live-ssl.yaqoobahmed.com-3fb950?style=flat-square&logo=letsencrypt&logoColor=white&labelColor=0d1117"/></a>
  <a href="https://encryption.yaqoobahmed.com"><img src="https://img.shields.io/badge/Live-encryption.yaqoobahmed.com-3fb950?style=flat-square&logo=letsencrypt&logoColor=white&labelColor=0d1117"/></a>
</p>

---

## `$ whoami`

I'm an SRE / systems engineer who builds production systems from first principles — **automated incident response, edge compute networks, applied cryptography**. The kind of work that runs unattended, has to recover when no one's watching, and where the test suite *is* the spec.

I read the actual specs, not the blog posts. Most of what I work on doesn't have a tutorial, so I trace syscalls, decompile binaries, and read kernel docs at odd hours until I understand what the system is *actually* doing — and then I implement against that understanding.

A few patterns that show up across my work:

- **Correctness over expedience.** GTID-based replication, not "good enough" binlog position; cross-runtime parity validated against thousands of test vectors; safety-governed automation that pages a human before it does something dangerous.
- **Designing around constraints, not fighting them.** Reverse WebSocket tunneling because residential CGNAT is permanent; KV-only hot paths because cold-start latency is non-negotiable; broker-blind encryption because trust in third-party infrastructure shouldn't be load-bearing.
- **Hand-built, end-to-end.** Vanilla HTML/CSS portfolios, scratch Docker images, custom systemd units, kernel sysfs hooks. If I can build it without a framework, I usually do.

---

## `$ ls -la /projects`

> Engineering write-ups with full architecture diagrams live at **[yaqoobahmed.com/#projects](https://yaqoobahmed.com/#projects)**. Repos below; the portfolio is the deeper read.

### ▸ Self-Healing SRE Trading Platform · `Featured`
> Kubernetes (K3s, GKE) · Apache Kafka · MySQL GTID · HAProxy · Terraform · Ansible · HashiCorp Vault · Prometheus · Grafana · Chaos Engineering

Production-grade SRE platform: hybrid cloud (Proxmox + GCP), three-tier architecture, automated MySQL failover via GTID set comparison, and a **safety-governed incident control plane** that refuses to promote a replica unless it can prove the promotion is safe. Chaos-validated against process kills, network partitions, broker eviction, and Vault seals.

`<10s` automated DB failover · `~70%` MTTR reduction · `99.9%` SLO target · `0` unsafe promotions · alert-correlation reduces noise without losing signal

[Repo](https://github.com/YZAHMED/sre-trading-simulator) · [Deep dive →](https://yaqoobahmed.com/projects/sre-trading-platform)

---

### ▸ Distributed Cryptographic Signing & Token Platform · `Anonymised`
> Go · Node.js · TypeScript · C# (reference) · GCP Cloud Run · GCP Cloud Functions · Cloudflare Workers · Firebase Auth · Stripe

A multi-runtime implementation of an **undocumented proprietary authentication protocol**, built byte-for-byte against the reference C# binary across Go, Node.js, and TypeScript runtimes. Includes a serverless deployment, a Cloudflare Workers JWT gateway with Firebase JWKS verification at the edge, and a KV-backed Stripe subscription state machine with no origin server.

`2,000+` cross-runtime test vectors at 100% pass · `byte-for-byte` parity vs reference implementation · `PBKDF2 · AES-CBC · HMAC-SHA256 · ECDSA P-256` from spec, no library shortcuts · sub-millisecond per-token generation in Go · ships as a 12 MB scratch image

[Deep dive →](https://yaqoobahmed.com/projects/cryptographic-signing-platform) · [Edge gateway →](https://yaqoobahmed.com/projects/edge-api-gateway) · [Go performance generator →](https://yaqoobahmed.com/projects/go-device-generator)

---

### ▸ TLS Certificate Chain Inspector · `Live`
> Node.js · Netlify Functions · X.509 · OCSP · CRL · SPKI Pinning · Multi-Trust-Store Comparison

Cryptographic chain validation, not just expiry checks: child→parent signature verification, OCSP revocation, CRL parsing, side-by-side comparison against Mozilla / Apple / Google / system trust stores, SPKI hashes for pinning. Built after a real incident where a "valid" certificate chain wasn't actually trusted by every relying party.

[**Live → ssl.yaqoobahmed.com**](https://ssl.yaqoobahmed.com) · [Deep dive →](https://yaqoobahmed.com/projects/tls-certificate-inspector)

---

### ▸ X.509 Encryption Service · `Live`
> Node.js (ESM) · Netlify Functions · RSA-OAEP · Self-signed CA + server certs · node-forge

End-to-end RSA encryption demo deployed serverless. Self-signed CA → server cert chain, application-level RSA-OAEP on top of TLS, ESM/CommonJS interop in a bundled serverless target. A small project that exists because I wanted to *fully* understand PKI rather than rely on it.

[**Live → encryption.yaqoobahmed.com**](https://encryption.yaqoobahmed.com)

---

### ▸ Hardware-Backed Key Attestation — Security Research · `Anonymised`
> Android Keystore · setAttestationChallenge · X.509 attestation chains · JADX · mitmproxy

Reverse-engineering analysis of a production Android app's attestation flow. Documented a critical finding: the device-identity field used throughout the attestation flow is **not cryptographically bound to the hardware-backed attestation certificate chain**, breaking the trust model in multi-tenant device scenarios. Methodology, vulnerability writeup, and remediation suggestions documented end-to-end.

---

### ▸ Global Egress Orchestration · `In Progress`
> Node.js · Dart · Redis · Cloudflare Zero Trust · Reverse WebSocket · ARM thermal/sysfs tuning · Headless ops

Residential ARM nodes tunneled to Oracle Cloud over reverse WebSocket. **Zero inbound ports, zero static IPs, zero hardware deaths**. CGNAT is treated as a constraint of the physical world, not an obstacle to defeat — out-of-band management is via Cloudflare Zero Trust SSH, not port-forwarded admin panels.

[Deep dive →](https://yaqoobahmed.com/projects/global-egress-orchestration)

---

### ▸ The Pocket Data Center · `Bare Metal`
> PostmarketOS · Docker on ARM64 · 4-watt power envelope · Kernel sysfs · ALSA · ModemManager · systemd

Wiped Android off a OnePlus 6, flashed PostmarketOS, ran a full Docker stack on ARM64 at 4 watts. **Battery charge limits via raw `/sys/class/power_supply` writes**, SSD on OTG for database I/O, SMS gateway through the Qualcomm modem (`mmcli`), ALSA routing for live cellular calls, custom systemd units for everything. The hardware costs less than a month of cloud.

[Deep dive →](https://yaqoobahmed.com/projects/oneplus6-linux-server)

---

### ▸ End-to-End Encrypted MQTT Gateway
> Node.js · MQTT.js · AES-256-CBC · Broker-Blind E2E

The broker is **structurally blind to payload content**. AES-256-CBC at the publisher, ciphertext through Mosquitto, decrypt at the subscriber. Routing and reliability without trusting the broker's confidentiality — useful when the broker is operated by someone whose threat model isn't yours.

[Deep dive →](https://yaqoobahmed.com/projects/iot-mqtt-gateway)

---

### ▸ This Portfolio Site
> Vanilla HTML / CSS / Vanilla JS · Cloudflare Pages · No frameworks · No trackers · Lighthouse-perfect

Hand-built [yaqoobahmed.com](https://yaqoobahmed.com): single 23 KB CSS file, 50 bytes of JS for theme + year update, fluid typography, AAA contrast, semantic HTML, full security headers (HSTS preload, CSP, COOP, Permissions-Policy, X-Frame-Options), structured-data graph (Person + WebSite + Project + BreadcrumbList), inline SVG favicon and OG card. Footer says "no frameworks, no trackers" because the source proves it.

---

## `$ ./architecture --diagrams`

> A picture is worth a thousand words. So is `kubectl describe`. I do both.

### Incident Control Plane — Safety-Governed Failover

```mermaid
sequenceDiagram
  autonumber
  participant H as HAProxy (L4)
  participant CP as Control Plane
  participant P as MySQL Primary
  participant R as Replica (most-advanced)
  participant A as Alertmanager

  H->>P: TCP health check (every 2s)
  P--xH: timeout
  H->>CP: DBPrimaryDown alert (T+0s)
  CP->>CP: Validate sustained failure (T+2s)
  CP->>R: Compare GTID executed sets across replicas
  R-->>CP: Most-advanced replica identified
  CP->>CP: Verify safety conditions<br>(GTID superset · heartbeat threshold · partition rules)
  alt Safety conditions met
    CP->>R: Promote to primary (T+8s)
    CP->>H: Reconfigure backend pool
    H-->>CP: Traffic flowing (T+10s)
    Note over CP,R: Zero data loss · Zero unsafe promotions
  else Ambiguous failure (split-brain risk)
    CP->>A: Page on-call with pre-validated runbook
    Note over CP,A: Human judgment > blind automation
  end
```

### Edge Egress — Reverse Tunnels Through CGNAT

```mermaid
flowchart LR
  Client[Public Client]
  OCI[Oracle Cloud<br>Orchestrator]
  Redis[(Redis<br>Pub/Sub)]
  Edge1[ARM Edge Node A<br>residential / CGNAT]
  Edge2[ARM Edge Node B<br>residential / CGNAT]
  CFZT[Cloudflare<br>Zero Trust SSH]
  Target1[Target Resource]
  Target2[Target Resource]

  Client -->|HTTPS| OCI
  OCI -->|enqueue task| Redis
  Redis -.->|reverse WS<br>outbound only| Edge1
  Redis -.->|reverse WS<br>outbound only| Edge2
  Edge1 -->|outbound| Target1
  Edge2 -->|outbound| Target2
  CFZT -.->|out-of-band mgmt| Edge1
  CFZT -.->|out-of-band mgmt| Edge2

  classDef edge fill:#0d1117,stroke:#58a6ff,color:#fff,stroke-width:2px
  classDef cloud fill:#0d1117,stroke:#3fb950,color:#fff,stroke-width:2px
  classDef ext fill:#161b22,stroke:#8b949e,color:#fff,stroke-width:1px
  class Edge1,Edge2 edge
  class OCI,Redis,CFZT cloud
  class Client,Target1,Target2 ext
```

---

## `$ cat ~/.toolbox`

### Orchestration & Infrastructure
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white)
![Ansible](https://img.shields.io/badge/Ansible-EE0000?style=flat-square&logo=ansible&logoColor=white)
![Helm](https://img.shields.io/badge/Helm-0F1689?style=flat-square&logo=helm&logoColor=white)
![Vault](https://img.shields.io/badge/HashiCorp%20Vault-FFEC6E?style=flat-square&logo=vault&logoColor=black)
![Proxmox](https://img.shields.io/badge/Proxmox-E57000?style=flat-square&logo=proxmox&logoColor=white)
![systemd](https://img.shields.io/badge/systemd-22272e?style=flat-square)

### Reliability & Observability
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white)
![NGINX](https://img.shields.io/badge/NGINX-009639?style=flat-square&logo=nginx&logoColor=white)
![HAProxy](https://img.shields.io/badge/HAProxy-1F2C40?style=flat-square&logo=haproxy&logoColor=white)
![SLOs · Error Budgets · Chaos Engineering](https://img.shields.io/badge/SLOs%20%C2%B7%20Error%20Budgets%20%C2%B7%20Chaos%20Engineering-22272e?style=flat-square)

### Cloud & Edge
![Google Cloud](https://img.shields.io/badge/Google%20Cloud-4285F4?style=flat-square&logo=googlecloud&logoColor=white)
![Cloud Run](https://img.shields.io/badge/Cloud%20Run%20%C2%B7%20Cloud%20Functions-4285F4?style=flat-square&logo=googlecloud&logoColor=white)
![Oracle Cloud](https://img.shields.io/badge/Oracle%20Cloud-F80000?style=flat-square&logo=oracle&logoColor=white)
![Cloudflare](https://img.shields.io/badge/Cloudflare-F38020?style=flat-square&logo=cloudflare&logoColor=white)
![Cloudflare Workers](https://img.shields.io/badge/Workers%20%C2%B7%20KV%20%C2%B7%20D1%20%C2%B7%20Pages-F38020?style=flat-square&logo=cloudflareworkers&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)

### Backend
![Go](https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![C#](https://img.shields.io/badge/C%23-512BD4?style=flat-square&logo=csharp&logoColor=white)
![Dart](https://img.shields.io/badge/Dart%20%C2%B7%20Flutter-0175C2?style=flat-square&logo=dart&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white)

### Data & Messaging
![MySQL](https://img.shields.io/badge/MySQL%20%28GTID%29-4479A1?style=flat-square&logo=mysql&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite%20%2F%20D1-003B57?style=flat-square&logo=sqlite&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![Apache Kafka](https://img.shields.io/badge/Apache%20Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white)
![MQTT](https://img.shields.io/badge/MQTT%20%28Mosquitto%29-660066?style=flat-square&logo=mqtt&logoColor=white)

### Security & Cryptography
![TLS / X.509](https://img.shields.io/badge/TLS%20%2F%20X.509%20%2F%20OCSP%20%2F%20CRL-005C99?style=flat-square&logo=letsencrypt&logoColor=white)
![OAuth 2.0 + PKCE](https://img.shields.io/badge/OAuth%202.0%20%2B%20PKCE-EB5424?style=flat-square&logo=auth0&logoColor=white)
![JWT](https://img.shields.io/badge/JWT%20%28Firebase%20JWKS%29-000000?style=flat-square&logo=jsonwebtokens&logoColor=white)
![WireGuard](https://img.shields.io/badge/WireGuard-88171A?style=flat-square&logo=wireguard&logoColor=white)
![Crypto Primitives](https://img.shields.io/badge/AES--CBC%20%C2%B7%20ECDSA%20P--256%20%C2%B7%20HMAC--SHA256%20%C2%B7%20PBKDF2-22272e?style=flat-square)
![Android Keystore](https://img.shields.io/badge/Android%20Keystore%20%C2%B7%20Hardware%20Attestation-3DDC84?style=flat-square&logo=android&logoColor=white)

### Networking, Analysis & RE
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)
![Wireshark](https://img.shields.io/badge/Wireshark-1679A7?style=flat-square&logo=wireshark&logoColor=white)
![mitmproxy](https://img.shields.io/badge/mitmproxy-000000?style=flat-square&logo=mitmproxy&logoColor=white)
![JADX](https://img.shields.io/badge/JADX%20%C2%B7%20dnSPY-22272e?style=flat-square)
![Cloudflare Zero Trust](https://img.shields.io/badge/Cloudflare%20Zero%20Trust-F38020?style=flat-square&logo=cloudflare&logoColor=white)
![CGNAT Traversal](https://img.shields.io/badge/CGNAT%20%C2%B7%20Reverse%20Tunnels-22272e?style=flat-square)

---

## `$ uptime --github`

<p align="center">
  <img height="170" src="https://github-readme-stats.vercel.app/api?username=yzahmed&show_icons=true&hide_border=true&bg_color=0d1117&title_color=58a6ff&icon_color=3fb950&text_color=c9d1d9&ring_color=58a6ff" alt="GitHub Stats"/>
  <img height="170" src="https://github-readme-stats.vercel.app/api/top-langs/?username=yzahmed&layout=compact&hide_border=true&bg_color=0d1117&title_color=58a6ff&text_color=c9d1d9&langs_count=8" alt="Top Languages"/>
</p>

<p align="center">
  <img src="https://streak-stats.demolab.com/?user=yzahmed&hide_border=true&background=0d1117&stroke=30363d&ring=58a6ff&fire=3fb950&currStreakLabel=58a6ff&sideLabels=c9d1d9&dates=8b949e&currStreakNum=c9d1d9&sideNums=c9d1d9" alt="GitHub Streak"/>
</p>

---

## `$ contact --how-to-reach`

|   |   |
|---|---|
| **Portfolio** | [yaqoobahmed.com](https://yaqoobahmed.com) — engineering write-ups + architecture diagrams |
| **Resume** | [yaqoobahmed.com/resume](https://yaqoobahmed.com/resume) — PDF + HTML |
| **Email** | [work@yaqoobahmed.com](mailto:work@yaqoobahmed.com) |
| **Live: TLS Inspector** | [ssl.yaqoobahmed.com](https://ssl.yaqoobahmed.com) — full chain validation |
| **Live: X.509 Encryption** | [encryption.yaqoobahmed.com](https://encryption.yaqoobahmed.com) — RSA-OAEP demo |
| **GitHub** | [@yzahmed](https://github.com/yzahmed) |
| **Status** | Open to remote / global relocation · prefer reliability-first teams |

> I work best in environments where reliability is treated as an engineering discipline, not an afterthought.

---

<p align="center">
  <code>yaqoob@ahmed:~$ logout</code><br>
  <sub><code>exit 0</code> · no frameworks, no trackers · © 2026 Yaqoob Ahmed</sub>
</p>
