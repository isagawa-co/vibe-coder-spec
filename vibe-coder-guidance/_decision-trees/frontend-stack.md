# Decision Tree: Frontend Stack

Evaluate the app profile and recommend a frontend framework.

## Entry Question

What platform does the app target?

---

## Branch: Web Only

### Sub-question: What kind of web app?

**Static / Content site** (blog, docs, marketing)
→ Recommend: **Next.js (Static Export)**
- Why: Pre-renders pages, fast loading, SEO-friendly
- Alternative: Astro (if minimal JavaScript needed)

**Dynamic web app** (dashboards, CRUD, SaaS)
→ Sub-question: Does it need SEO?

  **Yes, needs SEO** (public-facing, content pages)
  → Recommend: **Next.js (SSR)**
  - Why: Server-side rendering for SEO, React ecosystem
  - Alternative: Nuxt (if user prefers Vue)

  **No SEO needed** (internal tool, dashboard, admin)
  → Recommend: **React + Vite**
  - Why: Fast dev experience, large ecosystem, simple deployment
  - Alternative: Vue + Vite (simpler learning curve)

**Real-time app** (chat, collaboration, live updates)
→ Recommend: **React + Vite**
- Why: Works well with WebSocket/real-time libraries
- Note: Backend choice matters more for real-time than frontend
- Alternative: Next.js (if also needs SSR)

---

## Branch: Mobile Only

→ Recommend: **React Native + Expo**
- Why: Write once, deploy iOS + Android, large community
- Alternative: Flutter (if performance-critical native feel needed)

---

## Branch: Web + Mobile

→ Recommend: **Next.js (web) + React Native (mobile)**
- Why: Shared React knowledge, shared business logic possible
- Note: These are two separate codebases but same mental model
- Alternative: Expo Router (experimental unified approach)

---

## Branch: Desktop

→ Recommend: **Electron + React**
- Why: Web tech for desktop, cross-platform
- Alternative: Tauri (smaller bundle, Rust-based)

---

## Explain to User

### What is a frontend framework?
"A frontend framework is the tool that builds what users see and interact with — the buttons, pages, forms, and layout. Choosing one is like choosing which construction materials to use for a house."

### React vs Vue
"React and Vue both do the same job — they build user interfaces. React is more popular (more tutorials, more packages), Vue is slightly easier to learn. Both are great choices."

### What is SSR?
"SSR (server-side rendering) means the server builds the page before sending it to the user. This makes the first page load faster and helps search engines find your content. Not every app needs this."

### What is Vite?
"Vite is a build tool — it takes your code and packages it up so browsers can run it. It's very fast during development, which means you see your changes almost instantly."
