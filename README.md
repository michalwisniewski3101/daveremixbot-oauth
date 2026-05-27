# DaveRemixBot GitHub Pages OAuth Bridge

This folder is a static GitHub Pages site for TikTok OAuth.

It contains no secrets and no server-side code. TikTok redirects to `tiktok-callback.html`, and the browser forwards the OAuth query string to the private local DaveRemixBot callback.

Treat the callback URL as sensitive while OAuth is in progress. Do not paste full callback URLs with `code` or `state` into chats, logs, screenshots, or issue trackers.

## Files

- `index.html` - public app information page.
- `terms.html` - public Terms of Service page.
- `privacy.html` - public Privacy Policy page.
- `tiktok-callback.html` - static OAuth bridge.
- `config.js` - local DaveRemixBot callback target.
- `.nojekyll` - disables Jekyll processing.

## Configure

If DaveRemixBot runs on the same laptop where you authorize TikTok, keep:

```js
localTikTokCallbackUrl: "http://127.0.0.1:5088/integrations/tiktok/oauth/callback"
```

If DaveRemixBot runs on a private Tailscale server, change it to the private URL you open from your browser, for example:

```js
localTikTokCallbackUrl: "http://100.x.y.z:8080/integrations/tiktok/oauth/callback"
```

Do not put API keys, client secrets, refresh tokens, local environment files, database files, or upload files in the GitHub Pages repository.

Start DaveRemixBot before clicking TikTok authorization. Keep the app bound to `127.0.0.1` or to a private Tailscale address during this flow.
