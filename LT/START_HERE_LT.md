# AutoCAD LT — P&ID Tool Palette

No AutoLISP required. Works LT 2018–2026 Windows and LT for Mac.
ISA-5.1 schematic symbols. Size/schedule are attributes.

## Critical path

1. Unzip to `C:\\CAD\\SS_PID_LT_ToolPalette\\` (path must not move).
2. OPTIONS → Files → Support File Search Path → add folder + `02_Blocks_DXF_FLAT`.
   Also add Trusted Locations and Tool Palettes File Locations (`04_ToolPalette`).
3. New imperial drawing. UNITS = inches. INSUNITS = 1. ATTDIA = 1. ATTREQ = 1.
4. SCRIPT `03_Scripts/PID-LT-LAYERS.scr`
5. SCRIPT `03_Scripts/PID-LT-BUILD-LIBRARY.scr` then SAVEAS `Blocks\\SS-PID-LT-LIBRARY.dwg`
6. ADCENTER (Ctrl+2) → that DWG → right-click DWG → **Create Tool Palette of Blocks**
7. Split into 8 tabs: 01 Lines / 02 Fittings / 03 Isolation / 04 Check-Relief / 05 Control / 06 Sanitary / 07 Instruments / 08 Annotation
8. Every valve/fitting Properties: Prompt for rotation = Yes, Explode = No, Scale = 1, Layer = P-PID-VALV or P-PID-FITT
9. CUSTOMIZE → New Group `SS P&ID` → Export each tab `.xtp` into `04_ToolPalette` (keep Images\\ beside XTP)
10. Daily: **click** the tool (do not drag) so rotation prompt fires; EATTEDIT TAG/SIZE/SCH/LINE

## LT limits
- LT 2023 and older: no LISP. LT 2024+ Windows: LISP optional. Mac LT: no LISP.
- LT cannot CREATE dynamic blocks. Static attributed blocks. Size is an attribute.
- XTP has no geometry — Source File must stay pointed at the library DWG.
- Do not create palettes while CUI is open.
