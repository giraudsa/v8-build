# V8 Monolithic Library Builds

This repository contains automated builds of Google V8 static libraries for multiple platforms using GitHub Actions.

English | [简体中文](README.ZH.md)

## Current V8 Version

**14.3.92**

## Supported Platforms

- **Android** (arm64, arm)
- **iOS** (arm64, arm64.simulator)
- **macOS** (arm64)
- **Windows** (x64)

## Latest Release

Check the [Releases](../../releases) page for the latest precompiled binaries.

## Package Contents

Each release includes zip packages with:
- **Static library file** (libv8_monolith.a / v8_monolith.lib)
- **args.gn** - Build configuration used for compilation
- **args.full.txt** - Complete GN arguments list with all default values and descriptions

## Build Configuration Files

The repository contains GN build configuration files for each platform:

### Android
- [args.android.arm64.gn](args.android.arm64.gn)
- [args.android.arm.gn](args.android.arm.gn)

### iOS
- [args.ios.arm64.gn](args.ios.arm64.gn) - iOS device
- [args.ios.arm64.simulator.gn](args.ios.arm64.simulator.gn) - iOS simulator

### macOS
- [args.mac.arm64.gn](args.mac.arm64.gn)

### Windows
- [args.win.x64.gn](args.win.x64.gn)

## Features

- ✅ Automated builds via GitHub Actions
- ✅ Consistent configuration across platforms
- ✅ Pre-build scripts for platform-specific optimizations ([builder.js](builder.js))
- ✅ Full build argument traceability
- ✅ iOS WebAssembly support enabled

## Usage

1. Download the appropriate zip file for your platform from the [Releases](../../releases) page
2. Extract the static library file
3. Link against the library in your project
4. Include the V8 headers (included in the release)
5. Refer to `args.gn` and `args.full.txt` to understand the build configuration

## Build System

All builds are automated using [GitHub Actions](.github/workflows/main.yml):
- Clean build environment for each platform
- Consistent depot_tools version
- Reproducible builds
- Automated release creation

## V8 Documentation

### Official V8 Resources
- [V8 Build Instructions](https://v8.dev/docs/build)
- [V8 Build with GN](https://v8.dev/docs/build-gn)
- [V8 ARM64 Build](https://v8.dev/docs/compile-arm64)

### Chromium Build Instructions
- [Windows Build Instructions](https://chromium.googlesource.com/chromium/src/+/HEAD/docs/windows_build_instructions.md)
- [Android Build Instructions](https://chromium.googlesource.com/chromium/src/+/HEAD/docs/android_build_instructions.md)
- [iOS Build Instructions](https://chromium.googlesource.com/chromium/src/+/HEAD/docs/ios/build_instructions.md)
- [macOS Build Instructions](https://chromium.googlesource.com/chromium/src/+/HEAD/docs/mac_build_instructions.md)
- [macOS ARM64 Build](https://chromium.googlesource.com/chromium/src/+/HEAD/docs/mac_arm64.md)

### Additional Resources
- [V8 Release Schedule](https://chromiumdash.appspot.com/schedule)
- [GitHub Actions Runner Images](https://github.com/actions/runner-images)

## Contributing

To update the V8 version or modify build configurations:

1. Update `V8_VERSION` in [.github/workflows/main.yml](.github/workflows/main.yml)
2. Modify platform-specific `args.*.gn` files as needed
3. Update [builder.js](builder.js) for platform-specific build logic
4. Create a new git tag to trigger the build workflow

## License

This repository contains build configurations and automation scripts. V8 itself is licensed under the BSD license. See the [V8 repository](https://github.com/v8/v8) for details.
