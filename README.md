# FoldPlay: privacy site

A tiny static site (two HTML files, inline CSS, no scripts, no external fonts) for FoldPlay, the iPhone and iPad app built from [DualDS](https://github.com/bi-creator/DualDS).

- `index.html`: short app page with a link to the privacy policy and the contact email.
- `privacy.html`: the privacy policy (dated 21 November 2026).
- `vercel.json`: `cleanUrls: true`, so `/privacy` serves `privacy.html`.

## Deploy on Vercel

1. In Vercel choose Add New, Project, and import `bi-creator/foldplay-privacy`.
2. Settings:
   - Framework Preset: **Other**
   - Root Directory: the repo root
   - Build Command: leave empty (no build)
   - Output Directory: `.`
   - Install Command: leave empty
3. Deploy.

The privacy policy URL will be `https://<project>.vercel.app/privacy` (replace `<project>` with the domain Vercel gives the project). Open it on a phone first, then paste it into App Store Connect under App Privacy, Privacy Policy URL. The app's About screen links to the same URL (`AppConfiguration.privacyPolicyURL` in the DualDS repo); if Vercel gives a different domain, update it there too.

## Keep in sync

If the app ever adds a permission, network use, analytics, ads, purchases or an account, update `privacy.html` (and its date), the app's `PrivacyInfo.xcprivacy`, and the App Privacy answers in App Store Connect before releasing that version.
