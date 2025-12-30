# Formix KiCad Library

A KiCad 9.0 library containing symbols, footprints, and 3D models.

## Components

Currently, this library includes:

- **ESP32-S3-Zero** - WaveShare ESP32-S3-Zero development board
  - Datasheet: [WaveShare Wiki](https://www.waveshare.com/wiki/ESP32-S3-Zero)
  - Symbol: [symbols/WaveShare.kicad_sym](symbols/WaveShare.kicad_sym)
  - Footprint: [footprints/WaveShare.pretty/ESP32-S3-Zero.kicad_mod](footprints/WaveShare.pretty/ESP32-S3-Zero.kicad_mod)
  - 3D Model: [3dmodels/WaveShare.3dshapes/ESP32-S3-Zero_V2.stp](3dmodels/WaveShare.3dshapes/ESP32-S3-Zero_V2.stp)

### Known Issues

**ESP32-S3-Zero Bottom Pads:** The ESP32-S3-Zero has several pads (17, 18, 38-42, and 45) located on the bottom of the PCB module that are currently not included in the footprint. I'm not sure how to properly add these bottom-side pads to the KiCad footprint or if there's a standard way to connect to them. **Help wanted!** If you have experience with this type of footprint design, please contribute or provide guidance.

Additionally, pads 14, 15, and 16 are on the top side of the PCB module and are not included in this surface-mount footprint since there's nothing we can do on that side for a surface-mount design.

## Installation

### Method 1: Add as Project Library (Recommended)

1. Clone or download this repository to your local machine
2. Open your KiCad project
3. Go to **Preferences → Manage Symbol Libraries...**
4. Click the **Project Specific Libraries** tab
5. Click the folder icon to add a new library
6. Navigate to and select the `symbols/WaveShare.kicad_sym` file
7. Click **OK**

For footprints:

1. Go to **Preferences → Manage Footprint Libraries...**
2. Click the **Project Specific Libraries** tab
3. Click the folder icon to add a new library
4. Navigate to and select the `footprints/WaveShare.pretty` folder
5. Set the nickname to "WaveShare"
6. Click **OK**

### Method 2: Add as Global Library

Follow the same steps as Method 1, but use the **Global Libraries** tab instead of **Project Specific Libraries**. This makes the library available to all your KiCad projects.

### 3D Models Configuration

The 3D models are referenced using the `${KICAD9_FORMIX_LIBRARY}` environment variable. To set this up:

1. Go to **Preferences → Configure Paths...**
2. Click the **+** button to add a new environment variable
3. Set the **Name** to `KICAD9_FORMIX_LIBRARY`
4. Set the **Path** to the absolute path where you cloned this repository
5. Click **OK** to save

The footprint expects the 3D model at: `${KICAD9_FORMIX_LIBRARY}/3dmodels/WaveShare.3dshapes/ESP32-S3-Zero_V2.stp`

**Note:** The path should point directly to the root of your cloned repository, not to its parent directory.

## License

This library is licensed under the [Creative Commons CC-BY-SA 4.0 License](LICENSE.md) with the same exception as the official KiCad libraries.

## Contributing

Contributions are welcome! If you find an error in the library data or want to add more components, please submit a pull request or open an issue.

## Warranty

The libraries are provided in the hope that they will be useful, but are provided without warranty of any kind, express or implied.