# MyKiCad

Personal KiCad library repository for reusable symbols, footprints, 3D models, drawing sheet assets, and Eurorack-oriented schematic blocks.

This repository is maintained for KiCad 9 workflows and is intended to keep the mechanical, schematic, and PCB assets for recurring parts in one place.

## What is included

The current library set contains:

- A consolidated KiCad symbol library in `Eurorack-symbols/`
- A KiCad footprint library in `Eurorack.pretty/`
- STEP 3D models in `Eurorack-3dmodels/`
- Reusable schematic blocks in `Eurorack.kicad_blocks/`
- A custom worksheet template in `Eurorack-templates/`

At the moment, the repository is centered on Eurorack panel hardware, supporting power-entry blocks, and a small set of reusable components such as jacks, potentiometers, switches, and a CD4017-based design part.

## Repository structure

| Path | Purpose |
| --- | --- |
| `Eurorack-symbols/` | Consolidated symbol library directory containing `Eurorack.kicad_sym` |
| `Eurorack.pretty/` | Footprint library directory ready to add through KiCad's Footprint Library Manager |
| `Eurorack-3dmodels/` | STEP models used by the custom footprints |
| `Eurorack.kicad_blocks/` | Reusable schematic blocks for power and subsystem building |
| `Eurorack-templates/` | KiCad worksheet template assets |

## Library contents

### Symbols

The symbol side is now consolidated into a single library file at `Eurorack-symbols/Eurorack.kicad_sym` so it matches the naming style of `Eurorack.pretty/` and is easier to register in KiCad.

Current symbols in that library:

| File | Main symbol(s) |
| --- | --- |
| `Eurorack-symbols/Eurorack.kicad_sym` | `CD4017BE`, `RD901F`, `SR1712F-0108-20F0A-N9-N-027`, `1MS1T1B1M2QES`, `RD901F-40-15R1-B100K-00DL1` |

The old split symbol files and backup file were removed as part of the consolidation.

### Footprints

`Eurorack.pretty/` is the packaged footprint library that is most convenient to register in KiCad.

Footprints now use a searchable naming scheme:

- component category first, for example `Switch`, `Potentiometer`, `Jack`, `IC`, `Capacitor`, `Trimmer`
- manufacturer or family next where it helps, for example `Alpha`, `Dailywell`, `Bourns`, `KEMET`
- key part or variant details last, such as `RD901F`, `CD4017BE`, `1P8T`, `B100K`, `THT`, or `Vertical`

This makes it easier to find parts quickly from KiCad's footprint chooser without remembering the exact imported filename.

Current footprint library contents:

| Footprint | Meaning |
| --- | --- |
| `Capacitor_Film_KEMET_R82DC4100AA60J_THT` | KEMET R82 series film capacitor |
| `IC_DIP-16_CD4017BE_THT` | DIP-16 through-hole footprint for CD4017BE |
| `Jack_3.5mm_QingPu_WQP-PJ398SM_Vertical` | 3.5 mm vertical audio jack |
| `Jack_6.35mm_PJ-629HAN_THT_Slotted` | 6.35 mm through-hole jack with slotted holes |
| `Potentiometer_Alpha_RD901F_B100K_Vertical` | Alpha RD901F single potentiometer, B100K variant |
| `Potentiometer_Alpha_RD901F_Vertical` | Alpha RD901F single potentiometer |
| `Potentiometer_Alpha_RD901F_Vertical_Alt` | Alternate imported RD901F footprint kept for comparison |
| `Potentiometer_Alpha_RD902F_Dual_Vertical` | Alpha RD902F dual potentiometer |
| `Switch_Rotary_Alpha_SR1712F_1P8T` | Alpha-style rotary switch, 1 pole 8 throw |
| `Switch_Rotary_Alpha_SR1712F_1P8T_Alt` | Alternate imported rotary-switch footprint kept for comparison |
| `Switch_Toggle_Dailywell_MS1T1B1M2QES_SPDT` | Dailywell SPDT toggle switch |
| `Trimmer_Bourns_3296W_50k_THT` | Bourns 3296W trimmer, 50 kOhm |

At the moment, `_Alt` footprints are retained when there are multiple imported variants of the same part and one has not yet been retired.

### 3D models

The `Eurorack-3dmodels/` folder now follows the same naming convention as the footprint library wherever the model is attached directly to a custom footprint.

Current model files include:

