# Eurorack KiCad Library

Personal KiCad library repository for reusable symbols, footprints, 3D models, logo artwork, drawing sheet assets, and Eurorack-oriented schematic blocks.

This repository is maintained for KiCad 9 workflows and keeps the mechanical, schematic, and PCB assets for recurring parts in one place.

## What is included

The current library set contains:

- a consolidated KiCad symbol library in `Eurorack-symbols/`
- a KiCad footprint library in `Eurorack.pretty/`
- STEP 3D models in `Eurorack-3dmodels/`
- SVG and PNG logo exports in `Eurorack-logos/`
- reusable schematic blocks in `Eurorack.kicad_blocks/`
- custom worksheet templates in `Eurorack-templates/`

At the moment, the repository is centered on Eurorack panel hardware, supporting power-entry blocks, and a small set of reusable components and board artwork.

## Repository structure

| Path | Purpose |
| --- | --- |
| `Eurorack-symbols/` | Consolidated symbol library directory containing `Eurorack.kicad_sym` |
| `Eurorack.pretty/` | Footprint library directory ready to add through KiCad's Footprint Library Manager |
| `Eurorack-3dmodels/` | STEP models used by the custom footprints |
| `Eurorack-logos/` | SVG source exports plus PNG render exports for the Eurorack symbol, wordmark, and combined lockups |
| `Eurorack.kicad_blocks/` | Reusable schematic blocks for power and subsystem building |
| `Eurorack-templates/` | KiCad worksheet template assets |

## Library contents

### Symbols

The symbol side is consolidated into a single library file at `Eurorack-symbols/Eurorack.kicad_sym` so it matches the naming style of `Eurorack.pretty/` and is easier to register in KiCad.

Current top-level symbols in that library:

| Symbol | Linked footprint |
| --- | --- |
| `IC_DIP-16_CD4017BE_THT` | `IC_DIP-16_CD4017BE_THT` |
| `Potentiometer_Alpha_RD901F_B100K_Vertical` | `Potentiometer_Alpha_RD901F_B100K_Vertical` |
| `Potentiometer_Alpha_RD901F_Vertical` | `Potentiometer_Alpha_RD901F_Vertical` |
| `Switch_Rotary_Alpha_SR1712F_1P8T` | `Switch_Rotary_Alpha_SR1712F_1P8T` |
| `Switch_Toggle_Dailywell_MS1T1B1M2QES_SPDT` | `Switch_Toggle_Dailywell_MS1T1B1M2QES_SPDT` |

Note: the symbol `Potentiometer_Alpha_RD901F_B100K_Vertical` still points to a footprint name that is not currently present in `Eurorack.pretty/`.

### Footprints

`Eurorack.pretty/` is the packaged footprint library that is most convenient to register in KiCad.

Most footprint names follow a searchable component-first style, while a few older imports and artwork footprints still keep their original naming.

Current footprint library contents:

| Footprint | Meaning |
| --- | --- |
| `Arduino_Nano` | Arduino Nano module footprint |
| `Capacitor_Film_KEMET_R82DC4100AA60J_THT` | KEMET R82 series film capacitor |
| `IC_DIP-16_CD4017BE_THT` | DIP-16 through-hole footprint for CD4017BE |
| `Jack_3.5mm_QingPu_WQP-PJ398SM_Vertical` | 3.5 mm vertical audio jack |
| `Jack_6.35mm_PJ-629HAN_THT_Slotted` | 6.35 mm through-hole jack with slotted holes |
| `Potentiometer_Alpha_RD901F_Vertical_Alt` | Alternate imported RD901F footprint kept for comparison |
| `Potentiometer_Alpha_RD902F_Dual_Vertical` | Alpha RD902F dual potentiometer |
| `RoHs` | RoHS compliance board-art/logo footprint |
| `Switch_Rotary_Alpha_SR1712F_1P8T` | Alpha-style rotary switch, 1 pole 8 throw |
| `Switch_Toggle_Dailywell_MS1T1B1M2QES_SPDT` | Dailywell SPDT toggle switch |
| `Switch_Toggle_Dailywell_MS3T1B1M2QES_SPDT_1` | Alternate Dailywell SPDT toggle switch footprint variant |
| `Trimmer_Bourns_3296W_50k_THT` | Bourns 3296W trimmer, 50 kOhm |

### 3D models

The `Eurorack-3dmodels/` folder mostly follows the same naming convention as the footprint library wherever the model is attached directly to a custom footprint, with a few retained legacy or unmatched model files still present.

Current model files include:

