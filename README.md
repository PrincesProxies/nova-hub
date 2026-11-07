# NOVA HUB — Supabase-connected starter

## Included
- Supabase email/password sign-up and sign-in.
- User profiles created automatically in `public.profiles`.
- Profile name/avatar updates saved to Supabase.
- User sessions persist through Supabase Auth.
- Existing games/music/chat demo UI retained.

## Important limits
- This update connects account authentication and profile records only.
- Chat messages, friend relationships, uploaded audio, playlists, and game history are still local demo features. They are NOT synced between users/devices yet.
- Before public launch, add chat tables and policies, moderation/reporting, rate limits, and storage rules.
- The publishable key is designed for browser use. Never add a Supabase secret/service-role key to this file.
- The profile table policies allow users to read/update only their own profile. The username is therefore not yet searchable by other users.

## Setup
1. In Supabase Dashboard, open SQL Editor, create a query, paste all of `supabase_setup.sql`, and run it.
2. In Authentication > URL Configuration, set Site URL to your deployed NOVA HUB website origin (for example `https://your-site.example`). Add the same origin to Redirect URLs.
3. In Authentication > Providers, make sure Email is enabled. Email confirmation can remain enabled; users will need to confirm their address before signing in.
4. Upload `index.html` to your host as the new site build (replace the old deployment).
5. Test account creation with an email you control. Never share your password or secret keys.

## Deployment note
This is a static HTML site. Keep `index.html` and `supabase_setup.sql` together locally for your own project records. Only `index.html` needs to be deployed to the static host.
