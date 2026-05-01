# Apptime — Static Site

Hosts public pages for RunCalc and CounterSpy iOS apps.

## Pages

- `/` — landing
- `/runcalc.html` — RunCalc privacy + support
- `/counterspy.html` — CounterSpy privacy, terms, support
- `/app-ads.txt` — AdMob authorization (publisher: pub-0328952214359314)

## Deploy

This is a plain static site. To deploy on GitHub Pages:

1. Create a GitHub repo named `<username>.github.io` (e.g. `nlambson.github.io`)
2. Push contents of this directory to the `main` branch
3. Repo Settings → Pages → Source: `main` / `/ (root)` → Save
4. Wait ~60s. Site goes live at `https://<username>.github.io`

## Verify after deploy

```sh
curl -s https://<username>.github.io/app-ads.txt
# expected output (one line):
# google.com, pub-0328952214359314, DIRECT, f08c47fec0942fa0
```

## After deploy

Update App Store Connect for both apps:
- App Information → Marketing URL → `https://<username>.github.io`
- App Information → Privacy Policy URL → `https://<username>.github.io/runcalc.html` (or counterspy.html)
- Save (instant, no Apple review for URL changes)

Then in AdMob → Apps → click "Check for updates" on the verification banner.
