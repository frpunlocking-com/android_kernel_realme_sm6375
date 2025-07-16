# Changelog

All notable changes to this project are documented in this file. Note: Pre-release versions (Alpha and Beta builds prior to v1.0.0) are marked as pre-release on GitHub and listed separately below.

## v3.0.0

### Added
- Merged KernelSU‑Next v1.0.9 root‑management updates.

### Changed
- Disabled Realme UI bootloader fingerprint spoofing; devices now report their true build fingerprint.
- Now Yuri Keybox support for hardware‑backed Google Play Integrity (Strong) attestation.

### Fixed
- Resolved Luna FRP “farm fingerprint” mismatch error. 
- Devices now pass SafetyNet/Play Integrity checks on Luigi & Oscar families.

## v2.0.0

### Added

- Support for Realme: 9 Pro 5G / 9 5G / Q5 (codename "oscar") in addition to Realme 10 Pro 5G (codename "luigi").

### Fixed

- IMEI number now displays correctly (fixed IMEI showing as 0 by switching to KSUN `v1.0.8` tag from feature `Next`).
- Resolved 5G network and general connectivity issues.
- Fixed `Makefile` configuration issues in the build due to spoofing fingerprint.

## v1.0.0

### Added

- Included the [Yuri Keybox](https://github.com/dpejoh/yurikey/releases/) suggestion to enable passing Google Play Strong Integrity checks (with latest Play Services and Vending).

### Changed

- Updated build fingerprint to final release identifier ("Luna").

### Fixed

- Bypassed native detection in system apps by injecting into the Zygote process using kprobes (now passes Native Detector v7.20 checks).
- Fixed various device tree configuration issues in the build.

## v20250624 – Beta V3 (Pre-release)

### Changed

- Updated build fingerprint to Beta release version.

## v20250623 – Alpha V2 (Pre-release)

### Changed
- Updated build fingerprint to Alpha V2 release version.

## v20250621 – Alpha (Initial Pre-release)

### Added

- Initial support for Realme 10 Pro 5G (codename "luigi").
- KSUN Next in feature `Next` branch.
- Suggested TSupport Advanced for Keybox and Tricky Store / Addon to pass Google Play Strong Integrity checks.
