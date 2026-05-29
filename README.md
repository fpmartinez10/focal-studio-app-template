# [APP_NAME]

> [APP_TAGLINE]

A Focal Studio app. Built with React Native + Expo SDK 56.

---

## Getting started

```bash
npm install
npx expo start
```

Press `i` to open iOS Simulator, `a` for Android.

---

## Available scripts

| Script | What it does |
|--------|-------------|
| `npx expo start` | Start Metro bundler with dev menu |
| `npm run ios` | Start iOS Simulator directly |
| `npm run android` | Start Android emulator directly |
| `npm run lint` | Run ESLint |
| `npm run type-check` | Run TypeScript type-check |
| `npm test` | Run Jest tests |
| `npm run preview:ios` | EAS preview build (iOS) |
| `npm run build:ios` | EAS production build (iOS) |
| `npm run bump-version` | Bump version in package.json + app.json |

---

## Tech stack

| Layer | Technology |
|-------|-----------|
| SDK | Expo SDK 56 |
| Runtime | React Native (New Architecture) |
| Language | TypeScript 5.9 |
| Navigation | Expo Router 5 (file-based) |
| State | Zustand 5 |
| Storage | AsyncStorage |
| Build | EAS Build |
| Testing | Jest + React Native Testing Library |
| Analytics | PostHog RN SDK (EU-hosted, optional) |

---

## Project structure

```
app/                   # Expo Router screens
  _layout.tsx          # Root layout (providers, theme, hydration)
  index.tsx            # Entry — redirects to onboarding, auth, or tabs
  onboarding.tsx       # Multi-step onboarding flow
  paywall.tsx          # Subscription / paywall screen
  (auth)/              # Auth screens (login, signup, forgot-password)
  (tabs)/              # Main tab bar (home, settings)

src/
  components/          # Reusable UI (ui/ primitives, layout/ wrappers)
  hooks/               # useTheme
  services/            # analytics, haptics, notifications, ratingService
  store/               # Zustand stores (app, auth, onboarding, paywall)
  theme/               # Design tokens (colors, spacing, typography)
  types/               # Shared TypeScript types
  utils/               # storage helpers, pure utilities
  constants.ts         # App identity placeholders

.github/workflows/
  ci.yml               # Lint + type-check + test on every push
  eas-preview.yml      # EAS preview build on push to dev
  release.yml          # Auto-tag + GitHub Release on merge to main
  release-review.yml   # Quality gate on release/* branches
```

---

## Environment variables

Copy `.env.example` to `.env.local` and fill in the values:

```bash
cp .env.example .env.local
```

| Variable | Required | Purpose |
|----------|----------|---------|
| `EXPO_PUBLIC_POSTHOG_KEY` | No | PostHog analytics (disabled if empty) |
| `EXPO_PUBLIC_POSTHOG_HOST` | No | PostHog host (defaults to EU) |

---

## Setup

See [SETUP.md](SETUP.md) for the full new-app setup guide (~60 minutes).

---

## Claude Code optional features (Pro/Max only)

> These features require a Claude Pro or Max subscription. They are **not enabled in this repo** — both carry extra quota cost. Documented here for awareness.

- **`security-guidance` plugin** — auto-reviews code Claude writes for vulnerabilities as you work. Includes a free per-edit pattern scan (no model calls) plus optional model-backed reviews (Opus 4.7). To try it: `/plugin install security-guidance@claude-plugins-official`, then set `ENABLE_CODE_SECURITY_REVIEW=0` to keep only the free layer. [Docs](https://code.claude.com/docs/en/security-guidance)
- **Agent View** (`claude agents`) — terminal dashboard to dispatch and monitor many parallel Claude Code background sessions at once. Each session consumes quota independently, so running several in parallel multiplies usage. [Docs](https://code.claude.com/docs/en/agent-view)

---

## Privacy policy

[https://focalstudio.github.io/privacy](https://focalstudio.github.io/privacy)

---

## License

© 2026 Focal Studio. All rights reserved.
