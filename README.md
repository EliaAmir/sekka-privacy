# sekka-privacy

Hosts the privacy policy for the Sekka Android app, served at https://eliaamir.github.io/sekka-privacy/

This is the **legacy URL**. Released app versions and the Google Play listing
link here, so this page must keep serving the complete policy — not a
redirect — for as long as any shipped build still points at it. The
canonical copy now lives at https://sekka-eg.com/privacy/ (repo:
`sekka-eg-website`), and this page carries a `<link rel="canonical">` to it
plus a small banner saying so.

## Keep in sync

This policy exists in two places:

- `index.html` in this repo (legacy URL, kept alive for old app builds)
- `privacy/index.html` in the `sekka-eg-website` repo (canonical URL)

Any change to the policy text — what's collected, why, retention, contact —
**must land in both pages in the same sitting**, with the same "last
updated" date. Never edit one without the other.

After editing, run the sync checker from `sekka-eg-website` (it diffs the
visible policy text of both pages and fails on any drift):

```
cd ../sekka-eg-website
python3 scripts/check_privacy_sync.py
```

Update `kPrivacyPolicyUrl` in the Sekka app (`lib/config/links.dart`) only
once every shipped build is expected to have moved past this URL — until
then, this page stays live.
