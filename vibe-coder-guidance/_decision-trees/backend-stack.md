# Decision Tree: Backend Stack

Evaluate the app profile and recommend a backend approach.

## Entry Question

Does the app need a custom backend API?

---

## Branch: No Custom Backend Needed

**Simple CRUD, auth, and storage only**
→ Recommend: **Supabase (BaaS)**
- Why: Postgres database + auth + file storage + real-time, zero backend code
- Best for: MVPs, solo developers, apps that mostly read/write data
- Tradeoff: Less control, vendor lock-in
- Alternative: Firebase (if already in Google ecosystem)

**Static site with no data**
→ No backend needed
- Deploy frontend only (Vercel, Netlify)

---

## Branch: Needs Custom Backend

### Sub-question: What language does the user prefer?

**No preference / JavaScript**
→ Sub-question: How complex is the API?

  **Simple REST API** (CRUD, auth, basic business logic)
  → Recommend: **Express.js (Node.js)**
  - Why: Same language as frontend, massive ecosystem, simple to start
  - Alternative: Fastify (if performance matters)

  **Complex API** (many endpoints, complex business logic, background jobs)
  → Recommend: **Next.js API Routes**
  - Why: Unified frontend + backend in one codebase, serverless-friendly
  - Note: Only works well if frontend is also Next.js
  - Alternative: Express.js (if decoupled backend needed)

**Python preference**
→ Recommend: **FastAPI**
- Why: Modern, fast, automatic API docs, type-safe
- Best for: Data-heavy apps, ML integration, clean API design
- Alternative: Django (if needs admin panel, ORM, batteries-included)

**Go preference**
→ Recommend: **Go + Chi/Gin**
- Why: Fast, compiled, great for microservices
- Best for: High-performance APIs, concurrent workloads

---

## Branch: Real-time Needed

**WebSocket / live updates required**
→ Recommend: **Express.js + Socket.io**
- Why: Mature WebSocket library, easy to integrate
- Note: Supabase also supports real-time subscriptions (simpler option)
- Alternative: FastAPI + WebSockets (if Python backend)

---

## Branch: Serverless Preference

**Wants minimal infrastructure**
→ Recommend: **Next.js API Routes (Vercel)**
- Why: Zero server management, auto-scaling, integrated with frontend
- Tradeoff: Cold starts, execution time limits
- Alternative: AWS Lambda + API Gateway (more control)

---

## Explain to User

### What is a backend?
"The backend is the behind-the-scenes part of your app. It handles things like saving data, checking passwords, and talking to other services. Users never see it directly."

### REST API vs BaaS
"A REST API is custom code you write to handle data. A BaaS (Backend as a Service) like Supabase gives you a pre-built backend — database, auth, storage — without writing server code. BaaS is faster to start but less flexible."

### What is serverless?
"Serverless means your code runs on demand — you don't manage a server. It scales automatically and you only pay for what you use. The tradeoff is less control and occasional slow starts."

### Express vs FastAPI
"Express (JavaScript) and FastAPI (Python) both build APIs. Express has a larger ecosystem; FastAPI is faster and generates documentation automatically. Pick based on which language you prefer."
