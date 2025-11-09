# Crash Compass Web

Crash Compass Web is the front-end for the Crash Compass project. It is a Next.js 15 application that renders dashboards and navigation for the economic indicators served by the Crash Compass API. The UI is designed to surface themed groupings of Federal Reserve Economic Data (FRED) series—such as labor, consumers, and housing—and will evolve alongside the API.

## Features

- Global navigation that mirrors the Crash Compass economic themes (Labor Market, Consumers, Financial Conditions, Production, Housing).
- Responsive layout scaffolded with Tailwind CSS and the Geist font family.
- Ready-to-integrate charting powered by [`lightweight-charts`](https://github.com/tradingview/lightweight-charts) for plotting time-series data returned by the API.
- Configured Next.js 15 app router structure with shared layout, header component, and static assets.

## Prerequisites

- Node.js 18.18+ (or any version supported by Next.js 15)
- npm 9+ (bundled with the recommended Node.js release)
- Access to the Crash Compass API deployment for live data (optional for local UI development)

## Getting Started

1. **Install dependencies**
   ```bash
   npm install
   ```

2. **Run the development server**
   ```bash
   npm run dev
   ```

   The app will be available at [http://localhost:3000](http://localhost:3000). The dev server uses Turbopack for fast refresh by default.

3. **Open the project**
   Navigate to `http://localhost:3000` in your browser. Edit files under `app/` (for example, `app/page.tsx`) to see live updates.

## Connecting to the API

The front-end expects data from the Crash Compass API (FastAPI service documented in the backend repository). During local development you can:

- Run the API locally (see the backend README for setup) and configure your data-fetching hooks or requests to target that host.
- Stub or mock API responses while designing components if the backend is unavailable.

When deploying, ensure the web app is configured to call the correct API base URL (for example, via environment variables or Next.js runtime configuration as you introduce data fetching).

## Available Scripts

```bash
npm run dev     # Start the Next.js dev server with Turbopack
npm run build   # Build the production bundle
npm run start   # Launch the production server (after build)
npm run lint    # Run ESLint over the project
```

## Project Structure

```
app/
  layout.tsx          # Global layout with shared fonts, metadata, and header
  page.tsx            # Landing page shell
  components/
    Header.jsx        # Navigation bar
public/
  CCFav.svg, CCLogo.svg, ...  # Branding assets
```

## Styling & Fonts

The project uses Tailwind CSS v4 (via the `@tailwindcss/postcss` plugin) and the Geist sans/mono fonts from Vercel. Global styles live in `app/globals.css`. Adjust the Tailwind configuration in `postcss.config.mjs` or add utility classes directly within your components.

## Contributing

1. Create a feature branch.
2. Implement your changes and ensure the UI builds and linting passes.
3. Submit a pull request describing your changes and any relevant screenshots.

## License

This project is proprietary and intended for internal use. Contact the maintainers for licensing details.
