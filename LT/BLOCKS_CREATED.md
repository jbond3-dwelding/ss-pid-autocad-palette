# AutoCAD LT valve and fitting blocks

R12 DXF schematic symbols for 61 valves, fittings, sanitary items, and marks.
ISA-5.1 / PIP PIC001 style. Not to-scale plan geometry.

- Valve body width: **0.50 in**
- Units: inches (`INSUNITS = 1`)
- Geometry drawn on layer `0` so it inherits the current layer
- Visible attributes: `TAG`, `SIZE`, `TYPE`
- Invisible attributes (EATTEDIT): `LINE SCH SPEC MATL END RATING INSUL FAIL POS VIEW NOTES`
- Defaults: SIZE=2  SCH=40S  SPEC=S40S  MATL=316L  END=BW  RATING=150  POS=NO

## Install in AutoCAD LT

1. Copy this repo (or the `LT` folder) to a stable path, e.g. `C:\\CAD\\SS_PID_LT_ToolPalette\\`
2. OPTIONS → Files → Support File Search Path → add:
   - the folder containing this README
   - `LT/02_Blocks_DXF_FLAT`
3. Also add that path under Trusted Locations.
4. New imperial drawing. `UNITS` = inches. `INSUNITS` = 1.
5. Run SCRIPT `LT/03_Scripts/PID-LT-LAYERS.scr`
6. Either:
   - `INSERT` → `LT/SS-PID-LT-LIBRARY.dxf` (all block definitions + catalog sheet), then SAVEAS `Blocks/SS-PID-LT-LIBRARY.dwg`
   - or SCRIPT `LT/03_Scripts/PID-LT-BUILD-LIBRARY.scr` (inserts each DXF by name from the support path)
7. ADCENTER (Ctrl+2) → the library DWG → right-click → **Create Tool Palette of Blocks**
8. Split into tabs per `Palettes/PALETTE_CATALOG.md`
9. Tool properties: Prompt for rotation = Yes, Explode = No, Scale = 1
   Layer = `P-PID-VALV` or `P-PID-FITT`

Daily use: click the tool (do not drag) so the rotation prompt fires, then EATTEDIT for TAG/SIZE/SCH/LINE.

## Block list

### Isolation valves
PID-VLV-GATE, PID-VLV-BALL, PID-VLV-PLUG, PID-VLV-BFY, PID-VLV-KNIFE, PID-VLV-GLB, PID-VLV-ANGL, PID-VLV-NDL, PID-VLV-DIA, PID-VLV-3WAY, PID-VLV-4WAY, PID-VLV-DBB

### Check / relief / specialty
PID-CHK-SW, PID-CHK-LIFT, PID-CHK-WFR, PID-PSV, PID-PSV-ANG, PID-RD, PID-VB, PID-PRV-REG, PID-BFP

### Control valves
PID-CV-GLB, PID-CV-BALL, PID-CV-BFY, PID-CV-DIA, PID-XV, PID-HCV, PID-PCV

### Fittings
PID-TEE, PID-WYE, PID-CROSS, PID-RED-CON, PID-RED-ECC, PID-CAP, PID-UNION, PID-FLG, PID-SBLIND, PID-SPACER, PID-HOSE, PID-HOSE-STN, PID-STR-Y, PID-STR-T, PID-STR-BKT, PID-RO, PID-TRAP, PID-DRAIN, PID-WELD

### Sanitary
PID-SAN-TC, PID-SAN-FER, PID-SAN-EL90, PID-SAN-TEE, PID-SAN-RED, PID-SAN-BALL, PID-SAN-BFY, PID-SAN-DIA, PID-SAN-SAMP, PID-SAN-SPRAY

### Marks
PID-ARW-FLOW, PID-ARW-SLOPE, PID-BRK-SPEC, PID-OPC

## Regenerate

```
python Python/generate_pid_lt_dxf.py
```

Writes DXF into `LT/02_Blocks_DXF_FLAT/` and `LT/SS-PID-LT-LIBRARY.dxf`.

## Limits

- AutoCAD LT cannot **create** dynamic blocks. These are static attributed blocks.
- Size is an attribute, not a lookup table. Geometry does not scale with NPS.
- Confirm company P&ID standard before issue. ISA-5.1 allows company variants.
