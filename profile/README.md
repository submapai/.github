## Open Positions

We're building the infrastructure layer for autonomous AI sandboxes. Every user gets a fully provisioned environment — workers, containers, storage, DNS, access control — spun up in seconds through a real-time orchestration pipeline. If you want to work on hard problems at the intersection of developer tooling and infrastructure automation, read on.

---

<details>
<summary><strong>Frontend Engineer</strong> · React / Next.js / Design Systems</summary>

### The Role

You'll own the entire frontend surface of Submap — from the marketing site to the real-time provisioning dashboard that orchestrates cloud infrastructure through a browser. This isn't a CRUD app. You're building reactive interfaces on top of multi-step infrastructure pipelines where every state transition matters.

### What You'll Work On

**Real-Time Provisioning UI**
Our 9-step sandbox provisioning pipeline (R2 buckets → worker deploys → containers → DNS → access policies) streams status updates to the frontend in real time. You'll build and evolve the progress tracking UI, handle edge cases like partial failures and retries, and make complex infrastructure feel simple.

**Design System & Component Architecture**
We use **shadcn/ui** with **Radix UI** primitives on **TailwindCSS v4**. You'll shape our component library, build custom interactive elements, and maintain consistency across the product. We care about micro-interactions — animated number transitions with `@number-flow/react`, staggered message bubbles, spotlight cards with glassmorphism, and 3D CSS transforms.

**Next.js 16 on Cloudflare Workers**
Our frontend runs on **Next.js 16** with **React 19** deployed to Cloudflare via `@opennextjs/cloudflare`. Server components, edge rendering, and type-safe data fetching with **Drizzle ORM** against **Cloudflare D1**. You'll work at the bleeding edge of the React/Next.js ecosystem.

**Authentication & Protected Routes**
Passwordless auth via **Privy** with server-side JWT validation. Cloudflare Access integration for per-sandbox access control. You'll handle the full auth lifecycle from login to scoped resource access.

**Landing Page & Marketing**
Advanced CSS animations, responsive layouts, dark mode with system preference detection, and 200k+ icons via Iconify. The landing page is a showcase — 3D phone mockups, progressive blur, noise overlays, reveal animations.

### You Should Be

- Deeply fluent in **React 19** patterns — server components, suspense, transitions
- Experienced with **Next.js** App Router and edge runtime constraints
- Comfortable building design systems with Tailwind + Radix primitives
- Obsessive about interaction design, animation timing, and polish
- Familiar with **TypeScript** strict mode and type-safe patterns (Zod, Drizzle)
- Someone who has opinions about `cubic-bezier` curves

### Stack

`React 19` · `Next.js 16` · `TypeScript` · `TailwindCSS v4` · `shadcn/ui` · `Radix UI` · `Drizzle ORM` · `Cloudflare D1` · `Privy` · `Turborepo` · `Bun`

### Apply

Open an issue in this repo or reach out directly. Show us something you've built.

</details>

---

<details>
<summary><strong>DevOps / Systems Engineer</strong> · Cloudflare Workers / Containers / Infrastructure</summary>

### The Role

You'll own the infrastructure that provisions and manages per-user AI sandbox environments on Cloudflare. When a user signs up, we programmatically create R2 buckets, deploy workers with Durable Objects, spin up containers from GHCR, configure DNS subdomains, set up Access policies, and inject secrets — all through API orchestration. You'll make this pipeline faster, more resilient, and support new capabilities.

### What You'll Work On

**Multi-Step Provisioning Pipeline**
The core of Submap is a 9-step idempotent provisioning system that deploys a complete sandbox environment per user. Steps include R2 bucket creation, scoped S3 token generation, worker deployment with migration handling, container configuration, secret injection, DNS mapping, and Cloudflare Access setup. You'll extend this pipeline, improve error recovery, and add new infrastructure primitives.

**Cloudflare Workers & Durable Objects**
Our workers use **Durable Objects** for stateful container management, **service bindings** for self-reference caching, **browser bindings** for headless automation, and **cron triggers** for background tasks. Worker deployments use the 3-phase Workers Assets upload protocol — session creation, bucket uploads with blake3-wasm content hashing, then JWT-based completion. You'll work directly with these APIs.

**Container Orchestration**
We deploy Docker images from GitHub Container Registry to **Cloudflare Containers** with Durable Object namespace bindings. You'll handle rolling deployments, health checks with timeout/retry logic, and container lifecycle management including sleep policies.

**In-Browser Tar.gz Extraction**
Release bundles are fetched from GitHub Releases and extracted in the browser using a zero-dependency tar parser built on the `DecompressionStream` API. Worker modules and client assets are pulled from these bundles, base64-encoded, and uploaded via the Workers API. You'll maintain and optimize this pipeline.

**DNS & Access Control Automation**
Every sandbox gets a subdomain (`username.submap.ai`) with programmatic DNS record creation and worker route mapping. Cloudflare Access applications are created per-user with email-based policies and webhook bypass rules for public API endpoints. You'll manage the full lifecycle of these resources.

**Secrets & Credential Management**
Per-worker secret injection for AI Gateway credentials, R2 S3 tokens, plugin API keys, and container controls. Scoped API tokens with permission group discovery. You'll ensure secrets are rotated, scoped correctly, and never leak.

### You Should Be

- Experienced with **Cloudflare Workers**, Durable Objects, R2, and the Cloudflare API
- Comfortable orchestrating infrastructure programmatically (no ClickOps)
- Familiar with **Docker** and container lifecycle management
- Strong with **TypeScript** — our entire infrastructure layer is typed
- Good at designing idempotent, resumable pipelines with graceful error handling
- Someone who has debugged a 409 conflict at 2am and wrote the guard clause to prevent it

### Stack

`Cloudflare Workers` · `Durable Objects` · `R2` · `D1` · `Containers` · `Access` · `DNS API` · `TypeScript` · `Wrangler` · `GitHub Actions` · `GitHub Releases` · `blake3-wasm` · `Bun` · `Turborepo`

### Apply

Open an issue in this repo or reach out directly. Show us something you've deployed.

</details>
