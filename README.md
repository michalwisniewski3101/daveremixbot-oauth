# DaveRemixBot GitHub Pages OAuth Bridge

This folder is a static GitHub Pages site for TikTok and Instagram OAuth callbacks.

It contains no secrets and no server-side code. The platform redirects the browser to `tiktok-callback.html` or `instagram-callback.html`, and the page forwards the OAuth query string (`code`, `state`) to the private local DaveRemixBot callback.

Treat the callback URL as sensitive while OAuth is in progress. Do not paste full callback URLs with `code` or `state` into chats, logs, screenshots, or issue trackers.

## Files

- `index.html` - public app information page.
- `terms.html` - public Terms of Service page.
- `privacy.html` - public Privacy Policy page.
- `tiktok-callback.html` - static TikTok OAuth bridge.
- `instagram-callback.html` - static Instagram/Meta OAuth bridge.
- `config.js` - local DaveRemixBot callback targets for TikTok and Instagram.
- `.nojekyll` - disables Jekyll processing.

## Configure

If DaveRemixBot runs on the same laptop where you authorize the platform, keep:

```js
localTikTokCallbackUrl: "http://127.0.0.1:5088/integrations/tiktok/oauth/callback",
localInstagramCallbackUrl: "http://127.0.0.1:5088/integrations/instagram/oauth/callback"
```

If DaveRemixBot runs on a private Tailscale server, change both URLs to the private address you open from your browser, for example:

```js
localTikTokCallbackUrl: "http://100.x.y.z:8080/integrations/tiktok/oauth/callback",
localInstagramCallbackUrl: "http://100.x.y.z:8080/integrations/instagram/oauth/callback"
```

The same public origin (scheme + host) is registered in both the TikTok Developer Portal and the Meta Developer Portal as a Valid OAuth Redirect URI. The path differs:

- `https://<github-pages-host>/tiktok-callback.html`
- `https://<github-pages-host>/instagram-callback.html`

Do not put API keys, client secrets, refresh tokens, long-lived tokens, local environment files, database files, or upload files in the GitHub Pages repository.

Start DaveRemixBot before clicking platform authorization. Keep the app bound to `127.0.0.1` or to a private Tailscale address during this flow.
