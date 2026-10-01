<div align="center">

# 🎵 Mox-Player

### A modern, animation-rich landing experience for an online music school

Interactive 3D visuals · scroll-driven animations · fully responsive · type-safe end to end

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

**Mox-Player** is a front-end web application for a fictional online music school. It shows how a marketing site can feel like a product: 3D graphics, physics-inspired motion, and scroll-triggered storytelling, all built with a typed, component-driven architecture and deployed to production on Vercel.

The goal was to push past the "template landing page" and build something people remember, while keeping the codebase clean, typed, and performant.

> 🔗 **Live:** [https://mox-plyer.vercel.app](https://mox-plyer.vercel.app)

<!-- 📸 Add a hero screenshot or GIF here (recommended: 1200×630) -->
<!-- ![Mox-Player Preview](./public/preview.png) -->

---

## ✨ Features

| | Feature | Details |
|---|---|---|
| 🌍 | **Interactive 3D Globe** | A WebGL globe rendered with Three.js and React Three Fiber, showing the school's global presence |
| 🎬 | **Scroll-driven animations** | Framer Motion powers scroll-linked reveals, including a laptop and keyboard showcase section |
| 🎓 | **Course catalog** | Ten courses across guitar, piano, vocals, drums, jazz, production, songwriting and more, rendered from structured data |
| 💬 | **Testimonials carousel** | Animated student testimonials with continuous motion |
| 👥 | **Instructor showcase** | Hoverable instructor cards with smooth micro-interactions |
| 📨 | **Contact page** | Dedicated route for enquiries |
| 📱 | **Fully responsive** | Mobile-first layout built with Tailwind CSS utilities |
| ⚡ | **Optimized assets** | `next/image` for responsive, lazy-loaded images and `next/font` for font loading |

---

## 🧰 Tech Stack

**Framework & Language**
- [Next.js 14](https://nextjs.org/) (App Router), for routing, SSR/SSG and image optimization
- [React 18](https://react.dev/) and [TypeScript](https://www.typescriptlang.org/), with TypeScript making up about 99% of the codebase

**Styling & UI**
- [Tailwind CSS 3](https://tailwindcss.com/) with PostCSS
- `clsx` and `tailwind-merge` for conflict-safe conditional class composition
- [Tabler Icons](https://tabler.io/icons) and Emotion

**3D & Animation**
- [Three.js](https://threejs.org/), [React Three Fiber](https://docs.pmnd.rs/react-three-fiber) and [Drei](https://github.com/pmndrs/drei) for declarative WebGL
- [three-globe](https://github.com/vasturiano/three-globe) for the geospatial globe
- [Framer Motion](https://www.framer.com/motion/) for gesture and scroll-based animation
- `simplex-noise` for procedural noise-driven visuals

**Tooling & Deployment**
- ESLint (`eslint-config-next`), strict TypeScript config
- Continuous deployment on [Vercel](https://vercel.com/)

---

## 🏗️ Architecture Highlights

- **App Router structure**: file-based routes for Home (`/`), Courses (`/courses`) and Contact (`/contact`).
- **Component-driven UI**: reusable, typed components for the globe, animated cards, testimonials and layout sections.
- **Declarative 3D**: WebGL scenes are composed as React components through React Three Fiber, so 3D code stays in the same mental model as the rest of the UI.
- **Utility-first styling**: Tailwind plus a `cn()`-style helper (`clsx` + `tailwind-merge`) keeps styles predictable and free of class conflicts.
- **Performance-minded**: optimized images, font subsetting through `next/font`, and Next.js automatic code splitting.

---

## 🚀 Getting Started

### Prerequisites

- **Node.js** 18.17 or later
- **npm**, **yarn**, **pnpm** or **bun**

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/Anshrastogi05/mox-plyer.git
cd mox-plyer

# 2. Install dependencies
npm install

# 3. Start the development server
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

### Available Scripts

| Command | Description |
|---|---|
| `npm run dev` | Start the development server with hot reload |
| `npm run build` | Create an optimized production build |
| `npm run start` | Serve the production build |
| `npm run lint` | Run ESLint across the project |

---

## 📂 Project Structure

```
mox-plyer/
├── public/              # Static assets (course and instructor imagery)
├── src/                 # Application source (routes, components, utilities)
├── next.config.mjs      # Next.js configuration
├── tailwind.config.ts   # Tailwind theme and content configuration
├── postcss.config.mjs   # PostCSS pipeline
├── tsconfig.json        # TypeScript configuration
└── .eslintrc.json       # Linting rules
```

---

## 🗺️ Roadmap

- [ ] Dynamic course detail pages (`/courses/[slug]`)
- [ ] Authentication and student sign-up flow
- [ ] Working contact form with backend or email-service integration
- [ ] CMS-backed course data
- [ ] Payments and enrollment
- [ ] Unit and end-to-end tests (Jest and Playwright)
- [ ] Accessibility audit and Lighthouse optimization pass

---

## 💡 What I Learned

- Integrating **WebGL and Three.js** into a React and Next.js app without hurting performance or SSR compatibility
- Designing **scroll-linked animations** that feel smooth and stay accessible
- Structuring a **typed, scalable Next.js App Router** project
- Shipping and iterating on a production app through **Vercel's CI/CD**

---

## 🤝 Contributing

Contributions, issues and feature requests are welcome. Feel free to open an [issue](https://github.com/Anshrastogi05/mox-plyer/issues) or submit a pull request.

1. Fork the project
2. Create your feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m "Add amazing feature"`
4. Push to the branch: `git push origin feature/amazing-feature`
5. Open a pull request

---

## 👤 Author

**Ansh Rastogi**

- GitHub: [@Anshrastogi05](https://github.com/Anshrastogi05)


---

<div align="center">

⭐ If you found this project interesting, consider giving it a star.

</div>
