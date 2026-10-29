# Personal Tunnel

Build repository for the locally modified iOS VPN client.

`personal-tunnel-source.bundle` contains the complete modified source and Git history, not an unmodified upstream import.

Source commit: `cf4edaabd85738357bc373668a157f60e6732d1c`
Bundle SHA-256: `c7bf1762b7ae2957ab5a1c7e15c48bff89f192d055986e9a77d68d2bbb7a6c03`

Recover a normal source checkout:

```sh
git clone --branch audit/independent-client personal-tunnel-source.bundle source
cd source
git submodule update --init --recursive
```

The build workflow verifies the bundle hash and exact source commit before compiling. No signing credentials or server credentials are uploaded. The resulting IPA is unsigned and requires valid app/Network Extension signing before installation. See REPORT.md inside the source checkout for unresolved verification items.
