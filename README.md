# Personal Tunnel

Build repository for the locally modified iOS VPN client.

`personal-tunnel-source.bundle` contains the complete modified source and Git history, not an unmodified upstream import.

Source commit: `d5040cd873c085a0a52bbb3a5d48b2d40dad6d9f`
Bundle SHA-256: `7d26f223b8e675bcf1b5f08d25d2e96e6d27a8708baa06843f8c34ab2eef616e`

Recover a normal source checkout:

```sh
git clone --branch audit/independent-client personal-tunnel-source.bundle source
cd source
git submodule update --init --recursive
```

The build workflow verifies the bundle hash and exact source commit before compiling. No signing credentials or server credentials are uploaded. The resulting IPA is unsigned and requires valid app/Network Extension signing before installation. See REPORT.md inside the source checkout for unresolved verification items.
