# Personal Tunnel

Build repository for the modified iOS VPN client

`personal-tunnel-source.bundle` contains the complete modified source and Git history

Source commit: `422d7fb7e5df64c3cb2f47c0a78f2d922a2840a2`
Bundle SHA-256: `d39b596df7fdbedb32cadedf232262bfbc2e946c41c06508b1a162c4f6debf19`

Recover a source checkout:

```sh
git clone --branch audit/independent-client personal-tunnel-source.bundle source
cd source
git submodule update --init --recursive
```

This revision adjusts native Modern tab-bar placement, server-list motion and startup, TCP/UDP summaries, versioned uTLS fingerprints and supported import formats. Detailed changes and verification limits: `docs/device/2026-10-30-startup-import-motion.md` inside the source checkout

The workflow verifies the bundle hash and exact source commit, runs parser tests, builds the pinned Libbox core, compiles iOS and packages an unsigned IPA. Local static checks passed; this workspace has no Swift/Xcode. Device behavior and the reported private subscription TLS failure remain to be verified. No signing credentials or private subscription URLs are included. The IPA requires valid app and Network Extension signing before installation
