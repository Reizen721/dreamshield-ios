# DreamShield iOS v0.1.1

The native SwiftUI app supports iOS and iPadOS 17 or later. It pairs with the DreamShield desktop server and displays connection status, environmental readings, snapshots, and history. It also provides an entry point for AI review. Configure temperature-control presets and closed-loop thermal assessment in the desktop console.

## Build

Open `DreamShield.xcodeproj` on a Mac with Xcode 16 or a compatible version. Choose the shared **DreamShield** scheme, select an iPhone simulator, and click **Run**. To install on an iPhone, select your own team in **Signing & Capabilities** and run against the connected device.

From the repository root, run the project structure check.

~~~sh
python scripts/validate_project.py
~~~

On macOS, run the simulator build check. The unsigned simulator build does not require Apple signing credentials.

~~~sh
bash scripts/verify_build.sh
~~~

## Pair with the server

1. Start [DreamShield Server](https://github.com/Reizen721/dreamshield-server) on your PC. This iOS release pairs with Server v0.1.6.
2. On the PC, open [the mobile setup page](http://127.0.0.1:8016/mobile-setup).
3. With the iOS device and PC on the same local network, paste the generated pairing JSON into the app's settings. Verify the PC's local address and certificate fingerprint. Allow local network access when prompted. The gateway uses HTTPS on port `8746` by default.

See the [mobile API contract](https://github.com/Reizen721/dreamshield-server/blob/v0.1.6/docs/mobile-api.md) for gateway addresses and pairing payloads, and the [compatibility matrix](https://github.com/Reizen721/dreamshield-server/blob/v0.1.6/docs/compatibility.md) for tested versions. The Android companion app is in [DreamShield Android](https://github.com/Reizen721/dreamshield-android).

## Verification

On Windows, 57 project structure checks and 34 supporting-tool tests passed. Swift compilation, XCTest, and on-device verification require Xcode on macOS.
