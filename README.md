# ESP32 T-Display S2/S3 AMOLED project template

## Description

This is a project template focus on [ESP32 T-Display-S2](https://www.espressif.com/en/products/socs/esp32-s2) and [ESP32 T-Display-S3 (AMOLED, long)](https://www.espressif.com/en/products/socs/esp32-s3) microcontroller boards. It is based on the [ESP32-ghbuild-template](https://github.com/mcuw/ESP32-ghbuild-template) project template which supports a lot more boards. Please have a look there as well.

The following tools are in use for an automatic build [GitHub Actions](https://github.com/features/actions) and [platformio](https://platformio.org/).


## Requirements

- [Visual Source Code](https://code.visualstudio.com/) IDE
- [platformio extension](https://platformio.org/)


## Get Started

<img src="https://github.com/mcuw/ESP32-ghbuild-tdisplays3-amoled/blob/main/doc/create-new-project-with-template.png" />

1. Login to github

2. Click on `Use this template` to create a new git repository
3. Replace the whole content of this [README.md](README.md) file
4. Implement your application in the [src/main.cpp](src/main.cpp)
5. Comment your new change in the [CHANGELOG.md](CHANGELOG.md) file
6. Push your changes

```sh
git add .
```

```sh
git commit -am "my app"
```

```sh
git push -u origin main
```

5. Create a new tag to trigger a release, e.g. for v1.0.0

```sh
git tag v1.0.0
```

```sh
git push origin v1.0.0
```

6. You can find your firmwares under `Releases` after the CI build finished


## How to flash your microcontroller

Variant A - Online and no need to install an app
- download a `.bin` firmware file from releases then flash with:
https://mcuw.github.io/ESPConnect/

Variant B - Visual Studio Code
1. Select a board in Visual Studio Code

<img src="https://github.com/mcuw/ESP32-ghbuild-tdisplays3-amoled/blob/main/doc/choose-board-in-vsc.png" />

2. Flash your board

<img src="https://github.com/mcuw/ESP32-ghbuild-tdisplays3-amoled/blob/main/doc/flash-with-vsc.png" />


## Supported boards

- ESP32 S2 T-Display
- ESP32 S3 with dual-core processor
  - [LilyGo T-Display S3](https://s.click.aliexpress.com/e/_DBmOMkn) (aliexpress affiliate link)
  - [LilyGo T-Display-S3 AMOLED](https://s.click.aliexpress.com/e/_DmboYpZ) (aliexpress affiliate link)
  - [LilyGo T-Display-S3 Touch](https://s.click.aliexpress.com/e/_DCBgPlV) (aliexpress affiliate link)
  - [LilyGo T-Display S3 Long](https://s.click.aliexpress.com/e/_Dl6UVMx) (aliexpress affiliate link)


## PlatformIO

[PlatformIO](https://platformio.org/) is a tool to create microcontroller apps for arduino platforms and compatibles (esp32). You can install the [Visual Studio Code extension](https://platformio.org/install/ide?install=vscode) in the [Visual Studio Code](https://code.visualstudio.com/) IDE.

## GitHub Actions - Workflow

The release build happens in the `build & release` workflow: [build_release.yml](.github/workflows/build_release.yml).
It creates a release, after creation of a new git tag (named it like `v1.0.0`).

If you want to test the build on all merge w/o creating a tag then the `build` workflow is what you looking for: [build.yml](.github/workflows/build.yml)


## Python

There is a tiny python script needed to customize the firmware filenames within platformio, see documentation: https://docs.platformio.org/en/stable/scripting/examples/custom_program_name.html

The [extra_script.py](extra_script.py) script gets the platformio env (e.g. lolin32) and the git-tag for the firmware filename.
This is required to publish several firmware names in the github artifacts of a release.

## CHANGELOG

You can write your changes in the [CHANGELOG.md](CHANGELOG.md) before you create a release. It will be shown under the release page.

## Example Release

see [Releases](https://github.com/mcuw/esp-ghbuild-template/releases) on the right sidemenu.

## Usage

Use this repository as a template for your own esp32 repository. You can reduce and adapt your required boards in the [platformio.ini](platformio.ini). Update the [CHANGELOG.md](CHANGELOG.md) file before you are creating a new release. When you create a new git tag then a new release will always includes  generated firmwares.

---

## Disclaimer

Contribution and help ... if you find an issue or wants to contribute then please do not hesitate to create a merge request or an issue.

We provide our build template as is, and we make no promises or guarantees about this code.
