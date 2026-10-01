<div align="center">

# 🎵 Mox-Player

### An immersive, animation-driven website for an online music school

3D WebGL globe · scroll-driven animations · data-driven course catalog · strict TypeScript

[![Live Demo](https://img.shields.io/badge/Live_Demo-mox--plyer.vercel.app-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://mox-plyer.vercel.app)

![Next.js](https://img.shields.io/badge/Next.js_14-000000?style=flat-square&logo=nextdotjs&logoColor=white)
![React](https://img.shields.io/badge/React_18-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)
![Three.js](https://img.shields.io/badge/Three.js-000000?style=flat-square&logo=threedotjs&logoColor=white)
![Framer Motion](https://img.shields.io/badge/Framer_Motion-0055FF?style=flat-square&logo=framer&logoColor=white)
![Vercel](https://img.shields.io/badge/Deployed_on_Vercel-000000?style=flat-square&logo=vercel&logoColor=white)

</div>

---

## 📖 Overview

**Mox-Player** is a multi-page front-end application for a music school. It combines a real-time **3D globe**, **scroll-linked motion**, and a **JSON-driven course catalog** inside a Next.js 14 App Router project written almost entirely in TypeScript.

It was built to explore how far a marketing site can go in feeling like a product: interactive WebGL, physics-style micro-interactions, and clean component boundaries, without sacrificing performance or type safety.

> 🔗 **Live demo:** [https://mox-plyer.vercel.app](https://mox-plyer.vercel.app)

<!-- 📸 Add a hero screenshot or GIF here (recommended: 1200×630) -->
<!-- ![Mox-Player Preview](./docs/preview.png) -->

---

## ✨ Features

### 🌍 Interactive 3D Globe
- Rendered in real time with **Three.js**, **React Three Fiber** and **three-globe**
- Country polygons drawn from a **GeoJSON dataset**, with animated **arcs and ripple rings** connecting world cities
- Auto-rotating, atmosphere-lit, configurable through a fully typed `GlobeConfig`
- Loaded with `next/dynamic` and `ssr: false`, so WebGL code never runs on the server and stays out of the initial render path
- Paired with an animated headline that cycles through the countries the school serves

### 🎬 Motion & Interaction
- **Hero section** with a spotlight effect, flip-word text animation and an animated-border CTA
- **Scroll-driven laptop showcase** using Framer Motion scroll transforms
- **3D tilt cards** on the course catalog, reacting to the cursor in real time
- **Infinite-scrolling testimonial carousel**
- **Instructor section** with a simplex-noise **wavy canvas background** and hover tooltips
- **Aurora gradient background** on the contact page
- **Floating pill navbar** with animated hover dropdowns

### 🎓 Data-Driven Course Catalog
- Ten courses defined in a single `music.json` source (title, slug, price, instructor, featured flag, image)
- Featured courses on the home page are derived by filtering on `isFeatured`, with no hard-coded lists in the UI
- Full catalog page that renders directly from the same data, with a live course count

### 📨 Contact Page
- Controlled React form with typed event handlers and native validation (`required`, `type="email"`)

### 🎨 Design System
- Dark-mode-first theme
- Custom Tailwind plugins for **color CSS variables** and **SVG grid and dot background patterns**
- `cn()` utility (`clsx` + `tailwind-merge`) for safe, conflict-free class composition

---

## 🧰 Tech Stack

| Layer | Technologies |
|---|---|
| **Framework** | Next.js 14 (App Router), React 18 |
| **Language** | TypeScript (`strict` mode), about 99% of the codebase |
| **Styling** | Tailwind CSS 3, PostCSS, `clsx`, `tailwind-merge` |
| **3D / WebGL** | Three.js, React Three Fiber, Drei, three-globe |
| **Animation** | Framer Motion, `simplex-noise` |
| **Icons** | Tabler Icons |
| **Quality** | ESLint (`eslint-config-next`) |
| **Deployment** | Vercel |

---

## 🏗️ Architecture & Engineering Decisions

- **App Router with clear route boundaries.** `/`, `/courses` and `/contact` live under `src/app/`. Pages that need no interactivity stay as server components; only interactive pieces opt into `"use client"`.
- **WebGL isolated from SSR.** The globe is dynamically imported with SSR disabled, which avoids hydration errors from browser-only APIs and keeps heavy 3D dependencies off the critical path.
- **Single source of truth for content.** Course data lives in `src/data/music.json` and is consumed by both the featured section and the catalog page through a typed `Course` interface.
- **Typed 3D configuration.** The globe exposes `GlobeConfig` and `Position` types, so scene parameters (colors, lighting, arc timing, rotation) are validated at compile time.
- **Reusable UI primitives.** Animation and layout building blocks live in `src/components/ui/`, separate from page-level composition components, which keeps the section components short and readable.
- **Path aliases.** `@/*` maps to `src/*` for clean, refactor-friendly imports.
- **Optimized media.** `next/image` for responsive, lazy-loaded imagery and `next/font` for Inter.

---

## 📂 Project Structure

```
mox-plyer/
├── public/
│   └── courses/                 # Course and instructor imagery
├── src/
│   ├── app/
│   │   ├── layout.tsx           # Root layout, global navbar, dark theme
│   │   ├── page.tsx             # Home: composes all landing sections
│   │   ├── courses/page.tsx     # Full course catalog
│   │   ├── contact/page.tsx     # Contact form
│   │   └── globals.css
│   ├── components/
│   │   ├── HeroSection.tsx
│   │   ├── Globe.tsx            # Globe config, arcs and country cycling
│   │   ├── FeaturedCourses.tsx
│   │   ├── macbookScroll.tsx
│   │   ├── TestimonialCard.tsx
│   │   ├── Instructors.tsx
│   │   ├── Footer.tsx
│   │   ├── navbar.tsx
│   │   └── ui/                  # Reusable animated primitives
│   │       ├── globe.tsx        # Three.js / three-globe renderer
│   │       ├── 3d-card.tsx
│   │       ├── macbook-scroll.tsx
│   │       ├── infinite-moving-cards.tsx
│   │       ├── wavy-background.tsx
│   │       ├── aurora-background.tsx
│   │       └── ...
│   ├── data/
│   │   ├── music.json           # Course catalog
│   │   └── globe.json           # GeoJSON country geometry
│   └── utils/cn.ts              # Class-name helper
├── tailwind.config.ts           # Custom plugins (color vars, SVG patterns)
├── tsconfig.json                # Strict TS + path aliases
└── next.config.mjs
```

---

## 🚀 Getting Started

### Prerequisites
- **Node.js** 18.17+
- npm, yarn, pnpm or bun

### Run locally

```bash
# Clone the repository
git clone https://github.com/Anshrastogi05/mox-plyer.git
cd mox-plyer

# Install dependencies
npm install

# Start the dev server
npm run dev
```

Open [http://localhost:3000](http://localhost:3000).

### Scripts

| Command | Description |
|---|---|
| `npm run dev` | Start the development server with hot reload |
| `npm run build` | Create an optimized production build |
| `npm run start` | Run the production build |
| `npm run lint` | Lint the codebase with ESLint |

---

## 🗺️ Roadmap

- [ ] Dynamic course detail pages at `/courses/[slug]` (slugs already exist in the data model)
- [ ] Persist contact form submissions (API route plus email service or database)
- [ ] Authentication and student enrollment flow
- [ ] SEO: page-level metadata, Open Graph tags and sitemap
- [ ] Accessibility pass (reduced-motion support, keyboard navigation, ARIA labels)
- [ ] Automated tests (Jest and React Testing Library, Playwright for end-to-end)
- [ ] Move course data to a headless CMS or database

---

## 🙏 Acknowledgements

Several animated UI primitives in `src/components/ui/` are adapted from [Aceternity UI](https://ui.aceternity.com/) and customized for this project. Built on the shoulders of [Next.js](https://nextjs.org/), [Three.js](https://threejs.org/), [three-globe](https://github.com/vasturiano/three-globe) and [Framer Motion](https://www.framer.com/motion/).

---

## 👤 Author

**Ansh Rastogi**

- GitHub: [@Anshrastogi05](https://github.com/Anshrastogi05)
- LinkedIn: _add your link here_
- Portfolio: _add your link here_

---

<div align="center">

⭐ If you found this project interesting, consider giving it a star.

</div>
