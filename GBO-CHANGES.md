# GBO demo changes

Selects the GBO trust profile, retains the PubEAA fallback mapping and links the locally built GBO ETSI XCFramework. The framework is a generated build input, not tracked source.

Upstream: https://github.com/eu-digital-identity-wallet/eudi-lib-ios-iso18013-security

Pinned upstream base: `f0dee0a497b1fc2bba07652e7d807c274c595882`.

`main` follows upstream; `gbo/main` contains these changes. The source was
previously maintained as a patch in `jeroendk/gbo-wallet-patches`. Existing
licenses and copyright notices are retained. This is a demo profile; it does
not assert EU notification or wallet certification.

Build the KMP GBO source for device and ARM64 simulator and create
`EudiEtsi1196x2.xcframework` in this repository before building the iOS
package. The current preparation/build tooling remains in
`jeroendk/gbo-wallet-patches`. Release artifact publication is a separate step.
