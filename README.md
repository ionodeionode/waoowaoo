<p align="center">
  <a href="https://www.waoowaoo.com/">
    <img src="images/cta-banner.png" alt="🚀 Explore the next generation of AI filmmaking | Join the waoowaoo online beta waitlist" width="800">
  </a>
</p>

<p align="center">
  <img src="public/banner.png" alt="waoowaoo" width="600">
</p>

<h1 align="center">waoowaoo AI Film Studio</h1>

<p align="center">
  An AI-powered short drama / comic video production tool that automatically generates storyboards, characters, and scenes from novel text, and assembles them into a complete video.
</p>

<p align="center">
  <a href="README_en.md">English</a> · <a href="https://www.waoowaoo.com/">Join the Beta Waitlist</a> · <a href="https://github.com/saturndec/waoowaoo/issues">Report an Issue</a>
</p>

> [!IMPORTANT]
> ⚠️ **Beta Disclaimer**: This project is in an early beta stage. As it is currently developed by a single person, there are some bugs and rough edges. We are iterating quickly — **feel free to join the community to report issues and suggest features, and stay tuned for updates! Updates will be very frequent at this stage. Many new features and improvements are coming. Our goal is to become the most powerful AI tool in the industry!**

<img src="images/dab6b4105e3260f37ba2d5f536dce259.jpg" width="30%">

---

## ✨ Features

- 🎬 **AI Script Analysis** — Automatically parses novels, extracting characters, scenes, and plot
- 🎨 **Character & Scene Generation** — AI generates consistent character and scene images
- 📽️ **Storyboard Video Production** — Automatically creates storyboard panels and assembles them into video
- 🎙️ **AI Voice Synthesis** — Multi-character text-to-speech
- 🌐 **Multilingual Support** — Chinese / English interface, switchable in the top-right corner

---

## 🚀 Quick Start

**Prerequisites**: Install [Docker Desktop](https://docs.docker.com/get-docker/)

### Option 1: Pull Pre-built Image (Easiest)

No need to clone the repo — download and run:

```bash
# Download docker-compose.yml
curl -O https://raw.githubusercontent.com/saturndec/waoowaoo/main/docker-compose.yml

# Start all services
docker compose up -d
```

> ⚠️ This is a beta version; the database is not compatible between versions. To upgrade, clear old data first:

```bash
docker compose down -v
docker rmi ghcr.io/saturndec/waoowaoo:latest
curl -O https://raw.githubusercontent.com/saturndec/waoowaoo/main/docker-compose.yml
docker compose up -d
```

> After starting, **clear your browser cache** and log in again to avoid issues caused by stale caches.

### Option 2: Clone Repo + Docker Build (Full Control)

```bash
git clone https://github.com/saturndec/waoowaoo.git
cd waoowaoo
docker compose up -d
```

To update:
```bash
git pull
docker compose down && docker compose up -d --build
```

### Option 3: Local Development Mode (Developers)

```bash
git clone https://github.com/saturndec/waoowaoo.git
cd waoowaoo

# Copy the environment variable config file (must be done before npm install)
cp .env.example .env
# ⚠️ Edit .env and fill in your AI API keys (NEXTAUTH_URL defaults to http://localhost:3000, no change needed)

npm install

# Start infrastructure only
# Note: docker-compose.yml maps services to non-standard ports; .env.example is pre-configured accordingly
# mysql:13306  redis:16379  minio:19000
docker compose up mysql redis minio -d

# Initialize database schema (required on first run — skipping this will cause errors on startup)
npx prisma db push

# Start the development server
npm run dev
```

> [!WARNING]
> Skipping `npx prisma db push` will result in all database tables missing, and you will see `The table 'tasks' does not exist` errors on startup. Always run this command before starting the development server.

---

Visit [http://localhost:13000](http://localhost:13000) (Options 1 & 2) or [http://localhost:3000](http://localhost:3000) (Option 3) to get started!

> On first startup, the database is automatically initialized — no additional configuration required.

> [!TIP]
> **If you experience sluggish page loads**: HTTP mode may cause browsers to limit concurrent connections. You can install [Caddy](https://caddyserver.com/docs/install) to enable HTTPS:
> ```bash
> caddy run --config Caddyfile
> ```
> Then visit [https://localhost:1443](https://localhost:1443)

---

## 🔧 API Configuration

After starting, go to the **Settings Center** to configure your AI service API keys. A built-in configuration tutorial is included.

> 💡 **Note**: Currently, only official provider APIs are recommended. Third-party OpenAI-compatible formats are not yet fully supported and will be improved in future versions.

---

## 📦 Tech Stack

- **Framework**: Next.js 15 + React 19
- **Database**: MySQL + Prisma ORM
- **Queue**: Redis + BullMQ
- **Styling**: Tailwind CSS v4
- **Auth**: NextAuth.js

---

## 📦 Feature Preview

![4f7b913264f7f26438c12560340e958c67fa833a](https://github.com/user-attachments/assets/fa0e9c57-9ea0-4df3-893e-b76c4c9d304b)
![67509361cbe6809d2496a550de5733b9f99a9702](https://github.com/user-attachments/assets/f2fb6a64-5ba8-4896-a064-be0ded213e42)
![466e13c8fd1fc799d8f588c367ebfa24e1e99bf7](https://github.com/user-attachments/assets/09bbff39-e535-4c67-80a9-69421c3b05ee)
![c067c197c20b0f1de456357c49cdf0b0973c9b31](https://github.com/user-attachments/assets/688e3147-6e95-43b0-b9e7-dd9af40db8a0)

---

## 🤝 Contributing

This project is independently maintained by a core team. You are welcome to participate in the following ways:

- 🐛 Submit an [Issue](https://github.com/saturndec/waoowaoo/issues) to report a bug
- 💡 Submit an [Issue](https://github.com/saturndec/waoowaoo/issues) to propose a feature
- 🔧 Submit a Pull Request for reference — we will carefully review every PR's approach, but fixes will ultimately be implemented by the team; external PRs will not be merged directly

---

**Made with ❤️ by the waoowaoo team**

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=saturndec/waoowaoo&type=date&legend=top-left)](https://www.star-history.com/#saturndec/waoowaoo&type=date&legend=top-left)
