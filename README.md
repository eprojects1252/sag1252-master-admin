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


## Dashboard refresh v3
- More visible green gradient header, larger brand mark, redesigned cards and buttons, clearer active navigation, and stronger responsive spacing.
- Corrected the password-reset button markup so it uses a real newline rather than a literal `\n` string.
- Service worker cache changed to `sag1252-master-admin-v3` to trigger a fresh app-shell cache after deployment.

After uploading, wait for GitHub Pages deployment to finish. If an installed PWA still shows old assets, close all tabs for the site, then clear that site's stored data/cache in the browser and reopen the deployed URL. This does not change Firebase data.


## Functional UI update v4
- Sidebar and mobile navigation switch between the dashboard screens.
- Overview module buttons open their corresponding module-status screens.
- Refresh view re-renders the current screen and explains that it does not fetch live backend data.
- Export status downloads a JSON diagnostic report with configuration/security state; it does not export customer data or secrets.
- Service worker cache bumped to v4.

## Still requires backend setup
This ZIP does not deploy Firebase rules, Cloud Functions, server code, payment gateways, hosting APIs, or SMS provider APIs. Admin role assignment, user management, audit logs, wallet balances/payments, hosting controls, SMS sending, and market data are intentionally not presented as operational. Realtime Database rules remain locked. A successful Firebase login alone does not prove admin privileges.
