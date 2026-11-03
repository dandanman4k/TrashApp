# TrashApp

**Cross-platform Flutter client for a community waste-reporting project.**

`TrashApp` is the application-side part of an environmental monitoring experiment. The wider project explores using images, location information and a supporting backend to describe where litter is accumulating and help coordinate an informed response.

> **Status:** Work in progress. The earlier public repository view confirmed a Flutter project, but did not expose enough Dart source to validate individual user flows. The proposed functions below are project direction, not a completed-feature checklist.

## What the project aims to do

1. Collect a waste observation, potentially with an image and location.
2. Send or store that observation in an application-accessible format.
3. Let people review reports and prioritize areas that need attention.
4. Support later integration with analysis or image recognition.

## Stack

| Component | Technology |
| --- | --- |
| Client framework | Flutter / Dart |
| Mobile runners | Android, iOS |
| Other generated runners | Web, Windows, macOS, Linux |
| Packages and assets | `pubspec.yaml` |
| Companion repositories | `TrashAppServer`, `TrashModelTraining` |

Generated platform folders indicate project scaffolding, **not** confirmed support or production readiness on every platform.

## Repository layout

```text
TrashApp/
├── lib/                # Application source
├── test/               # Flutter tests, if maintained
├── android/            # Android configuration
├── ios/                # iOS configuration
├── web/                # Web runner
├── windows/            # Windows runner
├── macos/              # macOS runner
├── linux/              # Linux runner
├── pubspec.yaml        # Dependencies and Flutter assets
└── README.md
```

## Getting started

Install [Flutter](https://docs.flutter.dev/get-started/install), the correct native SDK for your target, and a device/emulator.

```bash
git clone https://github.com/dandanman4k/TrashApp.git
cd TrashApp
flutter doctor
flutter pub get
flutter devices
flutter run
```

If web support is configured and the application supports it:

```bash
flutter run -d chrome
```

## Development

```bash
flutter analyze
flutter test
```

Check `lib/` and `pubspec.yaml` to determine whether maps, camera, geolocation, remote storage or authentication packages are actually in use.

## Backend integration

A separate repository, [TrashAppServer](https://github.com/dandanman4k/TrashAppServer), contains Node.js server code. An exact API contract could not be verified. When the client and backend are tested together, document the base URL, authentication, request/response examples, upload limits, timeout behavior and failure handling here.

Do not hard-code production secrets in the Flutter source. Client-side code should be treated as public even when compiled into an APK.

## Data-handling considerations

For reports that include images or precise location, provide a clear consent flow; limit personal data stored; and account for offline access, unreliable networks and duplicate submissions.

## Related projects

- [recyclemap](https://github.com/dandanman4k/recyclemap): a related mapping-oriented Flutter prototype.
- [TrashAppServer](https://github.com/dandanman4k/TrashAppServer): backend repository.
- [TrashModelTraining](https://github.com/dandanman4k/TrashModelTraining): object-detection model experiment.

## What to document next

Add actual screenshots, a tested feature list, the verified backend contract, supported devices and deployment steps. Make sure documented behavior matches the current `lib/` code.

## License

Check the current repository for an explicit license before redistributing or reusing the project.
