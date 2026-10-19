# Release Status

The first public Minecraft standalone preview is being prepared. This repository
currently distributes documentation, not an application. There is no stable
release claim and no public binary has been certified for publication.

## Before The First Download

- Narrow the standalone package to its required components. The current local
  preview still bundles unused hub/other-game framework modules; that package is
  not the intended public release artifact.
- Review the exact application payload for credentials, personal data, private
  configuration, local server files, and unintended bundled assets or modules.
- Review dependency and asset redistribution licenses and include their required
  notices. The proprietary application terms do not replace third-party licenses.
- Review the custom free-to-use license before distribution; it is not a claim
  of professional legal review.
- Test the complete packaged application on a clean Windows system without
  developer Python, Java, PATH entries, caches, or an existing configuration.
- Verify create/import, readiness, graceful shutdown, backup/restore, protected
  pack update/rollback, mod changes, friends' ZIPs, and archive/removal workflows.
- Test interrupted downloads, invalid archives, denied writes, low disk space,
  insufficient memory, failed startup, and recovery after interruption.
- Verify interface layout at supported display sizes and scaling.
- Establish and test private vulnerability reporting and a repeatable release
  validation process.
- Record the version, known limitations, archive checksum, and exact artifact
  tested. Upload deliberately through Releases, never from a development folder.

## Distribution Boundaries

Only reviewed documentation and issue templates belong in the public Git tree.
Official packaged applications will be separate release assets. The source
checkout, build history, private hub, other-game code, live configuration,
credentials, servers, mods, worlds, and backups must not be copied into this
repository.

An application binary is not a confidentiality guarantee: packaged code may be
inspectable or recoverable. Keeping source out of the repository is a distribution
choice, not technical protection against reverse engineering.

The first download will be marked as a preview with its tested scope and known
limitations. A successful local test or a file-hash manifest alone is not a
clean-machine acceptance test, digital signature, or guarantee against data loss.
