# Personal Tunnel

Build repository for the modified iOS VPN client.

`personal-tunnel-source.bundle` contains the complete modified source and Git history.

Source commit: `b1f883134b8888f98f9f614800b9ff617433634b`
Bundle SHA-256: `abc6819815ba5cc052fb9a34c0516c30c9b7876e9f1470f92a3d54e690be4620`

Recover a source checkout:

```sh
git clone --branch audit/independent-client personal-tunnel-source.bundle source
cd source
git submodule update --init --recursive
```

This revision updates server-list motion and press bounds, server swipe ping, subscription-scoped ordering, native server field editing, manual connection after server selection, and analytics actions. Detailed changes and verification limits: `docs/device/2026-10-30-server-editing-and-selection.md` in the source checkout.

139 parser/regression tests passed with Swift 6.0.3 in a Linux-adapted isolated copy; changed Swift files passed iOS-targeted syntax parsing. The full parser package requires macOS because its existing Libbox stub uses a Darwin pointer type. No iOS SDK/Xcode or device verification is available locally. The workflow runs parser tests, builds the pinned Libbox core, compiles iOS and packages an unsigned IPA. The IPA requires valid app and Network Extension signing before installation. No private subscription URLs or signing credentials are included.

Import follow-up: multi-node provider/HWID refusal detection, URL-safe VMess Base64 and explicit HTTP(S) proxy links. Evidence and limits: `docs/device/2026-10-30-subscription-hwid-and-formats.md`. The user-authorized diagnostic HWID request returned 36 Xray profiles. Fixed a TLS-fragment byte-range-to-duration conversion defect; the resulting 36-leaf graph passes the checksum-verified pinned Linux core check. Exact Xray fragmentation tuning is adapted to native ClientHello fragmentation with an explicit warning. iOS tunnel connectivity remains unverified.

Modern layout follow-up: full container viewport, actual tab-bar frame alignment, tap/hold actions at the touch point, optional name-side selection, rounded menu animation without safe-area tint, and grouped subscription cards. See `docs/device/2026-10-30-fullscreen-server-menus.md`. Device visual behavior remains to be verified.
