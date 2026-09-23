# Campaign Desk hosting

This archive contains the deployable Campaign Desk frontend. It is a Vite static site and does not require a running server for the current frontend experience.

## Vercel

1. Extract the archive and push the folder to a Git repository, or upload it through Vercel.
2. Keep the project root at the repository root.
3. Vercel will use `vercel.json` automatically.
4. The build produces `artifacts/campaign-desk/dist/public`.

Equivalent settings:
- Install command: `pnpm install --frozen-lockfile`
- Build command: `pnpm --filter @workspace/campaign-desk run build`
- Output directory: `artifacts/campaign-desk/dist/public`

## Render

1. Push the extracted folder to a Git repository.
2. Create a Static Site in Render from that repository.
3. Render can use `render.yaml` automatically, or enter these settings:
   - Build command: `pnpm install --frozen-lockfile && pnpm --filter @workspace/campaign-desk run build`
   - Publish directory: `artifacts/campaign-desk/dist/public`
4. Keep the rewrite from `/*` to `/index.html` so routes such as `/campaigns` and `/reports` work after refresh.

## Important

Campaign Desk currently uses local browser state and seeded data. Campaign changes and workspace settings are not persisted across devices or refreshes until the API/database persistence work is added.
