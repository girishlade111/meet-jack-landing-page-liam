# Meet Jack Landing Page — Liam

A marketing landing page introducing **Jack**, a playful robot/UFO mascot character, for the "Liam" brand. Features an interactive 3D hero scene (Spline), character showcases (front/side/back views), and a branded footer with the UFO mascot.

## What it does

- **3D hero section** — interactive Spline scene behind a bold hero text overlay with rotating text accent
- **Character showcase** — front, side, and back views of the Jack character on a grid-pattern card
- **Brand header/footer** — Liam logo, navigation header, and footer with the Jack UFO artwork
- Fully client-side; no backend, no forms, no data collection

## Features

- Spline 3D scene with loading state and error fallback
- Animated hero text overlay + rotating circular text accent
- Character gallery (front/side/back PNG renders)
- shadcn/ui components with theme provider (light/dark)
- Responsive layout (mobile + desktop)
- Static-site friendly — builds to plain HTML/CSS/JS (`output: 'export'`)

## Tech stack

- **Next.js 14** (App Router, static export)
- **React 18**, **TypeScript 5**
- **Tailwind CSS 3**
- **@splinetool/react-spline** — 3D hero scene
- **shadcn/ui** (Radix primitives), `lucide-react` icons
- next-themes for theming

## Quick start

```bash
# install dependencies
npm install          # or: pnpm install

# run the dev server
npm run dev          # open http://localhost:3000

# production build (static export to ./out)
npm run build
```

Serve the static export with any static host:

```bash
npx serve out
```

## Project structure

```
app/                 # Next.js App Router (layout, page, global styles)
components/
  spline-scene.tsx       # interactive Spline 3D hero scene (client)
  hero-text-overlay.tsx  # hero headline overlay
  rotating-text-accent.tsx # rotating circular logo text
  header.tsx / footer.tsx  # brand chrome
  theme-provider.tsx       # next-themes provider
  ui/                      # shadcn/ui primitives
lib/utils.ts         # cn() class helper
public/              # character renders (jack-front/side/back.png), UFO art, logos
next.config.mjs      # output: 'export', unoptimized images
```

## Environment variables

None — the Spline scene is embedded client-side; no secrets needed.

## Deployment notes

- Statically exported (`out/`), so it can be hosted on **GitHub Pages**, **Vercel**, **Netlify**, or any static file host.
- `next.config.mjs` sets `basePath: '/meet-jack-landing-page-liam'` for the GitHub Pages subpath deployment, and raw `<img>` paths in the components include that prefix. For root-domain deploys (Vercel/custom domain), remove the `basePath` line, revert the `/meet-jack-landing-page-liam` image path prefixes to `/`, and rebuild.

---

Built by Girish Lade — [ladestack.in](https://ladestack.in)
