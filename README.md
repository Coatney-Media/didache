# 🧱 Didache Project – Increment 1

Welcome to **Didache**, a next-generation learning platform for **Koine Greek** built with the **PAANG** stack (Prisma, Apollo, Angular, Nx, GraphQL).

> **Increment 1 Goal:**  
> Lay the architectural foundation and build the first interactive learning module:  
> The Koine Greek Alphabet with TTS playback and an adaptive onboarding UI.

---

## 🚀 What's Included in Increment 1

### ✅ Nx Workspace Structure

- Monorepo initialized with Nx for scalable frontend + backend development
- Organized with apps, libs, and typed API contracts
- Plugins installed: `@nx/angular`, `@nx/nest`, `@nx/storybook`, `@nx/jest`

```text
apps/
greek-learning-app/     → Angular 21, mobile-first
api/                    → NestJS backend with REST + GraphQL ready

libs/
greek-alphabet/         → Displays 24 Koine Greek letters
diagnostic-ui/          → Onboarding flow to assess user knowledge
tts/                    → OpenAI TTS proxy & playback
core/                   → Shared types, models, state utilities
```

---

### 🔤 Greek Alphabet Module

- Fully responsive component showing all 24 Koine letters
- Upper/lowercase, English names, and optional mnemonics
- Each letter features **TTS playback** via OpenAI's API

> **Technologies:** Angular standalone components, SCSS, HTML5 Audio, OpenAI TTS

---

### 🧠 Diagnostic UI

- Interactive, adaptive questionnaire determines user’s starting point
- Local state + localStorage used for onboarding flow
- Simple routing logic to direct new learners to the alphabet or more advanced modules

---

### 🔊 OpenAI TTS Proxy

- NestJS backend endpoint: `GET /api/tts/:text`
- Calls OpenAI TTS and streams back audio/mpeg
- Angular service consumes and plays audio in real time
- Future upgrade path: SSR caching, phoneme refinement

---

### 🔧 Developer Experience Tools

- ESLint + Prettier with Nx plugin integration
- Husky + lint-staged for commit-time quality checks
- Storybook configured with sample components (`LetterCard`)
- Unit testing (Jest) and E2E testing (Playwright) scaffolded

---

### 🧩 PAANG Stack Foundations

- ✅ **Angular** 21 frontend (Standalone Components + SCSS)
- ✅ **NestJS** backend
- ✅ **Nx** workspace for scale
- ✅ **GraphQL** scaffolded and running side-by-side with REST
- ✅ **Prisma** ORM installed with placeholder schema

```prisma
model User {
  id       String @id @default(cuid())
  email    String @unique
  progress Progress[]
}

model Progress {
  id       String @id @default(cuid())
  userId   String
  lessonId String
  score    Int
}
```
