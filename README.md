# Personal Tunnel

Build repository for the locally modified iOS VPN client.

`personal-tunnel-source.bundle` contains the complete modified source and Git history, not an unmodified upstream import.

Source commit: `e95226fe38a4f1daf5ce39c6126776477717dd70`
Bundle SHA-256: `ce84a770d4d25adbb267c63315c5cfc1376003129272c46c3bf8c66172993cb4`

Recover a normal source checkout:

```sh
git clone --branch audit/independent-client personal-tunnel-source.bundle source
cd source
git submodule update --init --recursive
```

The build workflow verifies the bundle hash and exact source commit before compiling. No signing credentials or server credentials are uploaded. The resulting IPA is unsigned and requires valid app/Network Extension signing before installation. See REPORT.md inside the source checkout for unresolved verification items.
