# Preview Release Status

AtlasCraft (formerly AtlasWorlds Minecraft) 0.1.0-preview.9 is an early Windows x64 desktop preview,
not a stable release or security certification. The exact published ZIP, checksum,
automated-check results, and known limitations are recorded in its release notes.

The repository has been renamed to `RetroGooby/AtlasCraft`; the private multi-game
hub now uses `RetroGooby/AtlasWorlds`. Previously verified preview ZIPs are unchanged,
including their executable, legacy branding, bundled guides, and checksums. Use
this repository's current guide and links rather than the old bundled GitHub URLs.
No server data paths have been migrated or renamed.

## Release Checks

The publishing process checks the following before making a download public:

- Full-hub regression tests run separately against shared development source. The
  standalone is built from an isolated staging tree, not a live installation.
- Minecraft backend and standalone interface tests run against that staged tree.
- The frozen executable is inspected for excluded AzerothCore, WoW, Palworld,
  database, and remote-agent backends. Unsupported integration boundaries fail
  closed instead of loading another game's implementation.
- Every packaged file is covered by a size/hash manifest. Private configuration,
  known personal identifiers, server/world files, links, and proprietary plain-text
  source are rejected. Unreviewed branding assets are not included.
- Bundled dependency versions and license texts are inventoried. Exact unmodified
  certifi source is provided separately under its own MPL terms; AtlasWorlds-owned
  application source remains private. The custom application license is not a
  claim of professional legal review.
- Runtime downloads used for the build have recorded provenance. The build uses
  a separate maintained Python environment instead of replacing the hub's Python.
- An offline packaged-app check uses temporary data to exercise first run, setup
  and import dialogs, ZIP/JAR choices, unchecked consent, verified settings saves,
  profile isolation, runtime imports, and game isolation. No game server is started.
- The same ZIP is checked on an independent hosted Windows runner with Python
  and Java removed from the application's PATH and no application data or library
  installation copied from the developer's machine.
- The download has a SHA-256 checksum and is uploaded as a GitHub prerelease.

## Limits Of These Checks

For preview9, the full regression suite ran 543 tests and the staged Minecraft
suite ran 373 tests, with no failures or errors and one skipped test in each.
Targeted tests cover backed-up settings changes, independent server controls,
draft preservation, and safely reusing a removed managed server's folder while
keeping its verified world archive. Active duplicate and other-game roots remain
protected. The release-validation asset records exact package and hosted results.

Concurrent-control tests used isolated protocol/console stub servers, not two
real modpack play sessions. The vanilla 1.21.1 JAR inspection used an official
download with verified metadata; that JAR was not executed for the release check.

Automated fixture tests are not a real play session with every modpack. This
packaging preview does not establish a comprehensive live-server acceptance matrix
or guarantee recovery after every combination of filesystem, mod, and pack failure.
Keep independent backups and verify your own server after importing or updating.

The hosted check does not claim that the runner has no development tools installed;
it removes them from the application's environment and installs no app dependencies.
This checks application portability, not all Windows editions, display drivers,
antivirus products, network environments, or modpack launchers.

The executable is unsigned. Checksums are not digital signatures. Do not disable
security software or bypass an untrusted-download warning to run an unknown copy.
The source and dependency checks are not a professional penetration test or a
guarantee that no undiscovered vulnerability exists.

## Distribution Boundaries

This repository contains documentation, issue templates, and release-check
automation, not the proprietary application source or its development history.
Packaged applications are separate release assets. No private hub installation,
live configuration, credentials, game server, modpack, world, or backup is included.

An application binary is not a confidentiality guarantee: packaged code may be
inspectable or recoverable. Keeping source out of the repository is a distribution
choice, not technical protection against reverse engineering.
