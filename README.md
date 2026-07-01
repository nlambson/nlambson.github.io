# Apptime — Static Site

Public Privacy / Terms of Use / Support pages for Nathan Lambson's iOS apps.
Hosted on GitHub Pages at `https://nlambson.github.io`.

## Pages

Each app has one flat page that serves as its Privacy Policy **and** Terms of Use **and**
Support page (with `#privacy`, `#terms`, `#support` anchors). Use these URLs in App Store Connect.

| App           | URL                                       |
|---------------|-------------------------------------------|
| Sol           | `/sol.html`                               |
| OnThree       | `/onthree.html`                           |
| TidyScan      | `/tidyscan.html`                          |
| RunCalc       | `/runcalc.html`                           |
| CounterSpy    | `/counterspy.html`                        |
| Resync        | `/resync.html`                            |
| Elite Career  | `/haos.html`                              |

Legacy directory URLs still resolve (they redirect to the flat pages so already-shipped
app builds don't break):

- `/tidyscan/privacy.html` → `/tidyscan.html`
- `/resync/privacy` → `/resync.html`

Other files:

- `/` — landing page listing all apps
- `/style.css` — shared styles
- `/404.html` — not-found page
- `/app-ads.txt` — AdMob authorization (publisher: pub-0328952214359314)

## Deploy

Plain static site. Push to `main`; GitHub Pages redeploys in ~60s.

1. Repo Settings → Pages → Source: `main` / `/ (root)`
2. Wait ~60s. Live at `https://nlambson.github.io`

## Verify after deploy

```sh
for p in sol onthree tidyscan runcalc counterspy resync haos; do
  printf "%-12s " "$p"; curl -s -o /dev/null -w "%{http_code}\n" "https://nlambson.github.io/$p.html"
done
# all should print 200
```

## App Store Connect

For each app, set both URLs to that app's page:

- App Information → Privacy Policy URL → `https://nlambson.github.io/<app>.html`
- App Information → Support URL → `https://nlambson.github.io/<app>.html`
- Marketing URL (optional) → `https://nlambson.github.io`

URL changes are instant and need no Apple review.
