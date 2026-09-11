# AGENTS.md

## Project

A portfolio site for backend developers, inspired by Brazilian blogs from the 2000s, with emphasis on the hacker/edgy aesthetic of that era (animated GIFs, dark themes, Comic Sans, fire effects, etc.).

## Stack

- Angular 22 (standalone components, signals), TypeScript 6, Vite-based build
- Tests: Vitest via `@angular/build:unit-test` builder
- Formatter: Prettier (single quotes, 100 printWidth, Angular HTML parser)
- No linting configured

## Commands

- `npm start` — dev server
- `npm run build` — production build
- `npm test` — run unit tests (Vitest)
- `npx prettier --write .` — format

No lint or typecheck commands are configured. The build will catch TS errors.

## Project Structure

- `src/main.ts` → standalone bootstrap (no NgModule)
- `src/app/app.ts` — root component (`App`), imports `Header` and `RouterOutlet`
- `src/app/app.routes.ts` — currently empty routes array
- `src/app/header/` — header component (template + CSS only, no `.ts` spec)
- Assets served from `public/` (root-level) and `src/assets/` (mapped to `/assets/` in build)

## Conventions

- Components use inline `templateUrl` / `styleUrl` (not separate `.component.ts` naming)
- Component classes are named without `Component` suffix (e.g. `App`, `Header`)
- CSS files live next to their component (e.g. `header.css`)
- Global styles in `src/styles.css`

## Gotchas

- Assets in `src/assets/` are served at `/assets/` path — confirm before referencing new asset paths
- `app.routes.ts` is empty; header nav links reference routes (`/about`, `/contact`, `/blog`) that don't exist yet
- No environment files or `.env` loading configured
