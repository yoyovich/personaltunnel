# Personal Tunnel — particle transition preview

This preview contains all native server interaction and analytics changes from source `77b5e2b`,
plus the Modern Connection/Analytics particle transition and its appearance toggle.

Source commit: `c36876ff9b62beb5329e7b8f304e1392596baf4e`

Bundle SHA-256: `1f78d3c4bd513d9a54a8dcb3f8fea833869af228d5b1a363b8cdb551848d8901`

Recover the exact modified source:

```sh
git clone --branch audit/independent-client personal-tunnel-source.bundle source
cd source
git submodule update --init --recursive
```

The existing workflow checks the bundle hash and source commit, runs parser/geometry tests,
compiles iOS and packages an unsigned IPA. A valid app/Network Extension signature is required
before installation. No signing credentials or server credentials are included.

The native server UI build on main is separate from this preview. On-device animation performance
and screenshot fidelity still need verification. Read PARTICLE_PAGE_TRANSITION.md in the source
for rendering limits, accessibility fallbacks and device checks.
