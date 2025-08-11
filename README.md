# First-one
Tennis tracker
Tennis Picks — Next.js + Postgres + Auth

A clean, green-and-white web app to post, track, and share tennis picks. Decimal odds only, with Markets, Surface, and Tournament Level. Protected write access, public read profile pages.

1) Create Your Repo

Make a new empty repository on GitHub.

Copy all code from the “Tennis Picks — Next” project into it (including this README as README.md).

2) Create a Postgres Database

Use Neon, Supabase, or local Postgres.

Copy the connection string.

3) Set Up GitHub OAuth App

Go to GitHub → Settings → Developer settings → OAuth Apps → New OAuth App.

Homepage URL: http://localhost:3000

Authorization callback URL: http://localhost:3000/api/auth/callback/github

Save, then copy Client ID and Client Secret.

4) Add Environment Variables Locally

Create .env.local in the project root:

DATABASE_URL=postgres://USER:PASSWORD@HOST:PORT/DB
NEXTAUTH_SECRET=your_generated_secret
GITHUB_ID=your_github_oauth_client_id
GITHUB_SECRET=your_github_oauth_client_secret

Generate a secret:

openssl rand -base64 32

5) Install & Run Locally

npm install
npm run prisma:push
npm run dev

Visit http://localhost:3000 and:

Sign in with GitHub.

Set your handle in the dashboard.

Set your starting bankroll.

Add a few picks and watch the charts update.

6) Deploy to Vercel

Push your code to GitHub.

Import the repo in Vercel.

Add environment variables in Vercel (same as .env.local).

Update your GitHub OAuth app with the production callback:

https://your-vercel-domain/api/auth/callback/github

Deploy.

7) Share

Dashboard (/dashboard) — private to your GitHub account.

Public profile (/u/[handle]) — shareable link to your picks & mini stats.

Public API (read-only):

/api/picks?handle=your-handle

/api/stats?handle=your-handle

Next Steps

CSV import/export for bulk pick management.

Rolling 30/90-day ROI analytics.

Public “About & Methodology” section on profile.
