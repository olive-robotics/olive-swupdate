# Source provenance and release scope

Prepared on 2026-11-24.

## Version and origin

- Upstream project: https://github.com/sbabic/swupdate
- Advertised Makefile version: **2022.05.0**.
- Identified upstream snapshot: `d3bab1ebd3c1ab51e740a963489bbe9af26c4474`
  (2022-08-15, `delta_handler: fix SINGLE_RANGE handling`).
- The original `2022.05` tag resolves to
  `d542b7fa7c8b7ddb75e7cb3335f5a2590df2edab`. This release includes later
  upstream changes and must not be identified as an unchanged tag snapshot.

The reviewed ARM32, olixRobot ARM64 and olixSense ARM64 payloads contain
identical SWUpdate source and configuration. Of the 359 files in the
identified upstream snapshot, 345 match the payload copies byte-for-byte.
One C implementation file differs: `core/util.c` includes the free-space
arithmetic fix preserved here and recorded in `olive/patches/`.
Four optional web frontend files also differ in the payloads.
Nine upstream metadata/acceptance-test files are absent from those payloads;
this repository restores them from the identified upstream snapshot.

## What is included

The complete identified upstream source snapshot, original notices and
license texts, the matching locally modified C implementation, and the
configuration shared by the three reviewed payloads are included.
`SOURCE_MANIFEST.json` identifies file origins and source comparisons;
`SHA256SUMS` provides file integrity checks.

The repository retains SWUpdate's mixed upstream licensing, including its
GPL, LGPL, permissively licensed dependencies and documentation/assets.
It does not relicense every file as GPL. See `COPYING`, `LICENSES/`,
`.reuse/dep5`, and individual file notices.

## Exclusions and limits

No signing keys, certificates, customer update images, compiled payload
binaries, generated compiler outputs, private build logs, runtime
credentials, device trees, or private repository history were copied.
The separately customized optional MIT web frontend and Olive artwork are
not part of this publication; original upstream frontend files are retained.
This repository therefore does not reproduce the Olive-branded web page.

Source/configuration comparisons are not a byte-for-byte reconstruction of
historical binaries or proof of what accompanied every past shipment.
External libraries and toolchains are separate dependencies.
See `olive/BUILDING.md` for the scope of build validation.
