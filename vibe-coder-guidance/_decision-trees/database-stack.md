# Decision Tree: Database Stack

Evaluate the app profile and recommend a database.

## Entry Question

What kind of data does the app store?

---

## Branch: Structured Data (tables, relationships)

**Users, orders, products, etc. — data with clear relationships**

### Sub-question: What scale?

**Personal project / small team (< 1000 users)**
→ Recommend: **SQLite**
- Why: Zero setup, file-based, works everywhere, great for starting
- Best for: Prototypes, personal tools, small apps
- Tradeoff: Single-writer, not great for concurrent access
- Note: Can migrate to Postgres later if needed

**Startup / medium scale (1K - 100K users)**
→ Recommend: **PostgreSQL (via Supabase)**
- Why: Industry standard, scales well, Supabase adds auth + API for free
- Best for: Most web apps, SaaS, data-heavy applications
- Tradeoff: Slightly more setup than SQLite
- Alternative: PostgreSQL self-hosted (if avoiding vendor lock-in)

**Large scale (100K+ users)**
→ Recommend: **PostgreSQL (managed — Neon, RDS, or Supabase)**
- Why: Battle-tested, scales to millions, managed = less ops work
- Alternative: PlanetScale (MySQL-based, good for global distribution)

---

## Branch: Unstructured / Flexible Data

**Documents, user-generated content, varying schemas**
→ Recommend: **MongoDB**
- Why: Flexible schema, good for evolving data models, JSON-native
- Best for: Content platforms, social apps, apps where data shape changes often
- Tradeoff: Weaker relationships, eventual consistency by default
- Alternative: PostgreSQL JSONB (structured DB with flexible JSON columns)

---

## Branch: Key-Value / Cache

**Session data, real-time state, leaderboards**
→ Recommend: **Redis**
- Why: In-memory, blazing fast, great for caching and real-time
- Best for: Caching layer, session storage, pub/sub
- Note: Usually paired WITH another database, not instead of

---

## Branch: Already Using Supabase

**If backend decision was Supabase**
→ Recommend: **PostgreSQL (Supabase built-in)**
- Why: Already included, no extra setup, SQL + real-time out of the box
- No additional database needed

---

## Branch: No Persistent Data

**App doesn't need to store anything long-term**
→ No database needed
- Use local storage for client-side state
- Use session storage for temporary data

---

## Explain to User

### What is a database?
"A database is where your app stores information permanently. When a user creates an account, posts something, or saves settings — that goes in the database. Without it, everything disappears when they close the app."

### SQL vs NoSQL
"SQL databases (like PostgreSQL) organize data in tables with strict rules — like a spreadsheet. NoSQL databases (like MongoDB) are more flexible — like a folder of documents. SQL is better when your data has clear structure; NoSQL is better when your data shape might change."

### What is Supabase?
"Supabase is a service that gives you a PostgreSQL database plus extras (auth, file storage, real-time) with a nice dashboard. It's like getting a pre-furnished apartment instead of an empty house."

### SQLite vs PostgreSQL
"SQLite is a single file on your computer — zero setup, great for starting. PostgreSQL is a full database server — more powerful, handles many users at once. Start with SQLite if you're unsure; you can always upgrade later."

### What is managed vs self-hosted?
"Managed means someone else runs the database server for you (backups, updates, scaling). Self-hosted means you run it yourself. Managed costs money but saves time; self-hosted is free but you handle everything."