| 3D model file | Used by footprint |
| --- | --- |
| `Arduino Nano.STEP` | `Arduino_Nano` |
| `Capacitor_Film_KEMET_R82DC4100AA60J_THT.stp` | `Capacitor_Film_KEMET_R82DC4100AA60J_THT` |
| `IC_DIP-16_CD4017BE_THT.stp` | `IC_DIP-16_CD4017BE_THT` |
| `Jack_3.5mm_QingPu_WQP-PJ398SM_Vertical.step` | `Jack_3.5mm_QingPu_WQP-PJ398SM_Vertical` |
| `Jack_3.5mm_QingPu_WQP-PJ398SM_Vertical_Hex_nut.step` | `Jack_3.5mm_QingPu_WQP-PJ398SM_Vertical` |
| `Jack_3.5mm_QingPu_WQP-PJ398SM_Vertical_Knurl_nut.step` | `Jack_3.5mm_QingPu_WQP-PJ398SM_Vertical` |
| `Jack_6.35mm_PJ-629HAN_THT_Slotted.step` | `Jack_6.35mm_PJ-629HAN_THT_Slotted` |
| `Potentiometer_Alpha_RD901F_B100K_Vertical.stp` | retained model asset, no matching footprint currently in `Eurorack.pretty/` |
| `Potentiometer_Alpha_RD901F_Vertical.stp` | retained model asset for the RD901F family |
| `Potentiometer_Alpha_RD901F_Vertical_Alt.stp` | `Potentiometer_Alpha_RD901F_Vertical_Alt` |
| `Potentiometer_Alpha_RD902F_Dual_Vertical.stp` | `Potentiometer_Alpha_RD902F_Dual_Vertical` |
| `Switch_Rotary_Alpha_SR1712F_1P8T.stp` | `Switch_Rotary_Alpha_SR1712F_1P8T` |
| `Switch_Rotary_Alpha_SR1712F_1P8T_Alt.stp` | retained alternate model asset |
| `Switch_Toggle_Dailywell_MS1T1B1M2QES_SPDT.stp` | `Switch_Toggle_Dailywell_MS1T1B1M2QES_SPDT` |
| `Trimmer_Bourns_3296W_50k_THT.stp` | `Trimmer_Bourns_3296W_50k_THT` |

### KiCad blocks

The repository currently includes three reusable schematic blocks:

- `Europower +12 -12 GND (SMD Version)`
- `Eurorack +12 -12 5 GND (SMD Version)`
- `Power for TL074 (SMD Version)`

These blocks are intended to speed up repeated schematic entry for common power arrangements and subsystem fragments.

### Templates

The template folder currently contains:

- `Template with logo.kicad_wks`
- `dirty dream template.kicad_wks`

### Logos

The `Eurorack-logos/` folder contains icon-only, wordmark-only, and combined lockup exports in both SVG and PNG form.

SVG exports in `Eurorack-logos/` currently include:

- `eurorack-symbol-solid.svg`
- `eurorack-symbol-outline.svg`
- `eurorack-symbol-outline-thicker.svg`
- `eurorack-symbol-solid-with-accent-lines.svg`
- `eurorack-symbol-outline-with-accent-lines.svg`
- `eurorack-wordmark-solid.svg`
- `eurorack-wordmark-outline.svg`
- `eurorack-lockup-solid.svg`
- `eurorack-lockup-solid-with-accent-lines.svg`
- `eurorack-lockup-outline.svg`
- `eurorack-lockup-outline-with-accent-lines.svg`
- `eurorack-lockup-outline-with-solid-symbol.svg`
- `eurorack-lockup-outline-with-solid-symbol-and-accent-lines.svg`

PNG exports in `Eurorack-logos/png/` mirror those logo variants and currently include:

- `eurorack-symbol-solid.png`
- `eurorack-symbol-outline.png`
- `eurorack-symbol-outline-thicker.png`
- `eurorack-symbol-solid-with-accent-lines.png`
- `eurorack-symbol-outline-with-accent-lines.png`
- `eurorack-wordmark-solid.png`
- `eurorack-wordmark-outline.png`
- `eurorack-lockup-solid.png`
- `eurorack-lockup-solid-with-accent-lines.png`
- `eurorack-lockup-outline.png`
- `eurorack-lockup-outline-with-accent-lines.png`
- `eurorack-lockup-outline-with-solid-symbol.png`
- `eurorack-lockup-outline-with-solid-symbol-and-accent-lines.png`
- `certificates.png`

Naming stays in lowercase English kebab-case. Variant suffixes are used where needed:

- `with-accent-lines` replaces the old mixed-language `Striche` naming
- `with-solid-symbol` identifies the hybrid outline-wordmark plus filled-symbol exports
- `outline-thicker` identifies the heavier outline-only symbol variant

## KiCad setup

### Recommended approach

1. Add `Eurorack.pretty/` as a footprint library in KiCad.
2. Add `Eurorack-symbols/Eurorack.kicad_sym` through the Symbol Library Manager.
3. Use the `Eurorack:` library prefix in symbol footprint fields when assigning these custom footprints.
4. Define `KICAD_USER_3DMODEL_DIR` to point to this repository's `Eurorack-3dmodels/` folder.
5. Add `Eurorack.kicad_blocks/` only if you use KiCad block workflows and want the reusable power fragments available in the editor.

### Notes about paths and portability

Most custom footprints in this repository include `${KICAD_USER_3DMODEL_DIR}` model references.

- Set `KICAD_USER_3DMODEL_DIR` to the absolute path of `Eurorack-3dmodels/` on your machine.
- Several imported footprints still retain additional absolute model paths from earlier setups and may need cleanup over time.
- `Arduino_Nano.kicad_mod` is one of the older imports that still needs that path cleanup.

## Compatibility

This repository is maintained for KiCad 9. Some assets originated from imported or older library sources, but the active workflow target is KiCad 9 and that is the version the library should be considered validated against.

## Attribution and licensing

See `LICENSE.md` for the current attribution note related to third-party 3D models. Some STEP files in `Eurorack-3dmodels/` were not created by the repository owner and may require separate attribution or reuse permission from the original author.

## Use and maintenance

This is primarily a personal working library. The main goal is practical reuse: keep validated parts together, reduce repeated setup work, and preserve the schematic, footprint, and 3D assets needed for future projects.

If this repository grows further, the next logical cleanup steps are:

- align symbol footprint properties with the actual footprint inventory
- remove leftover absolute 3D model paths from imported footprints
- decide whether retained alternate or unmatched STEP assets should stay or be retired
