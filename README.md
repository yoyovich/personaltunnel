# Personal Tunnel

Build repository for the modified iOS VPN client.

`personal-tunnel-source.bundle` contains the complete modified source and Git history.

Source commit: `1dcf8c8e7124ec8ff8e8483f723fee9132f5c2ff`
Bundle SHA-256: `3f9b2bb617b355d5ab7d16d772b747145ba9bfe1af164a7c61bee5a00077f42a`

Recover a source checkout:

```sh
git clone --branch audit/independent-client personal-tunnel-source.bundle source
cd source
git submodule update --init --recursive
```

This revision updates server-list motion and press bounds, server swipe ping, subscription-scoped ordering, native server field editing, manual connection after server selection, and analytics actions. Detailed changes and verification limits: `docs/device/2026-10-30-server-editing-and-selection.md` in the source checkout.

156 parser/regression tests passed with Swift 6.0.3 in a Linux-adapted isolated copy; changed Swift files passed iOS-targeted syntax parsing. The full parser package requires macOS because its existing Libbox stub uses a Darwin pointer type. No iOS SDK/Xcode or device verification is available locally. The workflow runs parser tests, builds the pinned Libbox core, compiles iOS and packages an unsigned IPA. The IPA requires valid app and Network Extension signing before installation. No private subscription URLs or signing credentials are included.

Import follow-up: multi-node provider/HWID refusal detection, URL-safe VMess Base64 and explicit HTTP(S) proxy links. Evidence and limits: `docs/device/2026-10-30-subscription-hwid-and-formats.md`. The user-authorized diagnostic HWID request returned 36 Xray profiles. Fixed a TLS-fragment byte-range-to-duration conversion defect; the resulting 36-leaf graph passes the checksum-verified pinned Linux core check. Exact Xray fragmentation tuning is adapted to native ClientHello fragmentation with an explicit warning. iOS tunnel connectivity remains unverified.

Modern layout follow-up: full container viewport, actual tab-bar frame alignment, tap/hold actions at the touch point, optional name-side selection, rounded menu animation without safe-area tint, and grouped subscription cards. See `docs/device/2026-10-30-fullscreen-server-menus.md`. Device visual behavior remains to be verified.

Interaction correction: short subscription taps disclose directly; short server taps select without auto-connect; hold anywhere opens a native anchored popover. Compact subscription swipe/header styling and nested analytics edge handoff restored/fixed. See `docs/device/2026-10-30-hold-disclosure-and-pager.md`; iPhone motion and gestures remain to be verified.

Modern follow-up: native tab-bar clearance, light swipe thresholds, window-anchored hold popovers, labeled subscription swipe actions, gray light-mode surfaces and Anywhere-style expanded group structure. Import waits for activation and requires an explicit connect action; local launch display is independent of VPN preference preparation. See `docs/device/2026-10-31-modern-interactions-and-launch.md` in the source bundle. Device behavior and startup timing remain unverified.

Release 1.0.0 (156): isolated subscription disclosure containers with interruptible spring motion and virtualized native swipe rows; lighter analytics return and interruptible page settling. Packaging asserts visible app/extension version metadata. See `docs/device/2026-10-31-isolated-disclosure-release.md`. 146 isolated regression tests passed; per user request the triggered iOS compilation is not monitored.

Disclosure correction 1.0.0 (157): stable inner row snapshots throughout collapse, no nested per-frame table updates, correct hosting-controller containment and continuous group height at settling. 149 isolated tests passed; device crash resolution remains unverified without a native trace/device run. See `docs/device/2026-10-31-disclosure-crash-correction.md`.

Disclosure revision 1.0.0 (158): tap handlers read live persisted expansion state, preventing a cached row from restoring a previously closed group. Fixed-position headers and unified server body cards use bounded 0.24-second reversible frame animation, with no per-frame native table batches. 153 isolated tests passed. See `docs/device/2026-10-31-live-disclosure-and-unified-body.md`. Device rendering and gestures remain unverified; compilation is triggered without completion monitoring per user instruction.

Release polish 1.0.0 (159): first-sample analytics edge handoff, native hold-menu action delivery, Edit/Ping/Delete server swipe and swipe reset on closure. Configuration editor follows the supplied icon/group reference. Darker unified server panels reveal over a fixed native viewport with gradual large-list geometry and ProMotion support. 156 isolated regression tests passed. See `docs/device/2026-10-31-release-polish.md`. Native interaction timing and appearance remain device-unverified; iOS compilation is triggered without monitoring completion under the standing user instruction.
