# Miran Procurement Dashboard

Static GitHub/Vercel package for the **Miran Gas Project — Procurement Control Board**.

## Included files

- `index.html` — main dashboard application
- `404.html` — fallback page for static hosting
- `vercel.json` — Vercel routing and basic security headers
- `.gitignore` — prevents local files and secrets from being committed
- `.env.example` — placeholders for the later Supabase connection
- `robots.txt` — asks search engines not to index the dashboard

## Important current limitation

This version still stores users and uploaded tracker information in each browser's `localStorage`. Publishing it to GitHub/Vercel makes the same dashboard URL available to the team, but it does **not yet synchronize** Excel uploads, accounts, or changes between different computers.

Supabase authentication and the shared cloud database must be connected in the next development stage.

## Create the GitHub repository

1. Sign in to GitHub.
2. Select **New repository**.
3. Repository name: `miran-procurement-dashboard`.
4. Choose **Private** for company use.
5. Do not add another README, `.gitignore`, or license because this package already contains the required files.
6. Select **Create repository**.

## Upload without Git commands

1. Open the new empty repository.
2. Select **uploading an existing file** or **Add file → Upload files**.
3. Extract the supplied ZIP on your computer.
4. Upload the files *inside* the extracted folder, not the ZIP itself.
5. Confirm that `index.html` is at the repository root.
6. Commit message: `Initial Miran procurement dashboard`.
7. Select **Commit changes**.

Correct structure:

```text
miran-procurement-dashboard/
├── index.html
├── 404.html
├── vercel.json
├── README.md
├── robots.txt
├── .gitignore
└── .env.example
```

Incorrect structure:

```text
miran-procurement-dashboard/
└── Miran_Procurement_Dashboard_GitHub_Ready/
    └── index.html
```

## Connect the GitHub repository to Vercel

1. Sign in to Vercel.
2. Select **Add New → Project**.
3. Import `miran-procurement-dashboard` from GitHub.
4. Framework preset: **Other**.
5. Root directory: leave blank.
6. Build command: leave blank.
7. Output directory: leave blank.
8. Select **Deploy**.

Vercel will serve `index.html` automatically.

## Updating the dashboard code later

1. Open `index.html` in GitHub.
2. Select the pencil icon to edit it, or upload a replacement file with the same name.
3. Commit the change to the `main` branch.
4. Vercel will automatically create a new production deployment.

## Security warning

The existing owner login and browser-based access manager are suitable only as a temporary prototype. They are not secure server-side authentication. Do not publish the repository publicly and do not store Supabase secret/service-role keys in `index.html`, GitHub, or any browser-accessible JavaScript.
