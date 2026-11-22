# UniTrack University ERP — Deployment Package

This package scaffolds the supplied UniTrack ERP React/TSX interface into a Vite project so it can be built and deployed to Vercel.

## Important status
**This is a deployable demo/prototype, not a production ERP.** The supplied app currently stores its records in browser `localStorage` and includes demo account credentials in its source. It does not yet authenticate through Supabase or persist shared data in a cloud database. Do not enter real student, staff, fee, parent-contact, or other confidential data. A deployment makes the demo available on the internet; it does not make its demo login secure.

## Run locally
1. Install Node.js LTS.
2. Extract this ZIP and open the project folder in Terminal/PowerShell.
3. Run:
   ```bash
   npm install
   npm run dev
   ```
4. Open the local URL printed by Vite.

## Build check / preview
```bash
npm run build
npm run preview
```

## Deploy to Vercel (GitHub route)
1. Create a GitHub repository and upload the contents of this folder (not the ZIP itself).
2. In Vercel, choose **Add New → Project** and import that repository.
3. Framework preset: **Vite**. Build command: `npm run build`. Output directory: `dist`.
4. Deploy. No environment variables are required for this demo build.
5. After deployment, test the site on desktop and mobile, login, navigation, sample CRUD, and refresh persistence.

## Demo login
The original source contains these demo credentials:
- Admin: `admin@unitrack.edu.in` / `admin123`
- Faculty: `ramakrishna.cse@unitrack.edu.in` / `faculty123`
- Faculty: `lakshmi.ece@unitrack.edu.in` / `faculty123`

**These credentials are visible in the client code and are not secure.** This is only for demonstrating the interface. Do not use these passwords for any real account.

## Supabase starter schema
The `supabase/schema.sql` file is a starter schema inspired by the supplied deployment guide. It is not wired to the app yet. Review policies with your institution's security requirements before using real data. Never expose a Supabase service-role key in frontend code.

## Next step for real production use
Replace the demo login and localStorage data layer with Supabase Auth + database calls, implement role/branch/section authorization using restrictive Row Level Security, add server-side audit logging, validate every operation, and test backup/restore and privacy requirements.
