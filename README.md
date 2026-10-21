# AtlasCraft

A Windows desktop hub for Minecraft Java Edition servers. Formerly named
**AtlasWorlds Minecraft**, AtlasCraft lets you import an existing
server, create one from a server-pack ZIP or dedicated server JAR, manage compatible mods, and update packs
with backups and rollback protection.

**Minecraft standalone preview: 0.1.0-preview.10.**
Get the Windows application ZIP from
[Releases](https://github.com/RetroGooby/AtlasCraft/releases).
Read the release notes and [tested scope](docs/RELEASE_STATUS.md) before using it.

This repository contains public documentation and issue tracking. AtlasCraft is
free to use, but its application source is proprietary and is not published here.

**Naming transition:** the current preview download is still named
`AtlasWorldsMinecraft`, including its executable, window title, license, and data
folders. These names are retained for compatibility; do not rename your data
folders or recreate servers. Older bundled guides may link to the former
repository address; use the links in this repository instead. **AtlasWorlds** is
now the separate multi-game server hub, whose repository remains private.

## What It Does

- **Create from ZIP:** inspect a dedicated server pack, detect supported Minecraft,
  loader, and Java requirements, then prepare and start a separate server folder.
- **Create from JAR:** inspect a dedicated server JAR, detect supported Java
  requirements, and copy it into a new isolated server folder.
- **Import without recreating:** register a stopped existing server in place,
  preserving its worlds, settings, mods, and launch files.
- **Manage mods:** scan installed JARs, search Modrinth or CurseForge, inspect
  dependencies, and apply backed-up additions, updates, or removals.
- **Share client additions:** export a friends' ZIP describing the managed mod
  changes. Friends still need the matching base modpack and loader.
- **Update packs:** prepare a newer server-pack ZIP separately, back up the
  existing installation, preserve supported user settings and worlds, and retain
  a rollback path.
- **Run your server:** start and stop, view logs, copy join addresses, manage
  backups, and configure optional maintenance schedules.
- **Run multiple servers:** use Running Servers for independent controls and
  separate logs, with memory, port, and folder checks before starting.
- **Reuse freed ports:** newly created servers reuse the lowest available port;
  archived registrations no longer keep game/RCON ports reserved forever.
- **Manage players and gameplay:** use supported local RCON controls for player
  lists, OP status, kicks, bans, whitelist actions, and live settings. Other
  settings, including global PvP, require a clean stop and restart.
- **Save server settings:** back up and verify supported settings changes, with
  a confirmed clean stop and restart of only the selected controlled server.
- **Keep a world archive:** archive a server before removing its registration.
  Imported server folders are not deleted by the removal workflow.

## Get Started

Read the [Getting Started guide](docs/GETTING_STARTED.md) for installation,
new-server setup, import, updates, and friends joining.

The standalone has its own application data. It does not automatically adopt an
existing multi-game AtlasWorlds hub configuration. Minecraft folders must be
imported explicitly; this edition does not manage World of Warcraft or other games.

## Requirements And Limits

- **Platform:** Windows x64 desktop.
- **Resources:** enough available memory and disk space for your chosen pack,
  Windows, backups, and any client or other servers running on the same computer.
- **Internet:** required for runtime/loader downloads and online mod searches.
- **Packs:** supported Forge, NeoForge, Fabric, and direct dedicated-server JAR
  layouts. Not every ZIP or custom installer is supported. Compatibility checks
  explain detected requirements and block unsupported or ambiguous setups.
- **Existing-server imports:** matching Java must already be available. Import
  does not download Java or replay arbitrary launcher scripts.
- **CurseForge:** requires your own API key. No key is bundled. Provider rules or
  unavailable download metadata may require manual downloads.
- **Networking:** public join addresses and optional DuckDNS are not tunnels.
  Router forwarding and firewall configuration are still your responsibility.

This is preview software. Keep independent backups and test changes before
inviting players back. Dependency checks cannot guarantee that every combination
of mods is compatible. See [release status](docs/RELEASE_STATUS.md).

## Help And Feedback

Use [Issues](https://github.com/RetroGooby/AtlasCraft/issues) for reproducible bugs,
unsupported pack layouts, and feature suggestions. Include the application,
Minecraft, loader, and pack versions, plus a short sanitized log excerpt.

**Do not upload worlds, full configuration files, passwords, API keys, DNS tokens,
player details, or unreviewed diagnostic archives.** Read the
[security and privacy guidance](SECURITY.md) before reporting a problem.

## Support Development

AtlasCraft is free to use. Donations are entirely optional and do not unlock
features or provide a different application license.

[Support AtlasCraft on PayPal](https://www.paypal.com/donate/?hosted_button_id=8WCSEHZGTJGEQ)

## License And Credits

Created by **RetroGooby**. See [LICENSE.txt](LICENSE.txt) for the free-to-use,
proprietary application terms. Third-party components retain their own licenses;
required notices must accompany the application download.

AtlasCraft is an independent community tool. It is not an official Minecraft
product and is not approved by or associated with Mojang or Microsoft. Game names
and trademarks belong to their respective owners. No game, modpack, Java runtime,
world, or account credential is distributed in this documentation repository.
