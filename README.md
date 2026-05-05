# Chargee Mobile SDK — iOS Binaries

Binary releases of the Chargee Mobile SDK for iOS.

The SDK source is closed-source; this repository hosts only the compiled `Chargee.xcframework` and accompanying podspec for each release.

## Installation

Add to your `Podfile`:

```ruby
pod 'Chargee', '~> 0.0.3'
```

Then run `pod install`.

## Release contents

Each release tag (`vX.Y.Z`) ships two assets:

- `Chargee.xcframework.zip` — the compiled XCFramework, referenced by the podspec's `spec.source`.
- `Chargee.podspec` — the podspec for that version.

The podspec is also published to the [public CocoaPods Trunk](https://cocoapods.org/pods/Chargee), so the `pod 'Chargee'` snippet above resolves without adding this repository as a custom Podfile source.

## License

The Chargee SDK is distributed under the [Chargee SDK License](https://chargee.energy/sdk-license/v1).

## Support

[chargee.energy](https://chargee.energy)
