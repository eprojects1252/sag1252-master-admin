# Sri Amirthaa Groups 1252 Master Admin PWA — starter

## Included
- Responsive mobile-first admin interface
- Firebase Email/Password sign-in and Google popup sign-in
- Installable PWA manifest, SVG icon, and service worker
- Overview plus Admin Management, Security & Activity Logs, Wallet, Cloud Hosting, OTP/SMS, Share Market, and Integrations screens

## Important security state
- The Realtime Database is expected to remain locked with `.read: false` and `.write: false` until proper rules are designed.
- Authentication does NOT automatically grant Chief Admin privileges. This starter intentionally does not write admin roles or access the database.
- Admin role assignment, admin creation, audit-log writing, and privileged changes must be performed by trusted server-side code or another secure privileged workflow. Do not grant roles by editing a client-side field.
- This is a starter prototype, not production-ready. No Cloud Functions are deployed; no database reads/writes, wallet transactions, payment operations, or admin role management are active.

## Deploy/test
1. Keep the files together and host them on HTTPS (or use localhost for development). Opening `index.html` directly as a `file://` URL will not support the Firebase module imports or PWA install.
2. Firebase project: `sriamirthaagroups1252chifpanel`.
3. In Firebase Authentication, enable Email/Password and Google providers (already enabled per setup notes). Ensure the actual hosting domain is listed in Authentication > Settings > Authorized domains.
4. Firebase web config is in `index.html`. Web API keys/config are client-side identifiers; never add service-account private keys, Razorpay secret keys, or provider API secrets.
5. Test login first. Newly created users remain unprivileged until a secure role assignment is completed.
6. On Android Chrome, visit the HTTPS site and use the browser menu > Install app / Add to Home screen if the install prompt is not shown.

## Next required step
Choose a safe, privileged role-assignment approach that does not expose private keys in the browser. Since Cloud Functions deployment currently requests a billing upgrade, keep database rules locked while evaluating alternatives.


## Dashboard update (2026-10)
- Refreshed responsive visual styling, cards, spacing, focus states, and button feedback.
- Added Firebase password-reset email flow.
- Replaced raw Firebase error details with clearer user-facing messages.
- Added a visible warning for signed-in users whose Admin role is not verified.
- Bumped service-worker cache to v2 so deployed clients can receive the updated shell.

Security and functionality boundary:
- These changes do not grant Admin/Chief Admin privileges.
- Admin Management, audit logs, wallet, hosting, OTP/SMS, market and integrations remain informational placeholders until trusted server-side services and authorization rules are implemented.
- Firebase Realtime Database rules remain locked. Do not loosen them to make the UI appear functional.
