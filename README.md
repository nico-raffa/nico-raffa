<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a1b27,50:7aa2f7,100:bb9af7&height=200&section=header&text=Nicolás%20Raffagnini&fontSize=48&fontColor=ffffff&fontAlignY=38&desc=Software%20Engineer%20-%20Agentic%20AI&descAlignY=58&descSize=18&animation=fadeIn" width="100%" alt="header" />

<a href="https://git.io/typing-svg">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=20&duration=3000&pause=800&color=7AA2F7&center=true&vCenter=true&width=600&lines=Agentes+de+IA+%C2%B7+LLMs+%C2%B7+Tool-calling;Producto+end-to-end%3A+del+dato+al+deploy;Node.js+%C2%B7+TypeScript+%C2%B7+React+%C2%B7+PostgreSQL" alt="Typing SVG" />
</a>

<br/>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/nicolas-raffagnini)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/nico-raffa)
[![GitHub Work](https://img.shields.io/badge/Work-Nico--RaffaWW-1a1b27?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Nico-RaffaWW)
[![Email](https://img.shields.io/badge/Email-Contacto-bb9af7?style=for-the-badge&logo=gmail&logoColor=white)](mailto:nicolas.raffagnini95@gmail.com)
![Profile views](https://komarev.com/ghpvc/?username=nico-raffa&style=for-the-badge&color=7aa2f7&label=VISITAS)

</div>

---

## 👨‍💻 Sobre mí

- 🏭 En **NBG** diseño y opero **WWSystem**, un ERP de manufactura end-to-end que hoy corre en producción, desarrollado desde mi cuenta de trabajo [@Nico-RaffaWW](https://github.com/Nico-RaffaWW).
- 🧭 Perfil **full-cycle** con base fuerte en **backend**: arquitectura de datos, diseño de APIs, despliegue en infraestructura propia y observabilidad de punta a punta.
- 🤖 Diseño **agentes de IA en producción** — tool-calling, grounding determinístico, guardrails y control de costos — y trabajo con flujos de desarrollo asistidos por IA (**Claude Code**, **OpenCode**, **Codex**).
- 💬 **Hablemos de:** agentes de IA, arquitectura backend, APIs REST, seguridad, tiempo real (WebSockets / SSE), bases de datos, Docker y observabilidad.

---

## ⭐ Proyectos principales

### 🤖 Seller Agent — Vendedor con IA por WhatsApp &nbsp;<img src="https://img.shields.io/badge/%F0%9F%94%92_Private_Repo-En_producci%C3%B3n-7aa2f7?style=flat-square&labelColor=1a1b27" alt="Private Repo · En producción" />

> **Vendedor conversacional con IA** que atiende por WhatsApp 24/7 con **precios y stock reales**, arma el carrito en vivo, deriva a una persona cuando hace falta y centraliza la operación en un **panel multilínea en tiempo real**.

<p>
  <img src="https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=node.js&logoColor=white" />
  <img src="https://img.shields.io/badge/Express_5-000000?style=flat-square&logo=express&logoColor=white" />
  <img src="https://img.shields.io/badge/React_19-20232A?style=flat-square&logo=react&logoColor=61DAFB" />
  <img src="https://img.shields.io/badge/Tailwind_4-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white" />
  <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white" />
  <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white" />
  <img src="https://img.shields.io/badge/BullMQ-B22222?style=flat-square" />
  <img src="https://img.shields.io/badge/Google_Gemini-4285F4?style=flat-square&logo=google&logoColor=white" />
  <img src="https://img.shields.io/badge/WhatsApp-25D366?style=flat-square&logo=whatsapp&logoColor=white" />
  <img src="https://img.shields.io/badge/Tienda_Nube-00AEEF?style=flat-square" />
</p>

<table>
<tr>
<td width="50%" valign="top">

**🧠 Qué hace**
- Agente con **tool-calling sobre Gemini**: búsqueda semántica de catálogo, carrito y stock
- Ofertas y cupones con un **motor de precios determinístico**
- **Guard de derivación** a humano, **validador de grounding** de productos/precios e interceptor de estilo
- Seguimientos automáticos, carritos abandonados y **memoria del cliente**
- Panel operativo para supervisar chats, tomar el control y aprobar pedidos

> 💡 El modelo conversa y decide; **precios, stock y ofertas salen siempre de fuentes determinísticas**.

</td>
<td width="50%" valign="top">

**📈 En números**
- 📬 **4 colas BullMQ** para desacoplar la latencia de la IA
- 🗄️ **20 migraciones** con aislamiento por línea de WhatsApp
- 📝 **~31.500 líneas** de JS/JSX entre backend y frontend
- ⚡ **Caché read-through en Redis** con hit ratio expuesto en métricas
- 📡 Tiempo real por **SSE**, sin polling, y trazabilidad de costo de tokens

</td>
</tr>
</table>

```text
 ┌────────────────────┐     ┌──────────────────────┐       ┌─────────────────────────────┐
 │  WhatsApp Webhook  │     │     Express API      │       │         Colas BullMQ        │
 │ mensajes entrantes │────▶│ validación · ingesta │──────▶│     desacople · debounce    │
 └────────────────────┘     └──────────────────────┘       └──────────────┬──────────────┘
                                                                          │
 ┌───────────────────────────┐                             ┌──────────────▼──────────────┐
 │    Motor Determinístico   │                             │        Agente Gemini        │
 │ precios · stock · ofertas │◀─────── tool calls ────────▶│         tool-calling        │
 │    MySQL + caché Redis    │                             └──────────────┬──────────────┘
 └───────────────────────────┘                                            │
                                                           ┌──────────────▼──────────────┐
                                                           │    Validador de Grounding   │
                                                           │ productos · precios · stock │
                                                           └──────────────┬──────────────┘
                                                                          │
               ┌──────────────────────────────────────────────────────────┤
               ▼                                                          ▼
   ┌───────────────────────┐                               ┌─────────────────────────────┐
   │   Respuesta WhatsApp  │                               │         Eventos SSE         │
   │       al cliente      │                               │   Panel Operativo en vivo   │
   └───────────────────────┘                               └─────────────────────────────┘
```

---

### 🏭 WWSystem — ERP a medida en NBG

> **ERP a medida para gestión de manufactura**, diseñado y desarrollado desde 0 en NBG. Hoy está en producción.

<table>
<tr>
<td width="50%" valign="top">

**📦 Qué resuelve**
- Materias primas, formulación de productos y órdenes de producción
- Pedidos, ventas, listas de precios, cobros y envíos
- Proveedores, órdenes de compra y egresos
- Finanzas, balances, libro IVA, notas de crédito y débito
- Tablero del dueño, reportes, auditoría y RBAC por roles

</td>
<td width="50%" valign="top">

**📈 En números**
- 🧩 **+45 módulos** de negocio en el backend
- 🗄️ **+340 migraciones** de base de datos
- 🔀 **+2.900 commits** entre backend y frontend
- 🐳 Entornos de **producción y testing** separados
- 🖥️ Desplegado en **infraestructura propia** con Docker Compose y Nginx
- 🛡️ **Alta disponibilidad**: reinicio automático de servicios y backups programados
- 📊 Monitoreo con **métricas y logs centralizados**

</td>
</tr>
</table>

```text
 ┌──────────────┐     ┌──────────────────┐     ┌────────────────────────┐     ┌──────────┐
 │  React SPA   │────▶│  Nginx Gateway   │────▶│  Node.js · Express API │────▶│ MariaDB  │
 │ Vite · MUI   │ WS  │  HTTPS · proxy   │     │  Sequelize · Socket.io │     │  MySQL   │
 └──────────────┘     └──────────────────┘     └───────────┬────────────┘     └──────────┘
                                                           │ métricas / logs
                                       ┌───────────────────▼────────────────────┐
                                       │  Prometheus · Loki · Grafana           │
                                       └────────────────────────────────────────┘
   CI/CD: GitHub Actions ─▶ imágenes Docker en GHCR ─▶ deploy con Docker Compose
```

**Arquitectura y prácticas:** backend modular por *features* · auth con JWT y cookies, protección CSRF, Helmet y rate limiting · RBAC · notificaciones en tiempo real con Socket.io · tareas programadas con cron · backups automáticos con systemd · tests con Mocha, Chai, Sinon y Supertest · E2E con Cypress · Git hooks con Husky.

---

## 🛠️ Core Stack

<table>
  <tr>
    <td align="center" width="160"><b>Backend & Core</b></td>
    <td>
      <img src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white" />
      <img src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white" />
      <img src="https://img.shields.io/badge/Python-3670A0?style=for-the-badge&logo=python&logoColor=FFDD54" />
      <img src="https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white" />
      <img src="https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white" />
      <img src="https://img.shields.io/badge/MySQL_%2F_MariaDB-4479A1?style=for-the-badge&logo=mysql&logoColor=white" />
      <img src="https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white" />
    </td>
  </tr>
  <tr>
    <td align="center" width="160"><b>IA & Agentes</b></td>
    <td>
      <img src="https://img.shields.io/badge/Google_Gemini-4285F4?style=for-the-badge&logo=googlegemini&logoColor=white" />
      <img src="https://img.shields.io/badge/Tool_Calling-1a1b27?style=for-the-badge" />
      <img src="https://img.shields.io/badge/BullMQ-B22222?style=for-the-badge" />
      <img src="https://img.shields.io/badge/Guardrails_%26_Grounding-bb9af7?style=for-the-badge" />
    </td>
  </tr>
  <tr>
    <td align="center" width="160"><b>Frontend</b></td>
    <td>
      <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" />
      <img src="https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white" />
      <img src="https://img.shields.io/badge/Astro-BC52EE?style=for-the-badge&logo=astro&logoColor=white" />
      <img src="https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white" />
    </td>
  </tr>
  <tr>
    <td align="center" width="160"><b>Infra & Observabilidad</b></td>
    <td>
      <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" />
      <img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black" />
      <img src="https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white" />
      <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white" />
      <img src="https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white" />
      <img src="https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white" />
      <img src="https://img.shields.io/badge/Loki-F46800?style=for-the-badge&logo=grafana&logoColor=white" />
    </td>
  </tr>
</table>

---

## 📊 GitHub Stats

<div align="center">

<img height="170" src="https://github-profile-summary-cards.vercel.app/api/cards/stats?username=nico-raffa&theme=tokyonight" />
<img height="170" src="https://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=nico-raffa&theme=tokyonight" />

<img src="https://streak-stats.demolab.com?user=nico-raffa&theme=tokyonight&hide_border=true" width="60%" />

</div>

<table>
<tr>
<td width="50%" align="center" valign="top">

**🏢 Actividad · [@Nico-RaffaWW](https://github.com/Nico-RaffaWW)**

<img src="https://github-readme-activity-graph.vercel.app/graph?username=Nico-RaffaWW&theme=tokyo-night&hide_border=true&area=true&height=260" width="100%" alt="Actividad cuenta de trabajo" />

</td>
<td width="50%" align="center" valign="top">

**👤 Actividad · [@nico-raffa](https://github.com/nico-raffa)**

<img src="https://github-readme-activity-graph.vercel.app/graph?username=nico-raffa&theme=tokyo-night&hide_border=true&area=true&height=260" width="100%" alt="Actividad cuenta personal" />

</td>
</tr>
</table>

---

<div align="center">

**¿Tenés un proyecto o una idea? ¡Conectemos!** 🚀

Disponible para roles de **Tech Lead / Senior Full-Stack & AI Engineer**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Conectemos-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/nicolas-raffagnini)
[![Email](https://img.shields.io/badge/Email-Escribime-bb9af7?style=for-the-badge&logo=gmail&logoColor=white)](mailto:TU_EMAIL@ejemplo.com)

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:bb9af7,50:7aa2f7,100:1a1b27&height=100&section=footer" width="100%" alt="footer" />

</div>
