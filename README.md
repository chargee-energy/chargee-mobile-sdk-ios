# Chargee Mobile SDK — iOS

The Chargee Mobile SDK for iOS, distributed as a Swift package.

The SDK itself is closed-source. This repository holds only what a release produces: the
`Package.swift` manifest and a thin Swift shim, with the compiled `Chargee.xcframework` attached to
each release as a binary asset. Both are generated and committed by CI — nothing here is written by
hand, and an edit will be overwritten by the next release.

## Installation

In Xcode, choose **File → Add Package Dependencies** and enter this repository's URL, or add it to a
`Package.swift`:

```swift
dependencies: [
    .package(url: "https://github.com/chargee-energy/chargee-mobile-sdk-ios", from: "0.0.20")
]
```

Then depend on the `Chargee` product:

```swift
.target(name: "YourApp", dependencies: [
    .product(name: "Chargee", package: "chargee-mobile-sdk-ios")
])
```

And import it:

```swift
import Chargee
```

Resolving the package also pulls in
[`ESPProvisionWrapper`](https://github.com/chargee-energy/ESPProvisionWrapper), which supplies the
Wi-Fi provisioning symbols the framework leaves undefined. SwiftPM fetches it for you; nothing needs
declaring.

## Requirements

| | |
|---|---|
| Platform | iOS 15.0 or later |
| Architectures | Device (arm64) and simulator (arm64, x86_64) |

## What a release contains

Each tag (`vX.Y.Z`) carries one asset, `Chargee.xcframework.zip`, the compiled XCFramework. The
manifest's binary target pins it by URL and SHA-256, so a tag always resolves to exactly the binary
that was built for it. The manifest is committed before the tag is created — the tag points at the
commit holding the matching `Package.swift`, which is what SwiftPM resolves.

## CocoaPods

CocoaPods was the distribution channel through 0.0.19 and is no longer published. Existing Podfiles
continue to resolve the versions already on the
[CocoaPods Trunk](https://cocoapods.org/pods/Chargee), but new versions ship only as a Swift
package.

## License

The Chargee SDK is distributed under the [Chargee SDK License](https://chargee.energy/sdk-license/v1).

## Support

[chargee.energy](https://chargee.energy)