| 3D model file | Used by footprint |
| --- | --- |
| `Capacitor_Film_KEMET_R82DC4100AA60J_THT.stp` | `Capacitor_Film_KEMET_R82DC4100AA60J_THT` |
| `IC_DIP-16_CD4017BE_THT.stp` | `IC_DIP-16_CD4017BE_THT` |
| `Jack_3.5mm_QingPu_WQP-PJ398SM_Vertical.step` | `Jack_3.5mm_QingPu_WQP-PJ398SM_Vertical` |
| `Jack_3.5mm_QingPu_WQP-PJ398SM_Vertical_Hex_nut.step` | `Jack_3.5mm_QingPu_WQP-PJ398SM_Vertical` |
| `Jack_3.5mm_QingPu_WQP-PJ398SM_Vertical_Knurl_nut.step` | `Jack_3.5mm_QingPu_WQP-PJ398SM_Vertical` |
| `Jack_6.35mm_PJ-629HAN_THT_Slotted.step` | `Jack_6.35mm_PJ-629HAN_THT_Slotted` |
| `Potentiometer_Alpha_RD901F_B100K_Vertical.stp` | `Potentiometer_Alpha_RD901F_B100K_Vertical` |
| `Potentiometer_Alpha_RD901F_Vertical.stp` | `Potentiometer_Alpha_RD901F_Vertical` |
| `Potentiometer_Alpha_RD901F_Vertical_Alt.stp` | `Potentiometer_Alpha_RD901F_Vertical_Alt` |
| `Potentiometer_Alpha_RD902F_Dual_Vertical.stp` | `Potentiometer_Alpha_RD902F_Dual_Vertical` |
| `Switch_Rotary_Alpha_SR1712F_1P8T.stp` | `Switch_Rotary_Alpha_SR1712F_1P8T` |
| `Switch_Rotary_Alpha_SR1712F_1P8T_Alt.stp` | `Switch_Rotary_Alpha_SR1712F_1P8T_Alt` |
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

## KiCad setup

### Recommended approach

1. Add `Eurorack.pretty/` as a footprint library in KiCad.
2. Add `Eurorack-symbols/Eurorack.kicad_sym` through the Symbol Library Manager.
3. Use the `Eurorack:` library prefix in symbol footprint fields when assigning these custom footprints.
4. Define `KICAD_USER_3DMODEL_DIR` to point to this repository's `Eurorack-3dmodels/` folder.
5. Add `Eurorack.kicad_blocks/` only if you use KiCad block workflows and want the reusable power fragments available in the editor.

### Symbol to footprint links

The current symbols in `Eurorack-symbols/Eurorack.kicad_sym` point at the renamed footprints as follows:

- `CD4017BE` uses `Eurorack:IC_DIP-16_CD4017BE_THT`
- `RD901F` uses `Eurorack:Potentiometer_Alpha_RD901F_Vertical`
- `SR1712F-0108-20F0A-N9-N-027` uses `Eurorack:Switch_Rotary_Alpha_SR1712F_1P8T`
- `RD901F-40-15R1-B100K-00DL1` uses `Eurorack:Potentiometer_Alpha_RD901F_B100K_Vertical`
- `1MS1T1B1M2QES` uses `Eurorack:Switch_Toggle_Dailywell_MS1T1B1M2QES_SPDT`

### Notes about paths and portability

Custom footprints in this repository now reference their STEP files through `KICAD_USER_3DMODEL_DIR`.

- Set `KICAD_USER_3DMODEL_DIR` to the absolute path of `Eurorack-3dmodels/` on your machine.
- This keeps the footprint files portable across machines as long as the variable is defined in KiCad.
- Some third-party or future imports may still need cleanup if they are added with absolute model paths.

## Compatibility

This repository is maintained for KiCad 9. Some assets originated from imported or older library sources, but the active workflow target is KiCad 9 and that is the version the library should be considered validated against.

## Attribution and licensing

See `LICENSE.md` for the current attribution note related to third-party 3D models. Some STEP files in `Eurorack-3dmodels/` were not created by the repository owner and may require separate attribution or reuse permission from the original author.

## Use and maintenance

This is primarily a personal working library. The main goal is practical reuse: keep validated parts together, reduce repeated setup work, and preserve the schematic, footprint, and 3D assets needed for future projects.

If this repository grows further, the next logical cleanup steps are:

- decide whether the consolidated symbol library should keep the imported part-number symbol names or adopt more descriptive symbol names
- decide whether the remaining `_Alt` footprint variants should be merged or removed
- decide whether the remaining `_Alt` STEP variants should be merged or removed
