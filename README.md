# Bloom — Legal site (GitHub Pages)

Static hosting for Bloom's **Privacy Policy**. Terms of Use point to Apple's standard
EULA, so only the privacy policy needs hosting.

Files:
- `index.html` — landing page linking to both documents
- `privacy.html` — the Privacy Policy

## Publish to GitHub Pages

The app expects the policy at:

```
https://filipinius.github.io/bloom-legal/privacy.html
```

To match that URL, create a repo named **`bloom-legal`** under the `filipinius` account
and serve these files from the repo root:

```bash
cd legal-site
git init
git add .
git commit -m "Add Bloom legal pages"
git branch -M main
git remote add origin https://github.com/filipinius/bloom-legal.git
git push -u origin main
```

Then in the repo on GitHub: **Settings → Pages → Build and deployment**
- Source: **Deploy from a branch**
- Branch: **main** / **`/ (root)`** → Save

Pages takes a minute to go live. Verify both URLs load:
- https://filipinius.github.io/bloom-legal/
- https://filipinius.github.io/bloom-legal/privacy.html

## If you use a different repo name or account

Update `BloomConfig.privacyPolicyURL` in `Bloom/Services/BloomConfig.swift` to the new
URL (and the link in `index.html`). The Terms URL (`termsOfUseURL`) is Apple's hosted
EULA and does not change.

## App Store Connect

Enter the same privacy URL in **App Store Connect → App Privacy → Privacy Policy URL**.
The EULA is handled by Apple's standard agreement automatically; only provide a custom
EULA under **App Information → License Agreement** if you replace it.
