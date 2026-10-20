# Ziorpure Website + Admin Price Manager

Responsive one-page store with the supplied product photos, animated design, cart, quantity controls, automatic subtotal, and WhatsApp checkout to **03138681319**. Delivery charges are not included and are requested for confirmation over WhatsApp.

## Manage prices from the admin page

The admin page is `admin.html`. GitHub Pages is static hosting, so to save prices online for every visitor, this package uses a free Supabase database. Complete these one-time setup steps:

1. Create a project at https://supabase.com/.
2. In Supabase, open **Authentication → Users** and create your own admin user. Keep the email/password private. If email confirmation is required, confirm the user.
3. Copy that user's UUID from the Users page.
4. Open **SQL Editor**, paste `supabase-schema.sql`, replace every occurrence of `YOUR_ADMIN_USER_UUID` with your UUID, then run it.
5. Open **Project Settings → API** (or **Connect**) and copy the Project URL and the `anon`/publishable key. Do NOT use a `service_role` or secret key in the website.
6. Edit `backend-config.js` and replace `YOUR_SUPABASE_PROJECT_URL` and `YOUR_SUPABASE_ANON_KEY` with those two values.
7. Upload the whole folder contents to your GitHub repository, preserving `assets/`.
8. On your live site, open `/admin.html`, sign in with the admin account, and adjust any product price. Press **Save price**. Prices will be read by the public store and totals will calculate in the cart.

Example: if your GitHub Pages site is `https://USERNAME.github.io/ziorpure-website/`, the admin page is `https://USERNAME.github.io/ziorpure-website/admin.html`.

### Security notes
- The public `anon` key is designed to be present in browser code; database access is restricted by Row Level Security (RLS).
- Never put a Supabase `service_role`/secret key in `backend-config.js`.
- The SQL policy must contain your own admin UUID. This is what restricts price updates to your admin account.
- Keep admin credentials private. The admin URL alone does not grant edit access.

## Product list
- Keratin Pearl Shampoo — original supplied photo
- Nourishing Hair Serum — original supplied photo
- Hair Mask — supplied product photo
- Kojic Soap — supplied product photo
- Herbal Soap — supplied product photo

Prices start blank because you haven't provided them yet. Set prices through `admin.html` after backend setup.
