# Nexaro Edit Hub

Mobile-first editing-app directory with search/filter, official sources, third-party APK catalogs, security links, community resources, and Groq recommendations through a Supabase Edge Function.

## Current integration
- Frontend calls `https://cvwkvwvdtvmhlqpdyojn.supabase.co/functions/v1/nexaro-edit-recommend`.
- Edge Function reads the server-side secret `GROQ_API_KEY_2`.
- Never add the Groq key, Supabase service-role key, or database password to static files.
- `supabase/schema.sql` creates a read-only public directory table using RLS and seeds known sources.

## Publish on GitHub Pages
Upload `index.html`, `styles.css`, and `app.js` to the repository root or a Pages-published directory. The existing repository `black444yt8610-alt/Nexaro` is not overwritten by this package. If placed in its `edit-hub/` folder, the likely URL is `https://black444yt8610-alt.github.io/Nexaro/edit-hub/`, provided Pages is enabled for that repo and branch.

## Supabase
Run `supabase/schema.sql` in the SQL editor after the project is active. The existing project restore was requested, but database migration and Edge Function deployment have not yet been confirmed.

## Security notes
The AI endpoint is public to the allowed web origin; configure platform rate limits/abuse protection before sharing widely. Origin checks are not authentication. A public directory never guarantees APK safety. Verify publisher, signature and permissions; scanner results are not a guarantee.
