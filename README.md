# MyKiCad

Personal KiCad library repository for reusable symbols, footprints, 3D models, drawing sheet assets, and Eurorack-oriented schematic blocks.

This repository is maintained for KiCad 9 workflows and is intended to keep the mechanical, schematic, and PCB assets for recurring parts in one place.

## What is included

The current library set contains:

- Custom and imported schematic symbols in `kicad-symbols/`
- A KiCad footprint library in `Eurorack.pretty/`
- STEP 3D models in `kicad-packages3d/`
- Reusable schematic blocks in `Eurorack.kicad_blocks/`
- A custom worksheet template in `kicad-templates/`

At the moment, the repository is centered on Eurorack panel hardware, supporting power-entry blocks, and a small set of reusable components such as jacks, potentiometers, switches, and a CD4017-based design part.

## Repository structure

| Path | Purpose |
| --- | --- |
| `kicad-symbols/` | Symbol libraries and imported part symbols |
| `Eurorack.pretty/` | Footprint library directory ready to add through KiCad's Footprint Library Manager |
| `kicad-packages3d/` | STEP models used by the custom footprints |
| `Eurorack.kicad_blocks/` | Reusable schematic blocks for power and subsystem building |
| `kicad-templates/` | KiCad worksheet template assets |

## Library contents

### Symbols

The symbol folder currently includes these usable symbol libraries:

| File | Main symbol(s) |
| --- | --- |
| `kicad-symbols/cd4017be.kicad_sym` | `CD4017BE`, `RD901F` |
| `kicad-symbols/RD901F-40-15R1-B100K-00DL1.kicad_sym` | `RD901F-40-15R1-B100K-00DL1` |
| `kicad-symbols/1MS1T1B1M2QES.kicad_sym` | `1MS1T1B1M2QES` |

Also present:

- `kicad-symbols/Eurorack.kicad_sym` currently exists as a minimal library file and does not yet contain symbol definitions.
- `kicad-symbols/cd4017be.bak` is a backup file and is not needed for normal KiCad library setup.

### Footprints

`Eurorack.pretty/` is the packaged footprint library that is most convenient to register in KiCad. It currently contains:

- `1 Pole 8 Step Switch Alpha`
- `2MS1T1B1M2QES`
- `3296W1503LF`
- `CD4017BE THT`
- `Jack_3.5mm_QingPu_WQP-PJ398SM_Vertical`
- `Jack_6.35mm_PJ_629HAN_slots`
- `Kemet Film Cap`
- `POT_RD901F-40-15R1-B100K-00DL1`
- `Potentiometer_Alpha_RD902F-40-00D_Dual_Vertical_CircularHoles_centered`
- `RD901F`
- `RD901F_1`
- `SR1712F010820F0AN9N027`

### 3D models

The `kicad-packages3d/` folder currently includes STEP models for:

- `1MS1T1B1M2QES`
- `N0016A`
- `PJ398SM`
- `PJ398SM_Hex_nut`
- `PJ398SM_Knurl_nut`
- `RD901F-40-15F`
- `RD902F-40-00D`
- `SJ-63083A`

### KiCad blocks

The repository currently includes three reusable schematic blocks:

- `Europower +12 -12 GND (SMD Version)`
- `Eurorack +12 -12 5 GND (SMD Version)`
- `Power for TL074 (SMD Version)`

These blocks are intended to speed up repeated schematic entry for common power arrangements and subsystem fragments.

### Templates

The template folder currently contains:

- `Template with logo.kicad_wks`

## KiCad setup

### Recommended approach

1. Add `Eurorack.pretty/` as a footprint library in KiCad.
2. Add the required `.kicad_sym` files from `kicad-symbols/` through the Symbol Library Manager.
3. Keep `kicad-packages3d/` available on a stable local path so 3D models can be remapped cleanly where needed.
4. Add `Eurorack.kicad_blocks/` only if you use KiCad block workflows and want the reusable power fragments available in the editor.

### Notes about paths and portability

Some footprints in this repository still contain machine-specific absolute 3D model references from earlier workstations. In practice this means:

- The footprint geometry is usable as-is.
- 3D previews may need path cleanup or remapping on a new machine.
- If you want the repository to be portable across systems, prefer updating model paths to a consistent KiCad path variable or a repository-relative workflow in your local setup.

## Compatibility

This repository is maintained for KiCad 9. Some assets originated from imported or older library sources, but the active workflow target is KiCad 9 and that is the version the library should be considered validated against.

## Attribution and licensing

See `LICENSE.md` for the current attribution note related to third-party 3D models. Some STEP files in `kicad-packages3d/` were not created by the repository owner and may require separate attribution or reuse permission from the original author.

## Use and maintenance

This is primarily a personal working library. The main goal is practical reuse: keep validated parts together, reduce repeated setup work, and preserve the schematic, footprint, and 3D assets needed for future projects.

If this repository grows further, the next logical cleanup steps are:

- consolidate symbol naming and file naming
- consolidate footprint naming where imported parts still use inconsistent names
- normalize 3D model paths for cross-machine portability
