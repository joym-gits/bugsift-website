# bugsift.dev

Marketing landing page for [bugsift](https://github.com/joym-gits/bugsift).
Single static HTML file, deployed to Firebase Hosting.

## Deploy

```sh
npm install -g firebase-tools
firebase login
firebase use --add          # pick or create your Firebase project
firebase deploy --only hosting
```

## Custom domain

Add your domain in the Firebase console → Hosting → Add custom domain.
Firebase provisions TLS via Let's Encrypt automatically.

## Vanity install URL

`firebase.json` includes a 301 rewrite so once deployed, anyone can run:

```sh
curl -fsSL https://bugsift.dev/install | bash
```

…and Firebase will redirect to the latest `install.sh` on GitHub.

## Files

- `public/index.html` - the landing page (single file, inline CSS, no build step).
- `public/favicon.svg` - favicon.
- `public/og-image.svg` - source for the OG preview. Export to `og-image.png` at
  1200×630 for best compatibility. Any SVG → PNG tool works (`rsvg-convert`,
  CloudConvert, screenshot, etc.).
- `firebase.json` - hosting config (cache headers, security headers, rewrite).
- `.firebaserc` - Firebase project binding. Replace the placeholder with your
  project ID, or run `firebase use --add`.
