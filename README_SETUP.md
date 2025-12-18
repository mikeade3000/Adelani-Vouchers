# Voucher Approval App (Static HTML/CSS/JS + Supabase) — Fixed Login/Profile

## Why you saw: "Cannot coerce the result to a single JSON object"
That error happens when the app tries to load your `profiles` row but it doesn't exist yet (common when Email Confirmation is ON).
This build auto-creates the profile row on first successful login.

## Supabase setup
1. Create a Supabase project
2. SQL Editor: run `supabase_schema.sql`
3. Storage: create bucket `vouchers` (private)
4. Enable realtime for table `vouchers` (Database → Replication)

## GitHub Pages / Redirect URLs (Important)
Supabase → Authentication → URL Configuration
- Site URL: https://YOUR_GITHUB_USERNAME.github.io/YOUR_REPO/
- Additional Redirect URLs: add the same URL

For your case:
- https://mikeade3000.github.io/Adelani-Vouchers/

## Configure the app
Open your website → click **Settings** → enter:
- Supabase URL
- Supabase anon public key
Save → page refreshes.

## Create first Super Admin (one-time)
Register & confirm, then login.
In Supabase Table Editor → `profiles`, set your role to `super_admin`.
Then you can assign Finance/Chairman roles inside the app.

## Supabase configuration
This build has the Supabase URL + anon key embedded, so users will not see any configuration panel.
