Fastlane placeholder info.

To enable Fastlane signing via App Store Connect API, add the following secrets to GitHub:
- APPSTORE_P8_BASE64 : base64 of the AuthKey_XXXXXX.p8
- APPSTORE_KEY_ID : Key ID of the App Store Connect API key
- APPSTORE_ISSUER_ID : Issuer ID of the App Store Connect API key
- APPLE_TEAM_ID : Your Apple Developer Team ID
- PROVISION_PROFILE_NAME : (optional) Exact provisioning profile name to match bundle id

The workflow contains a Fastlane lane that tries to use the decoded p8 key. You may need to adapt
the Fastfile to use match/sigh or your chosen fastlane flow.
