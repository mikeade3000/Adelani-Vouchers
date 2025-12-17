# Voucher Approval App (Static HTML/CSS/JS + Supabase) — No Notifications

This is a client-only app:
- HTML/CSS/JS runs on GitHub Pages (or any static host)
- Supabase provides Auth + Database + Storage + Realtime (multi-user concurrency)

## 1) Supabase setup
1. Create a Supabase project
2. SQL Editor: run `supabase_schema.sql`
3. Storage: create bucket `vouchers` (private)
4. Realtime/Replication: enable realtime for table `vouchers`

## 2) GitHub Pages / Auth Redirect URLs (Important)
Supabase → Authentication → URL Configuration
- Site URL: https://YOUR_GITHUB_USERNAME.github.io/YOUR_REPO/
- Additional Redirect URLs: add the same URL
(Optional local testing)
- http://127.0.0.1:8080/

## 3) Configure the site
Open the site and click **Settings** (top-right). Enter:
- Supabase URL
- Supabase anon public key
Then Save and refresh.

## 4) Create first Super Admin (one-time)
Register a user normally in the app.
Then in Supabase Table Editor → `profiles`, set that user's `role` = `super_admin`.
After that, Super Admin can set Finance/Chairman roles from the UI.

## 5) Run locally (Windows)
From the folder containing `index.html`:
py -m http.server 8080
Open: http://127.0.0.1:8080
