# Abyt Network iOS Wrapper (Capacitor)

This project wraps your PWA in a native iOS shell using Capacitor and includes a GitHub Actions workflow
that builds an .ipa on GitHub's macOS runners. It supports **unsigned** builds out of the box and includes
placeholders for **Fastlane signing automation** (you must add your Apple credentials / App Store Connect API key
as GitHub Secrets to enable signing).

## Quick steps (local / Linux)
1. Clone this repo.
2. Run `npm install`.
3. Push to GitHub (create repo and push).
4. On GitHub, go to **Actions** -> enable workflow run for `main`.
5. The workflow will run on macOS and produce an `.ipa` artifact.

## Important GitHub Secrets (for signing automation)
Add these secrets in your repo Settings → Secrets → Actions to enable automated signing:
- `APPLE_CERT_BASE64` : base64-encoded .p12 signing certificate (optional if using App Store Connect API)
- `APPLE_CERT_PASSWORD` : password for the .p12 (if using APPLE_CERT_BASE64)
- `APPLE_PROVISION_BASE64`: base64-encoded .mobileprovision (optional)
- OR for App Store Connect API (recommended):
  - `APPSTORE_ISSUER_ID`
  - `APPSTORE_KEY_ID`
  - `APPSTORE_P8_BASE64` (base64 of your AuthKey_XXXXX.p8 file)
  - `APPLE_TEAM_ID`

## Notes
- The generated IPA will be available under GitHub Actions → Build iOS IPA → Artifacts → `Abyt-IPA`.
- If you want a fully-signed IPA for TestFlight/App Store, configure the secrets above and follow the comments
  in `.github/workflows/build-ios.yml`.

