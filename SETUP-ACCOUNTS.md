# Turning on accounts (Cloudflare Pages)

Accounts need two things: the `functions/` folder (already in this site) and one KV namespace.

1. Cloudflare dashboard -> Storage & Databases -> KV -> Create a namespace (any name, e.g. holesmp-progress).
2. Workers & Pages -> your project -> Settings -> Bindings (or Functions) -> Add -> KV namespace.
   - Variable name: PROGRESS   (must be exactly this)
   - KV namespace: the one you just made
   Do this for Production (and Preview if you use it).
3. Deploy the whole folder so `functions/` is included:
   - Git-connected project: push everything, including `functions/`.
   - Direct Upload: use Wrangler: `npx wrangler pages deploy . --project-name YOUR_PROJECT`
     (Dashboard drag-and-drop may not run the functions folder.)
4. Open the site and click "Sign in" in the top menu.

Until this is set up, the site still works and saves progress on the device only;
the Sign in window just says accounts aren't available yet.

Notes
- Passwords are salted and hashed (PBKDF2); they are never stored in plain text.
- There are no emails, so there is no password reset.
- Tell students not to use their real names as usernames. If students under 13 will use accounts,
  check your school or district's privacy rules (COPPA/FERPA) first.
