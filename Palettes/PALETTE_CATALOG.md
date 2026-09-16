# Palette group: SS P&ID

ISA-5.1 / PIP PIC001 schematic symbols. Not to-scale plan geometry.
Insert 1:1 in paper space (or annotative). Valve body width = 0.50 in.
Prompt for rotation = Yes. Explode = No. Scale = 1.

Line number format (PIP-style):
```
<SIZE>"-<SERVICE>-<SEQ>-<SPEC>
example: 2"-PW-1001-S40S
         1.5"-CIP-2010-SAN
```

## Tab 01 Lines

| Tool | Block | Command |
|---|---|---|
| Process line | PID-LINE-PROC | PIDLINE |
| Utility line | PID-LINE-UTIL | PIDLINE |
| Sanitary line | PID-LINE-SAN | PIDLINE |
| Jacket / trace | PID-LINE-JKT | PIDLINE |
| Capillary | PID-LINE-CAP | PIDLINE |
| Pneumatic signal | PID-SIG-PN | PIDLINE |
| Electric signal | PID-SIG-EL | PIDLINE |
| Software / DCS | PID-SIG-SW | PIDLINE |
| Flow arrow | PID-ARW-FLOW | PIDFIT |
| Slope arrow | PID-ARW-SLOPE | PIDFIT |
| Spec break | PID-BRK-SPEC | PIDFIT |
| Insulation tick | PID-MRK-INSUL | PIDFIT |
| Heat trace tick | PID-MRK-HT | PIDFIT |
| Off-page connector | PID-OPC | PIDFIT |
| Continuation | PID-CONT | PIDFIT |

## Tab 02 Fittings

| Tool | Block |
|---|---|
| Tee | PID-TEE |
| Wye | PID-WYE |
| Cross | PID-CROSS |
| Conc reducer | PID-RED-CON |
| Ecc reducer FOB | PID-RED-ECC |
| Cap / blind | PID-CAP |
| Union | PID-UNION |
| Flange pair | PID-FLG |
| Spectacle blind | PID-SBLIND |
| Spacer / skid | PID-SPACER |
| Hose | PID-HOSE |
| Hose station | PID-HOSE-STN |
| Y-strainer | PID-STR-Y |
| T-strainer | PID-STR-T |
| Basket strainer | PID-STR-BKT |
| Restriction orifice | PID-RO |
| Steam trap | PID-TRAP |
| Drain / vent | PID-DRAIN |

## Tab 03 Isolation valves

Visibility: NO / NC. Actuator vis: HAND / LEVER / GEAR / CHAIN.

| Tool | Block | ISA body |
|---|---|---|
| Gate | PID-VLV-GATE | bowtie, no marker |
| Ball | PID-VLV-BALL | bowtie + hollow circle |
| Plug | PID-VLV-PLUG | bowtie + solid circle |
| Butterfly | PID-VLV-BFY | two ticks + diagonal disc |
| Knife gate | PID-VLV-KNIFE | bowtie + blade |
| Globe | PID-VLV-GLB | bowtie + solid dot |
| Angle globe | PID-VLV-ANGL | 90° bowtie |
| Needle | PID-VLV-NDL | tapered bowtie |
| Diaphragm | PID-VLV-DIA | bowtie + arc seat |
| 3-way ball | PID-VLV-3WAY | T bowtie |
| 4-way | PID-VLV-4WAY | cross bowtie |
| DBB | PID-VLV-DBB | two gates + bleed |

## Tab 04 Check / relief / specialty

| Tool | Block |
|---|---|
| Swing check | PID-CHK-SW |
| Lift check | PID-CHK-LIFT |
| Wafer check | PID-CHK-WFR |
| PSV / PRV | PID-PSV |
| Angle PSV | PID-PSV-ANG |
| Rupture disc | PID-RD |
| Vacuum breaker | PID-VB |
| Pressure reducing | PID-PRV-REG |
| Backflow preventer | PID-BFP |

## Tab 05 Control valves

Body vis: GLB / BALL / BFY / DIA. Actuator vis: DIA / PISTON / MOV / SOV.
Fail vis: FO / FC / FL. Positioner tick optional.

| Tool | Block |
|---|---|
| Control globe | PID-CV-GLB |
| Control ball | PID-CV-BALL |
| Control butterfly | PID-CV-BFY |
| Control diaphragm | PID-CV-DIA |
| On-off w/ SOV | PID-XV |
| Hand control | PID-HCV |
| Self-contained PCV | PID-PCV |

## Tab 06 Sanitary

Ends default TC. Size lookup 1/4–6 (8/10/12 extra).

| Tool | Block |
|---|---|
| Sanitary line | PID-SAN-LINE |
| Tri-clamp pair | PID-SAN-TC |
| Ferrule | PID-SAN-FER |
| Sanitary 90 | PID-SAN-EL90 |
| Sanitary tee | PID-SAN-TEE |
| Sanitary reducer | PID-SAN-RED |
| Sanitary ball | PID-SAN-BALL |
| Sanitary butterfly | PID-SAN-BFY |
| Sanitary diaphragm | PID-SAN-DIA |
| Sample valve | PID-SAN-SAMP |
| Spray ball | PID-SAN-SPRAY |

## Tab 07 Instruments (minimal ISA-5.1)

Balloon vis: FIELD / LOCAL-BOARD / DCS / PLC / DISCRETE.

| Tool | Default letters |
|---|---|
| Balloon blank | user letters |
| FE / FT / FIT / FIC / FV / FCV | flow |
| PE / PT / PIT / PIC / PI / PSV tag | pressure |
| TE / TT / TIT / TIC / TI | temperature |
| LE / LT / LIT / LIC / LG | level |
| AE / AT / AIT | analysis |
| PDIT / PDT | dP |
| HS / HOA | hand switch |

## Tab 08 Annotation

SIZE / SCH 10S / SCH 40S / SAN / 304L / 316L / SPEC / LINE-NO / NOTE / HOLD / TIE-IN / ISO-BREAK

## Tool properties after Create Tool Palette

- Prompt for rotation: Yes
- Explode: No
- Scale: 1
- Layer: see Standards/LAYERS.md (P-PID-*)
- Aux scale: none
