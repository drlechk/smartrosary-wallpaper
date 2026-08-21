# SmartRosary Wallpaper

Wallpaper image source repository for SmartRosary device and app surfaces. It stores preset PNG files and manifests for 240 px, 466 px, 368 x 448 px, and 448 x 368 px device display variants.

## What is in this repository

- `manifest.json` - top-level preset manifest grouped by display size.
- `img-240-png/` - 240 px wallpaper PNGs and `factory.json`.
- `img-466-png/` - 466 px wallpaper PNGs and `factory.json`.
- `img-368x448-png/` - 368 x 448 px wallpaper PNGs and `factory.json`.
- `img-448x368-png/` - 448 x 368 px wallpaper PNGs and `factory.json`.

## Usage

The firmware, dashboard, app, and installer workflows can use this repository as the source for available wallpaper presets. Keep `manifest.json` aligned with the PNG files that should be exposed to users.

The current manifest groups presets by display size:

- `240` for the smaller display target.
- `466` for the ESP32-S3 AMOLED display target.
- `368x448` for the ESP32-S3 Touch AMOLED 1.8 portrait target.
- `448x368` for the ESP32-S3 Touch AMOLED 1.8 landscape target.

## Validation

There is no build or test command documented for this repository. After changing presets:

```sh
python3 -m json.tool manifest.json
python3 -m json.tool img-240-png/factory.json
python3 -m json.tool img-466-png/factory.json
python3 -m json.tool img-368x448-png/factory.json
python3 -m json.tool img-448x368-png/factory.json
```

Also verify that each manifest URL points to a committed PNG file.

## License

This repository is licensed under the PolyForm Noncommercial License 1.0.0. See `LICENSE`.
