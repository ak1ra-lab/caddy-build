# caddy-build

A custom [Caddy](https://github.com/caddyserver/caddy) build with ACME DNS-01 challenge modules plugged in. Prebuilt static binaries for `linux/amd64` and `linux/arm64` are available via [GitHub Releases](https://github.com/ak1ra-lab/caddy-build/releases).

## Included modules

- [caddyserver/caddy](https://github.com/caddyserver/caddy) — Caddy v2 core and standard modules
- [caddy-dns/acmedns](https://github.com/caddy-dns/acmedns) — ACME DNS (RFC compliance)
- [caddy-dns/alidns](https://github.com/caddy-dns/alidns) — Alibaba Cloud DNS
- [caddy-dns/cloudflare](https://github.com/caddy-dns/cloudflare) — Cloudflare DNS
- [caddy-dns/tencentcloud](https://github.com/caddy-dns/tencentcloud) — Tencent Cloud DNS

## Build

Manual build:

```sh
CGO_ENABLED=0 go build -trimpath -ldflags="-s -w" -o caddy .
```

Automated build via [GitHub Actions](.github/workflows/build.yml) (manual trigger, `linux/amd64` + `linux/arm64`). Artifacts are uploaded to GitHub Releases with filenames like `caddy_v2.11.4_<sha>_linux_amd64.tar.gz`.
