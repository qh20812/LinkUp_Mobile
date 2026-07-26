# LinkUp Mobile — AGENTS.md

> React Native 0.86.0 CLI (TypeScript). Not Expo.

## Build & run

```bash
npm install                           # install deps
npx react-native start                # Metro bundler
npx react-native run-android          # Android emulator/device
npx react-native run-ios              # iOS simulator (macOS only)
```

## Verify

```bash
npm run lint          # ESLint
npm run test          # Jest
npx tsc --noEmit      # TypeScript check
```

## Stack

| Layer | Choice |
|---|---|
| Framework | React Native 0.86.0 (CLI) |
| Language | TypeScript 5.8 |
| Navigation | None yet — default template |
| State | None yet |
| HTTP | None yet |
| Testing | Jest + react-test-renderer |
| Bundler | Metro |

## Project structure

```
mobile/
├── android/          # Android native project
├── ios/              # iOS native project
├── __tests__/        # Jest tests
├── App.tsx           # Root component
├── index.js          # Entry point (AppRegistry.registerComponent)
├── metro.config.js   # Metro bundler config
├── babel.config.js   # Babel config
├── tsconfig.json     # TypeScript config
│   .eslintrc.js      # ESLint config
│   .prettierrc.js    # Prettier config
└── package.json
```

## Conventions (to follow when adding code)

- **Navigation:** Use `@react-navigation/native` (add when needed)
- **HTTP layer:** Use `axios` or a wrapper around `fetch` (TBD)
- **State:** Start with React Context + hooks; add Zustand/Redux if complexity grows
- **API base URL:** Configured externally (not committed). Add `.env` support via `react-native-config`
- **Icons:** No icon library yet — add `react-native-vector-icons` when needed
- **Styling:** `StyleSheet.create` (vanilla RN), no CSS-in-JS

## Backend API

Server runs at `http://10.0.2.2:8080` (Android emulator → host localhost). For iOS simulator, use `http://localhost:8080`. For physical devices, use the machine's LAN IP.

## Root project

This is a standalone repo (`LinkUp_Mobile`). The `mobile/` directory is a git submodule pointer in the root `CAPSTONE-PROJECT` repo. Always commit+push from this directory first, then update the pointer in root.
