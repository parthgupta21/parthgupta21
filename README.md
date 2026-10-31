<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./assets/banner-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="./assets/banner-light.svg">
  <img alt="Parth Gupta, Software Engineer, backend systems" src="./assets/banner-light.svg" width="100%">
</picture>

<br/>

[![Hashnode](https://img.shields.io/badge/Hashnode-@ParthGupta-2962FF?style=flat-square&logo=hashnode&logoColor=white)](https://hashnode.com/@ParthGupta) [![X](https://img.shields.io/badge/X-@honoured__0ne__-000000?style=flat-square&logo=x&logoColor=white)](https://x.com/honoured_0ne_)

</div>

## About

I'm a software engineer who mostly works on the backend: HTTP APIs, gateways, background workers, and the queues between them. I like the problems that show up once a system is real, such as a downstream service that is slow, a request that arrives twice, or a job that dies halfway through. Most of what I build here is about handling those cases properly.

- **Reliability first.** Persist before processing, retry with backoff, make replays idempotent, and sweep up the jobs that slip through.
- **Security as part of the design.** JWT auth, role-based access, rate limits, audit logs, SSRF guards on outbound calls.
- **Systems you can operate.** Structured logs, Prometheus metrics, health checks, Docker images, and CI that tests against real MySQL and Redis.

I also practise data structures and algorithms in C++ ([DS-and-algos](https://github.com/parthgupta21/DS-and-algos), [Coding-Contests](https://github.com/parthgupta21/Coding-Contests)).

## Featured: RELAY

<table>
<tr>
<td>

**A hosted, multi-tenant webhook gateway.** Senders post to a stable RELAY URL and get a fast response. RELAY stores the request first, then a separate worker delivers it to your destinations as signed HTTP requests, with retries and replay. Your server can be down or redeploying without losing the event.

- **Capture:** the raw body is stored byte for byte, so sender signatures still verify downstream. Optional per-endpoint idempotency header, body size limits, rate limits and quotas.
- **Delivery:** BullMQ worker, HMAC-SHA256 signatures, exponential backoff with jitter, `Retry-After` support, concurrency caps, and a sweeper for stuck deliveries.
- **Replay:** replay any event or delivery. `Idempotency-Key` is required, so a retried replay request returns the stored response.
- **Operations:** live inspector over Socket.IO, delivery analytics (success rate, p50/p95 latency), Prometheus metrics, an operator admin API, and a production Docker Compose stack with a deploy workflow.

<sub>Node.js · Koa · MySQL · Sequelize · Redis · BullMQ · Socket.IO · React 19 · Vite · Tailwind CSS · shadcn/ui · Docker · Nginx · GitHub Actions</sub>

[**relay-backend →**](https://github.com/parthgupta21/relay-backend) &nbsp;&nbsp; [**relay-frontend →**](https://github.com/parthgupta21/relay-frontend)

</td>
</tr>
</table>

## Selected projects

<table>
<tr>
<td width="50%" valign="top">

### [auth-rbac-gateway](https://github.com/parthgupta21/auth-rbac-gateway)

A Koa API gateway that handles identity so upstream services don't have to: JWT access and refresh tokens, RBAC permissions, Redis rate limiting, audit logging, and proxying with identity headers. Ships with Prometheus metrics, OpenTelemetry instrumentation and an OpenAPI spec.

<sub>Koa · MySQL · Sequelize · Redis · OpenTelemetry · Docker</sub>

</td>
<td width="50%" valign="top">

### [mini-ecommerce-backend](https://github.com/parthgupta21/mini-ecommerce-backend)

An e-commerce backend split into user, product and order services behind an API gateway. Each service runs in its own container and finds the others through Docker's internal DNS. Timeouts on service-to-service calls return a clean `503` instead of letting one slow service hang the rest.

<sub>Node.js · Express · Axios · Docker Compose</sub>

</td>
</tr>
<tr>
<td width="50%" valign="top">

### [asynchronous-task-orchestrator](https://github.com/parthgupta21/asynchronous-task-orchestrator)

AtlasJS, a framework-free task orchestrator that runs in the browser. A FIFO scheduler with a concurrency limit, a task state machine that rejects illegal transitions, pause, resume and cancel, history that survives a page reload, and explicit cleanup to avoid memory leaks.

<sub>Vanilla JavaScript · Event system · localStorage</sub>

</td>
<td width="50%" valign="top">

### [content-sense-ai](https://github.com/parthgupta21/content-sense-ai)

A text analysis API that returns sentiment and topics using Google's Gemini model. Requests go through Joi validation, API-key auth and a Redis-backed rate limiter before they reach the model.

<sub>Node.js · Express · Gemini API · Redis · Docker</sub>

</td>
</tr>
</table>

<details>
<summary><b>Earlier full-stack work</b></summary>
<br/>

| Project | What it is | Stack |
| --- | --- | --- |
| [Form-Builder-App](https://github.com/parthgupta21/Form-Builder-App) | Drag-and-drop form builder | Next.js · TypeScript · Prisma · PostgreSQL |
| [horizon-banking-app](https://github.com/parthgupta21/horizon-banking-app) | Banking dashboard with linked accounts and transfers | Next.js · TypeScript · Plaid · Dwolla · Appwrite |
| [Video-Calling-Realtime-Chat-App](https://github.com/parthgupta21/Video-Calling-Realtime-Chat-App) | Chat and video calling with friend requests | React · Express · MongoDB · Stream |
| [Codeflex](https://github.com/parthgupta21/Codeflex---An-AI-trainer-app) | AI fitness program generator | Next.js · Convex · Clerk · Vapi |

</details>

## Toolbox

<table>
<tr>
<td><b>Languages</b></td>
<td>
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black" alt="JavaScript"/>
<img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript"/>
<img src="https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white" alt="C++"/>
<img src="https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=mysql&logoColor=white" alt="SQL"/>
</td>
</tr>
<tr>
<td><b>Backend</b></td>
<td>
<img src="https://img.shields.io/badge/Node.js-5FA04E?style=flat-square&logo=nodedotjs&logoColor=white" alt="Node.js"/>
<img src="https://img.shields.io/badge/Koa-33333D?style=flat-square&logo=koa&logoColor=white" alt="Koa"/>
<img src="https://img.shields.io/badge/Express-000000?style=flat-square&logo=express&logoColor=white" alt="Express"/>
<img src="https://img.shields.io/badge/BullMQ-E4405F?style=flat-square" alt="BullMQ"/>
<img src="https://img.shields.io/badge/Socket.IO-010101?style=flat-square&logo=socketdotio&logoColor=white" alt="Socket.IO"/>
<img src="https://img.shields.io/badge/Sequelize-52B0E7?style=flat-square&logo=sequelize&logoColor=white" alt="Sequelize"/>
</td>
</tr>
<tr>
<td><b>Data</b></td>
<td>
<img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white" alt="MySQL"/>
<img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white" alt="PostgreSQL"/>
<img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white" alt="Redis"/>
<img src="https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white" alt="MongoDB"/>
<img src="https://img.shields.io/badge/Prisma-2D3748?style=flat-square&logo=prisma&logoColor=white" alt="Prisma"/>
</td>
</tr>
<tr>
<td><b>Frontend</b></td>
<td>
<img src="https://img.shields.io/badge/React-087EA4?style=flat-square&logo=react&logoColor=white" alt="React"/>
<img src="https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white" alt="Next.js"/>
<img src="https://img.shields.io/badge/Vite-646CFF?style=flat-square&logo=vite&logoColor=white" alt="Vite"/>
<img src="https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white" alt="Tailwind CSS"/>
<img src="https://img.shields.io/badge/shadcn%2Fui-000000?style=flat-square&logo=shadcnui&logoColor=white" alt="shadcn/ui"/>
</td>
</tr>
<tr>
<td><b>Ops</b></td>
<td>
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Docker"/>
<img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white" alt="GitHub Actions"/>
<img src="https://img.shields.io/badge/Nginx-009639?style=flat-square&logo=nginx&logoColor=white" alt="Nginx"/>
<img src="https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white" alt="Prometheus"/>
<img src="https://img.shields.io/badge/OpenTelemetry-000000?style=flat-square&logo=opentelemetry&logoColor=white" alt="OpenTelemetry"/>
</td>
</tr>
</table>

<br/>

<div align="center">
<sub>Always up for a good engineering conversation. Find me on <a href="https://x.com/honoured_0ne_">X</a> or <a href="https://hashnode.com/@ParthGupta">Hashnode</a>.</sub>
</div>
