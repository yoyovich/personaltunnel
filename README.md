# Personal Tunnel

Build repository for the modified iOS VPN client.

`personal-tunnel-source.bundle` contains the complete modified source and Git history.

Source commit: `7709876ad02ea2681e24da2974f251964d459013`
Bundle SHA-256: `38ee0799b8eaf35205a71d79912f47bb979b069bce5cafdf9c26f88f97eed50d`

Recover a source checkout:

```sh
git clone --branch audit/independent-client personal-tunnel-source.bundle source
cd source
git submodule update --init --recursive
```

This revision updates server-list motion and press bounds, server swipe ping, subscription-scoped ordering, native server field editing, manual connection after server selection, and analytics actions. Detailed changes and verification limits: `docs/device/2026-10-30-server-editing-and-selection.md` in the source checkout.

157 parser/regression tests passed with Swift 6.0.3 in a Linux-adapted isolated copy; changed Swift files passed iOS-targeted syntax parsing. The full parser package requires macOS because its existing Libbox stub uses a Darwin pointer type. No iOS SDK/Xcode or device verification is available locally. The workflow runs parser tests, builds the pinned Libbox core, compiles iOS and packages an unsigned IPA. The IPA requires valid app and Network Extension signing before installation. No private subscription URLs or signing credentials are included.

Import follow-up: multi-node provider/HWID refusal detection, URL-safe VMess Base64 and explicit HTTP(S) proxy links. Evidence and limits: `docs/device/2026-10-30-subscription-hwid-and-formats.md`. The user-authorized diagnostic HWID request returned 36 Xray profiles. Fixed a TLS-fragment byte-range-to-duration conversion defect; the resulting 36-leaf graph passes the checksum-verified pinned Linux core check. Exact Xray fragmentation tuning is adapted to native ClientHello fragmentation with an explicit warning. iOS tunnel connectivity remains unverified.

Modern layout follow-up: full container viewport, actual tab-bar frame alignment, tap/hold actions at the touch point, optional name-side selection, rounded menu animation without safe-area tint, and grouped subscription cards. See `docs/device/2026-10-30-fullscreen-server-menus.md`. Device visual behavior remains to be verified.

Interaction correction: short subscription taps disclose directly; short server taps select without auto-connect; hold anywhere opens a native anchored popover. Compact subscription swipe/header styling and nested analytics edge handoff restored/fixed. See `docs/device/2026-10-30-hold-disclosure-and-pager.md`; iPhone motion and gestures remain to be verified.

Modern follow-up: native tab-bar clearance, light swipe thresholds, window-anchored hold popovers, labeled subscription swipe actions, gray light-mode surfaces and Anywhere-style expanded group structure. Import waits for activation and requires an explicit connect action; local launch display is independent of VPN preference preparation. See `docs/device/2026-10-31-modern-interactions-and-launch.md` in the source bundle. Device behavior and startup timing remain unverified.

Release 1.0.0 (156): isolated subscription disclosure containers with interruptible spring motion and virtualized native swipe rows; lighter analytics return and interruptible page settling. Packaging asserts visible app/extension version metadata. See `docs/device/2026-10-31-isolated-disclosure-release.md`. 146 isolated regression tests passed; per user request the triggered iOS compilation is not monitored.

Disclosure correction 1.0.0 (157): stable inner row snapshots throughout collapse, no nested per-frame table updates, correct hosting-controller containment and continuous group height at settling. 149 isolated tests passed; device crash resolution remains unverified without a native trace/device run. See `docs/device/2026-10-31-disclosure-crash-correction.md`.

Disclosure revision 1.0.0 (158): tap handlers read live persisted expansion state, preventing a cached row from restoring a previously closed group. Fixed-position headers and unified server body cards use bounded 0.24-second reversible frame animation, with no per-frame native table batches. 153 isolated tests passed. See `docs/device/2026-10-31-live-disclosure-and-unified-body.md`. Device rendering and gestures remain unverified; compilation is triggered without completion monitoring per user instruction.

Release polish 1.0.0 (159): first-sample analytics edge handoff, native hold-menu action delivery, Edit/Ping/Delete server swipe and swipe reset on closure. Configuration editor follows the supplied icon/group reference. Darker unified server panels reveal over a fixed native viewport with gradual large-list geometry and ProMotion support. 156 isolated regression tests passed. See `docs/device/2026-10-31-release-polish.md`. Native interaction timing and appearance remain device-unverified; iOS compilation is triggered without monitoring completion under the standing user instruction.

Release correction 1.0.0 (160): analytics return pins child content without cancelling its pan, removes the initial recognition-slop jump and uses stable snapshot rendering during interactive movement. Lighter expanded server panels and a row-scoped tap target on the existing ping/timeout value recheck only that node. 158 isolated regression tests passed. See `docs/device/2026-10-31-analytics-drag-and-ping-tap.md`. Actual iPhone gestures/rendering and hit targets remain device-unverified; compilation is triggered without completion monitoring under the standing user instruction.

Release refinement 1.0.0 (161): native dismissal-start notification clears the held-row tint independently of menu content/action lifetime. Disclosure keeps the small-group 0.24-second timing and gradually lengthens to roughly 0.7 seconds for 30 servers and 1 second for 100+, with immediate reversal. 161 isolated regression tests passed. See `docs/device/2026-10-31-menu-highlight-and-large-group-timing.md`. Native timing remains device-unverified; compilation is triggered without monitoring completion under the standing user instruction.

Release 1.0.1 (162): physical viewport-prefix disclosure replaces count-dependent full-height curves. Participating surfaces and native viewports remain stable during motion; anchored completion, reversal and structural-update guards preserve input geometry. Both actual pager hosts now stay fixed while snapshot pages move, with nested content locked until settling. Semantic release metadata is authoritative in `release-version.json`; `scripts/release_version.py` prepares patch/minor releases and validates every app/extension Info.plist. 157 Swift regression tests and 5 release-tool tests passed. See `docs/device/2026-10-31-motion-rebuild-101.md` and `docs/RELEASING.md`. Device animation/gesture verification is still required; iOS compilation is triggered without completion monitoring under the standing user instruction.

Release 1.0.2 (163): live page rendering replaces snapshot transitions; compact swipe icons, unified expanded subscription backing and direct single-server rows. See `docs/device/2026-10-31-live-pages-and-unified-subscriptions.md`. iPhone interaction/rendering remains unverified.

Release 1.0.3 (164): fixed-width disclosure content, immediate deferred live-page updates, scalar pager motion, standalone ping/pinning/deletion, selected-row cache correction and safe traffic-counter conversion. 162 isolated Swift regression tests and 5 version-tool tests passed; changed UI files passed iOS-targeted syntax parsing. See `docs/device/2026-10-31-regression-audit-103.md`. Native iPhone behavior remains unverified; compilation is triggered without completion monitoring under the standing user instruction.

Release 1.0.4 (165): targeted server swipe footprint matching with subscription contextual actions preserved, stable analytics viewport/scroll insets during live paging, and a continuous last-corner-height blend on disclosure collapse. Disclosure timing and final style remain unchanged. 166 isolated Swift regression tests and 5 release-tool tests passed; changed UI files passed iOS-targeted syntax parsing. See `docs/device/2026-10-31-targeted-animation-fixes-104.md`. Native visual/gesture matching requires device verification; compilation is triggered without completion monitoring under the standing user instruction.

Release 1.0.5 (166): fixes the missing UIView gestureRecognizerShouldBegin override diagnosed from the failed native 1.0.4 build artifact. Release metadata validated; compilation retriggered without completion monitoring.
