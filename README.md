# Gumroad-GitHub Webhook

Automatically grants GitHub repo access when someone buys your product on Gumroad.

## How it works

1. Buyer purchases your product on Gumroad and enters their GitHub username in a custom checkout field
2. Gumroad sends a webhook to your deployed service
3. The service verifies the request, looks up which repo maps to that product, and invites the buyer as a collaborator
4. GitHub sends the buyer an email to accept the invitation

## Setup

### 1. Install dependencies

```bash
npm install
```

### 2. Configure environment variables

Copy `.env.example` to `.env.local` and fill in your values:

```bash
cp .env.example .env.local
```

| Variable | Purpose |
|----------|---------|
| `GITHUB_TOKEN` | GitHub personal access token with `repo` scope |
| `GITHUB_OWNER` | Your GitHub username or org |
| `GUMROAD_WEBHOOK_SECRET` | A secret string you create (also added to Gumroad) |
| `PRODUCT_REPO_MAP` | JSON mapping product IDs to repo names |

### 3. Configure Gumroad

- Add a custom field called "GitHub Username" to your product checkout
- Set the webhook URL to `https://your-domain.vercel.app/api/webhook/gumroad`
- Include your `GUMROAD_WEBHOOK_SECRET` in the webhook payload

### 4. Deploy to Vercel

```bash
npx vercel
```

## Development

```bash
npm run dev      # Start dev server
npm test         # Run tests
npm run build    # Production build
```

## Project structure

```
src/
├── app/api/webhook/gumroad/route.ts   # Webhook endpoint
├── lib/
│   ├── config.ts                      # Env var loading & product-repo mapping
│   ├── gumroad.ts                     # Webhook verification & payload parsing
│   └── github.ts                      # GitHub API (invite collaborator)
└── types/index.ts                     # TypeScript type definitions
tests/                                 # Tests (mirrors src/ structure)
```
