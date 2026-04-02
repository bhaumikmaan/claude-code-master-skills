# Project Overrides — Browser Testing

## Dev Server
<!-- How to start and access the dev server. -->
- Start command: <!-- e.g., pnpm dev -->
- URL: <!-- e.g., http://localhost:3000 -->
- Ready signal: <!-- e.g., "Ready on http://localhost:3000" in terminal output -->

## Authentication
<!-- Steps to authenticate before testing protected pages. -->
- <!-- e.g., Navigate to /login, fill email: test@example.com, password: test123 -->
- <!-- e.g., Use cookie injection via browser tool for test session -->
- <!-- e.g., No auth needed — all pages are public in dev mode -->

## Key Pages to Test
<!-- Important routes and what to verify on each. -->
- <!-- e.g., / — landing page loads, hero image visible, CTA button works -->
- <!-- e.g., /dashboard — charts render, data table populates, filters work -->
- <!-- e.g., /settings — form saves, toast notification appears -->

## Framework-Specific Patterns
<!-- Testing patterns specific to the project's frontend framework. -->
- <!-- e.g., React: check for hydration warnings in console -->
- <!-- e.g., Next.js: verify SSR by checking page source for content -->
- <!-- e.g., SPA: wait for client-side routing, not full page loads -->

## Console Filters
<!-- Patterns to ignore or highlight in console output. -->
- Ignore: <!-- e.g., "Download the React DevTools" warning -->
- Alert on: <!-- e.g., Any "Unhandled" error, any "CORS" message -->
