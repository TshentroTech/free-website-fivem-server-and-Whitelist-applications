# Free FiveM Website + Whitelist Applications

# My Tebex Store

## If you would like to support me, you can take a look at my scripts: https://tshentro.tebex.io

## YouTube

- https://www.youtube.com/watch?v=PC0Mrz61Mys

Open-source FiveM roleplay community website with Discord authentication, whitelist/staff/job applications, admin review tools, and customizable branding.

## Features

- Discord OAuth login with `NextAuth`
- Public whitelist application form
- Staff application form
- Job application system
- Admin dashboard for reviewing applications
- Rules pages and editable content sections
- Store/categories pages
- Discord webhook and DM workflow support
- Optional role assignment and device-check flow

## Tech Stack

- `Next.js 16`
- `React 19`
- `TypeScript`
- `Prisma`
- `PostgreSQL` (Neon/Supabase/Vercel Postgres compatible)
- `Tailwind CSS`

## Quick Start

1. Install dependencies:

```bash
npm install
```

2. Create your environment file:

```bash
copy .env.example .env
```

3. Fill required values in `.env` (database + Discord + NextAuth).

4. Run development server:

```bash
npm run dev
```

5. Open `http://localhost:3000`.

## Required Environment Variables

Create a file named ` .env `. And copy this 👇
```env
# Database — MUST be PostgreSQL (postgresql:// or postgres://). Do NOT use file:./dev.db.
# Get a connection string from: Vercel (Storage → Postgres), Neon, Supabase, or any Postgres host.
# Then set this in .env and in Vercel → Settings → Environment Variables.
DATABASE_URL="postgresql://user:password@host:5432/dbname?sslmode=require"

# Discord OAuth2 - Create app at https://discord.com/developers/applications
DISCORD_CLIENT_ID=your_discord_client_id
DISCORD_CLIENT_SECRET=your_discord_client_secret
NEXTAUTH_SECRET=generate_with_openssl_rand_base64_32
NEXTAUTH_URL=http://localhost:3000

# Discord Webhook for notifications (optional - create in Discord channel settings)
DISCORD_WEBHOOK_URL=https://discord.com/api/webhooks/...

# Discord Bot Token for sending DMs and assigning roles (optional - use same app's Bot, enable "Message Content Intent")
# Bot must share a server with the user to send DMs. Create bot at discord.com/developers/applications → Your App → Bot
DISCORD_BOT_TOKEN=your_bot_token_here

# Server (guild) ID and roles – bot adds these when applications are approved
# Get guild ID: Right-click your server icon → Copy Server ID (enable Developer Mode in Discord settings)
# Get role IDs: Server Settings → Roles → right-click role → Copy Role ID. Roles must be below the bot's role.
DISCORD_GUILD_ID=your_discord_server_id
DISCORD_WHITELIST_ROLE_ID=your_whitelist_role_id
# When a whitelist application is moved to device check, the bot grants this role
DISCORD_DEVICE_CHECK_ROLE_ID=your_device_check_role_id
# When a staff application is approved, the bot grants this role to the user
DISCORD_STAFF_ROLE_ID=your_staff_role_id

# Author name shown on DM embeds (optional, default: "Whitelist System")
# DISCORD_DM_AUTHOR_NAME=Your Server Name

# Admin Discord IDs - divide privileges. You can add multiple admins per rank (comma-separated).
# ADMIN_DISCORD_IDS = full admin (whitelist + jobs + staff applications, sees all PENDING lists)
# TEAM_ADMIN_DISCORD_IDS = whitelist + staff applications only (no job applications)
# JOBS_ADMIN_DISCORD_IDS = job and city position applications only
# To see job requests in Admin PENDING list, use ADMIN_DISCORD_IDS or JOBS_ADMIN_DISCORD_IDS.
ADMIN_DISCORD_IDS=discord id,discord id
TEAM_ADMIN_DISCORD_IDS=111,222
JOBS_ADMIN_DISCORD_IDS=333,444

```
## Scripts

- `npm run dev` - run local dev server
- `npm run build` - build production app
- `npm run start` - run production server
- `npm run db:migrate:deploy` - apply Prisma migrations
- `npm run db:seed` - run database seed
- `npm run deploy` - deploy with Vercel CLI

## Project Setup Notes

- Full setup guide: `INSTALLATION.md`
- Deployment guide: `DEPLOY.md`
- Site text/branding config: `src/config/config-site.ts`

## CFX Release Notes

## Deploy to Vercel

1. Push this project to GitHub.
2. Import the repo in Vercel.
3. Add all required environment variables in Vercel.
4. Deploy.

If your production database already has tables, you may need to baseline migrations before running `prisma migrate deploy`.

- Type: Free release
- Source code: Open source
- Support: No
- Download: [GitHub repository](https://github.com/TshentroTech/free-website-fivem-server-and-Whitelist-applications)

## Support My Development Time

- https://ko-fi.com/tshentrotech
