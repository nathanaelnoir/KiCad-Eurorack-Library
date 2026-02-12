
![KiCad](https://img.shields.io/badge/KiCad-9-orange)
![Status](https://img.shields.io/badge/Status-Personal-blue)

# MyKiCad — Personal KiCad Library

A personal collection of KiCad footprints, symbols, and 3D models maintained for small projects and reuse. NOTE: I use these libraries with KiCad 9 only.

## Overview

This repository contains custom KiCad library assets created and curated for personal use. It groups footprints, 3D models, and symbols so they can be easily referenced from KiCad projects.


## Repository layout

### Footprints

| File | Path | Notes |
|---|---|---|
| Jack_3.5mm_QingPu_WQP-PJ398SM_Vertical.kicad_mod | [kicad-footprints/Jack_3.5mm_QingPu_WQP-PJ398SM_Vertical.kicad_mod](kicad-footprints/Jack_3.5mm_QingPu_WQP-PJ398SM_Vertical.kicad_mod) | KiCad footprint module (.kicad_mod)
| Jack_6.35mm_PJ_629HAN_slots.kicad_mod | [kicad-footprints/Jack_6.35mm_PJ_629HAN_slots.kicad_mod](kicad-footprints/Jack_6.35mm_PJ_629HAN_slots.kicad_mod) | KiCad footprint module (.kicad_mod)
| Potentiometer_Alpha_RD902F-40-00D_Dual_Vertical_CircularHoles_centered.kicad_mod | [kicad-footprints/Potentiometer_Alpha_RD902F-40-00D_Dual_Vertical_CircularHoles_centered.kicad_mod](kicad-footprints/Potentiometer_Alpha_RD902F-40-00D_Dual_Vertical_CircularHoles_centered.kicad_mod) | KiCad footprint module (.kicad_mod)

### 3D models

| File | Path | Notes |
|---|---|---|
| PJ398SM_Hex_nut.step | [kicad-packages3d/PJ398SM_Hex_nut.step](kicad-packages3d/PJ398SM_Hex_nut.step) | STEP model used by PJ398SM footprints
| PJ398SM_Knurl_nut.step | [kicad-packages3d/PJ398SM_Knurl_nut.step](kicad-packages3d/PJ398SM_Knurl_nut.step) | STEP model used by PJ398SM footprints
| PJ398SM.step | [kicad-packages3d/PJ398SM.step](kicad-packages3d/PJ398SM.step) | Main PJ398SM STEP model
| RD902F-40-00D.stp | [kicad-packages3d/RD902F-40-00D.stp](kicad-packages3d/RD902F-40-00D.stp) | Potentiometer 3D model (STEP)
| SJ-63083A.STEP | [kicad-packages3d/SJ-63083A.STEP](kicad-packages3d/SJ-63083A.STEP) | Misc 3D model (STEP)

### Symbols

| File | Path | Notes |
|---|---|---|
| (none yet) | [kicad-symbols](kicad-symbols/) | Schematic symbols and symbol library files — currently empty.

## Recommended KiCad versions

These files are intended for KiCad 9. They may work with other versions, but compatibility is not guaranteed.

## Installation / Usage

1. Copy or symlink the `kicad-footprints`, `kicad-packages3d`, and `kicad-symbols` folders into a location that your KiCad installation can access (for example, a dedicated library folder).
2. In KiCad, add the libraries via the library managers:
   - Footprints: Preferences → Manage Footprint Libraries
   - Symbols: Preferences → Manage Symbol Libraries
   - 3D models are referenced from footprint `.kicad_mod` entries; ensure `kicad-packages3d` is reachable by the footprint paths.
3. When adding libraries, prefer using relative paths or absolute paths that will be stable across your environment.

Tip: For project-specific use, copy needed footprints or symbols into your project's library tables to avoid global changes.

## Naming & Conventions

- Footprints use descriptive names matching the component (e.g., connector, potentiometer, jack) and may include the vendor/model identifier.
- 3D models are provided in STEP format for mechanical integration in PCB assemblies.

## Contribution

This is primarily a personal library. If you want to contribute improvements or additional parts:

- Fork the repository and submit a pull request with the new/updated files.
- Include a short description of the part, the tested KiCad version, and any 3D source or vendor links.

Before merging, test footprints in a board and verify symbol pin mappings and 3D alignment.

## License

No license file is included. These assets are distributed by the repository owner. Contact the owner for reuse permissions or to request a license.

## Credits & References

- Generated and maintained by the repository owner for personal and small-team use.
- Where applicable, parts reference vendor datasheets and 3D model sources — see individual files for details.

## Contact

For questions, improvements, or reuse requests, open an issue or send a pull request in this repository.
