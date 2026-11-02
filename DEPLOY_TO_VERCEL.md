# ShopSense — deploy the public demo on Vercel

This repository has been prepared for a static Vite deployment on Vercel.

## Deploy

1. Extract this ZIP file.
2. Create a GitHub repository (for example, `shopsense-demo`). Upload the **contents** of the `ShopSense-Business-App-main` folder to the repository root. Make sure `package.json`, `pnpm-lock.yaml`, `pnpm-workspace.yaml`, and `vercel.json` are at the repository root.
3. Sign in to Vercel with GitHub, choose **Add New → Project**, and import that repository.
4. Keep the project Root Directory set to `.` (the repository root). The included `vercel.json` sets the ShopSense build command, output folder, and client-side route fallback.
5. Deploy. Vercel will assign a public `*.vercel.app` URL. Share that URL with anyone who should open the demo.

If Vercel asks for build settings, use:

- Framework preset: **Vite**
- Install command: `pnpm install --frozen-lockfile`
- Build command: `PORT=4173 BASE_PATH=/ pnpm --filter @workspace/shopsense build`
- Output directory: `artifacts/shopsense/dist/public`

## Important prototype limitations

- This is a browser-side prototype. Inventory, sales, language and selected demo business are stored in the visitor's own browser (`localStorage`); they are not shared with other visitors or synced to a central database.
- The login and sign-up screens do not authenticate users. The app routes to demo screens.
- The dashboard includes seeded sample figures. Do not use it as a live accounting or stock-control system.
- No backend database or production authentication is configured in this deployment.

## Search engines

Publishing creates a working public URL, but it does not guarantee that Google will show it for a search such as “ShopSense”. After deployment, add the URL to Google Search Console and request indexing for the homepage. Google decides whether and when to index it. The free `vercel.app` address is sufficient for sharing; a custom domain such as `shopsense.in` must be purchased separately.

## Hosting plan note

Vercel's Hobby plan is free for personal, non-commercial projects. This is suitable for an academic/demo deployment. Review Vercel's current terms and usage limits before using it as a commercial service.
