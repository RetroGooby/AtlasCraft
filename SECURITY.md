# Security And Privacy

## Reporting A Vulnerability

Do not post exploit details, passwords, tokens, or private server files in a public
issue. Use GitHub's private reporting channel:
[Report a vulnerability](https://github.com/RetroGooby/AtlasWorlds/security/advisories/new).

Private vulnerability reporting is enabled for this repository. If the form is
unavailable, open an issue asking the maintainer for a private contact route,
without vulnerability details or attachments. Do not guess an email address or
send secrets to an unverified account.

## What Not To Upload

Do not publish `.env`, application configuration or registry files,
`server.properties`, worlds, backups, player lists, full logs, or unreviewed
diagnostic archives. Exact settings backups can contain RCON passwords.
Sanitize small excerpts and screenshots before sharing them. Remove account
names, personal paths, addresses, API keys, DNS tokens, and passwords.

Rotate exposed credentials immediately. Removing a visible file does not remove
copies, history, or revoke the credential.

## Local Software And Networking

Server packs, mods, installers, and launch scripts are executable software.
Install only content you trust. Compatibility checks are not a malware scanner
or sandbox. Backups do not guarantee recovery; keep independent world copies.

Forward only the intended game port, never RCON. A local RCON client does not
prove its server listener is loopback-only; check firewall exposure. DuckDNS is
DNS, not a tunnel, and does not hide the public address.

Online searches and downloads contact their providers. Public-IP discovery uses
ipify; authorized DNS updates contact DuckDNS. These services receive normal
connection metadata. The standalone does not automatically upload diagnostics.

This is preview software, not a completed security audit. Public-release
verification is tracked in [release status](docs/RELEASE_STATUS.md).
