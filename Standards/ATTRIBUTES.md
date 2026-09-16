# P&ID attribute and dynamic-block schema

Every piping / fitting / valve block carries these attributes.
Insert default values; drafter edits on place or via Properties.

| Tag | Prompt | Default | Example |
|---|---|---|---|
| TAG | Equipment / valve tag | — | HV-1001, FV-201, PSV-301 |
| LINE | Line number | — | 2"-PW-1001-S40S |
| SIZE | NPS or tube OD | 2 | 1/4 … 18 |
| SCH | Schedule / sanitary | 40S | 10S, 40S, SAN |
| SPEC | Piping spec | S40S | plant spec code |
| MATL | Material | 316L | 304, 304L, 316, 316L |
| END | End connection | BW | BW, SW, THD, FLG, TC |
| RATING | Pressure class | 150 | 150, 300, sanitary |
| INSUL | Insulation / trace | NONE | INS, HT, ST, NONE |
| FAIL | Fail position (actuated) | — | FO, FC, FL |
| POS | Normal position | NO | NO, NC, LO, LC |
| VIEW | Symbol set | PID | PID |
| NOTES | Free | — | |

## Line number convention

```
<SIZE>"-<SERVICE>-<SEQ>-<SPEC>
```

Suggested service codes for SS utility / process:

| Code | Service |
|---|---|
| PW | process water / potable |
| CW | chilled water |
| HW | hot water |
| ST | steam |
| SC | steam condensate |
| CA | compressed air |
| IA | instrument air |
| N2 | nitrogen |
| CIP | clean-in-place |
| SIP | steam-in-place |
| WFI | water for injection |
| P | process product |
| DR | drain |
| VE | vent |

SPEC token examples: `S10S` `S40S` `SAN` `BPE`.

## Dynamic-block parameters (BEDIT recipe)

Master blocks (one per family, not one per size):

| Master | Lookup | Visibility | Other |
|---|---|---|---|
| PID-LINE-DYN | SIZE, SCH, SERVICE | PROC / UTIL / SAN / JKT | Stretch LEN; linetype by vis |
| PID-FIT-DYN | SIZE, SCH | TEE / WYE / CROSS / RED-CON / RED-ECC / CAP / FLG / UNION / STR-Y / TC | Flip branch |
| PID-VLV-DYN | SIZE, SCH, END | GATE / GLB / BALL / PLUG / BFY / CHK / DIA / NDL / 3WAY / KNIFE | Flip flow; vis NO/NC (hatch) |
| PID-ACT-DYN | — | HAND / LEVER / GEAR / DIA / PISTON / MOV / SOV | vis FAIL FO/FC/FL |
| PID-CV-DYN | SIZE | GLB / BALL / BFY / DIA | compose with PID-ACT |
| PID-SAN-DYN | TUBE-OD | TUBE / EL90 / TEE / TC / BALL / BFY / DIA | END locked TC |
| PID-INST-DYN | LETTERS | FIELD / BOARD / DCS / PLC | attr TAG + LOOP |

SIZE lookup list:
1/4 3/8 1/2 3/4 1 1-1/4 1-1/2 2 2-1/2 3 3-1/2 4 5 6 8 10 12 14 16 18

Sanitary tube OD list (geometry does not scale; attr only):
1/4 3/8 1/2 3/4 1 1-1/2 2 2-1/2 3 4 6 (+ 8 10 12 extra)

## Layers

| Layer | Color | Linetype | Use |
|---|---|---|---|
| P-PID-LINE | 4 cyan | CONTINUOUS | Process / utility pipe |
| P-PID-LINE-SAN | 3 green | CONTINUOUS | Sanitary |
| P-PID-LINE-JKT | 30 | HIDDEN2 | Jacket / trace |
| P-PID-SIG-PN | 6 | PHANTOM2 | Pneumatic |
| P-PID-SIG-EL | 1 | DASHED | Electric |
| P-PID-VALVE | 1 red | CONTINUOUS | Valves |
| P-PID-FITTING | 6 magenta | CONTINUOUS | Fittings |
| P-PID-INST | 2 yellow | CONTINUOUS | Balloons |
| P-PID-ANNO | 7 | CONTINUOUS | Tags, line numbers |
| P-PID-EQPM | 5 blue | CONTINUOUS | Equipment outline |

Aliases: PID-LINE PID-VALVE PID-FIT PID-INST PID-ANNO

## Naming

```
PID-{FAMILY}-{TYPE}[-END][-ACT]
```

Examples: `PID-VLV-BALL` `PID-VLV-GATE-NC` `PID-CV-GLB-DIA-FC` `PID-SAN-TC` `PID-TEE` `PID-INST-FIT`

Do not bake SIZE into the block name. Size lives on the SIZE attribute / lookup.
