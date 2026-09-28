# BEST WAY EC — Education Center System

> **English & International Exams (IELTS / Multilevel / General)**
> Shofirkon, Bukhara · Since 2007 · Founder **Aziz Akhtamov**

Welcome to the official GitHub organisation of **BESTWAY Education Center** — `[@bestwayec](https://github.com/bestwayec)`.

One platform for the whole center — students, teachers, parents and admins — with transparent attendance, points, payments and exam results.

---

## 🏫 About us

- 📍 **Location:** Shofirkon, Bukhara, Uzbekistan
- 📅 **Founded:** 2007
- 👤 **Founder:** Aziz Akhtamov
- 📚 **Focus:** English, IELTS, Multilevel, General English, Mock Exams
- 🤖 **Telegram bot:** [@bestway_xabarbot](https://t.me/bestway_xabarbot)
- 📧 **Contact:** `otashdev1@gmail.com`

We build and maintain our own internal platform to run the center — no paper journals, no lost payments, everything visible.

## 💻 What we build here

### ⭐ [bestwayec/bestway](https://github.com/bestwayec/bestway) — flagship monorepo

Full education-center management system:

**Students & Parents:** take tests / mocks, track points & leaderboard, watch purchased videos, see payments & attendance.

**Teachers:** Excel-like attendance grid, ± points with reason, auto + manual test grading, own groups only.

**Admins:** 12-month payments grid, debtors + Telegram reminders, income charts, CSV exports, CMS (news / gallery / teachers / videos), in-app + Telegram broadcasts, audit log.

```
Browser → Next.js (3005) → NestJS API (3001 /v1) → PostgreSQL
          httpOnly bw_at/bw_rt | proxy + refresh | next-intl (uz/en)
                               | helmet + throttler + ValidationPipe
                               | Swagger /docs + /admin + Telegram bot
```

**Quick start:**

```bash
git clone https://github.com/bestwayec/bestway.git
cd bestway
cp backend/.env.example backend/.env
docker compose up -d --build
# frontend → http://localhost:3005
# backend  → http://localhost:3001/v1/health
# swagger  → http://localhost:3001/docs
```

See full docs in the [repo README](https://github.com/bestwayec/bestway#readme).

---

## 🧰 Tech stack

| Layer | Choice |
|-------|--------|
| Backend | **NestJS 10** · Prisma 5 · PostgreSQL 17 · JWT + bcryptjs · helmet · pdfkit |
| Frontend | **Next.js 16** (App Router, Turbopack, RSC) · React 19 · Tailwind v4 · next-intl · TanStack Query · Radix UI · Recharts |
| DevOps | Docker multi-stage (`node:22-slim` / `24-alpine`), `education-net`, healthchecks, GitHub Actions CI |
| Integrations | Telegram Bot API, signed video stream URLs, PDF certificates |

## 🔐 Roles in our system

| Role | Access |
|------|--------|
| `super_admin` | all + audit / settings / delete |
| `admin` | students / groups / attendance / payments / tests / videos / articles |
| `teacher` | own groups: attendance, points ±limit, grading |
| `student` | take tests / mocks, own data, videos, leaderboard |
| `parent` | read-only children via `linkCode` |

---

## 📊 Organisation stats

![GitHub Org stars](https://img.shields.io/github/stars/bestwayec/bestway?style=social)
![Last commit](https://img.shields.io/github/last-commit/bestwayec/bestway)
![Languages](https://img.shields.io/github/languages/top/bestwayec/bestway)
![Repo size](https://img.shields.io/github/repo-size/bestwayec/bestway)

- 🏢 Org: https://github.com/bestwayec
- 📦 Public repos: 1 (`bestway`, TypeScript, 191+ commits, updated Sep 2026)
- ⭐ 2 stars · 0 forks · 20 PRs · CI on every PR to `main`

---

## 🚀 How to use this profile README on GitHub

GitHub shows this file on https://github.com/bestwayec only if it lives in a special repo:

1. Create a new **public** repository named `.github` under the `bestwayec` org
2. Inside it create file `profile/README.md`
3. Paste the contents of this file there and push:

```bash
# inside this folder (bw-org):
# copy this README to profile/README.md for the .github repo
mkdir profile
cp README.md profile/README.md
git init -b main
git remote add origin https://github.com/bestwayec/.github.git
git add profile/README.md
git commit -m "feat: org profile README"
git push -u origin main
```

Alternatively name the repo `bestwayec` — GitHub also renders its README, but `.github/profile/README.md` is the canonical org profile.

---

*Built for a single center, modular for growth — StorageService & Notifications swappable to S3/CDN. Feedback: `otashdev1@gmail.com` · See `SECURITY.md` in [bestwayec/bestway](https://github.com/bestwayec/bestway).*
