# GBO demo changes

Selects the GBO trust profile, retains the PubEAA fallback mapping and links a GBO ETSI XCFramework release archive with an explicit SwiftPM SHA-256 checksum. The framework is a generated build input, not tracked source.

Upstream: https://github.com/eu-digital-identity-wallet/eudi-lib-ios-iso18013-security

Pinned upstream base: `f0dee0a497b1fc2bba07652e7d807c274c595882`.

`main` follows upstream; `gbo/main` contains these changes. The source was
previously maintained as a patch in `jeroendk/gbo-wallet-patches`. Existing
licenses and copyright notices are retained. This is a demo profile; it does
not assert EU notification or wallet certification.

The default SwiftPM manifest selects the fixed GitHub release URL and checksum
recorded in `GBO-ETSI-ARTIFACT.json`. It does not require an ignored framework
in a consumer's checkout. The release is public and its downloaded archive has been checked against
the pinned checksum.

For unpublished development, explicitly set `GBO_USE_LOCAL_ETSI_FRAMEWORK=1`
and extract the verified archive into this repository, producing
`EudiEtsi1196x2.xcframework`. This opt-in selects the local binary target; it
never changes the default release URL or checksum. The archive contains iPhone
ARM64 and ARM64 simulator slices.

Build/package the KMP revision using `scripts/prepare-etsi-artifact.py` in
`jeroendk/gbo-wallet-patches`. A rebuild can produce different framework bytes;
review and update the SwiftPM checksum together with the artifact metadata.
Publishing source, tags and the release asset requires separate approval.
