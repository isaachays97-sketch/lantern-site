# Lantern — public pages

Three static pages Apple requires before Lantern can be submitted, plus a
landing page.

| File | Used for |
|---|---|
| `privacy.html` | Privacy Policy URL on the App Store listing, AND the privacy link on the in-app paywall |
| `support.html` | Support URL on the App Store listing |
| `index.html` | A landing page, so the root URL isn't a 404 |

## Before publishing

**Replace `lanternbible@gmail.com`** in `privacy.html` and `support.html` with a real
address — two places in each file. Consider a dedicated address rather than a
personal one: it goes on a public page and will be scraped.

## Publishing on GitHub Pages

The Lantern source repo can stay private; these pages need their own public one.

1. Create a new **public** repo, e.g. `lantern-site`
2. Copy these four files into it and push
3. Repo **Settings → Pages** → Source: *Deploy from a branch*, branch `main`, folder `/ (root)`
4. Wait a minute or two, then the URLs are:

```
https://<your-github-username>.github.io/lantern-site/
https://<your-github-username>.github.io/lantern-site/privacy.html
https://<your-github-username>.github.io/lantern-site/support.html
```

## Then

Put those URLs in two places:

1. **`src/config/legal.ts`** in the app — `PRIVACY_URL`, `TERMS_URL`, `SUPPORT_URL`.
   The paywall shows its legal links only once terms and privacy are both set.
2. **App Store Connect** — the listing's Privacy Policy URL and Support URL.

For `TERMS_URL`, Apple's standard EULA is acceptable and needs no page of your
own: `https://www.apple.com/legal/internet-services/itunes/dev/stdeula/`

## Accuracy

`privacy.html` describes Lantern as it actually is: no accounts, no analytics,
nothing leaving the device except Apple's purchase handling and RevenueCat's
subscription check. **If the app ever starts collecting something — analytics,
cloud sync, an account — this page has to change first.** Don't let it drift
into being a document that describes a different app.
