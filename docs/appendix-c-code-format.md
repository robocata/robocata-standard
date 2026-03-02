---
layout: default
title: "Appendix C: Code Format"
---

# Appendix C: RoboCata Code Format

Every robot in the RoboCata Standard is assigned a unique identification code following this format:

```
RBC-TT-CC-XXXXXXX
```

## Structure

| Segment | Length | Description |
|---|---|---|
| RBC | 3 | Fixed prefix identifying a RoboCata code |
| TT | 2 | Type code (from the Type table) |
| CC | 2 | Category code (from the Category table) |
| XXXXXXX | up to 7 | Unique identifier (alphanumeric, derived from product name) |

## Type Codes (TT)

| Type | RBC Code |
|---|---|
| Robotic Arm | AR |
| Mobile Platform | MO |
| Biped | BI |
| Quadruped | QU |
| Hexapod+ | HE |
| Aerial | AE |
| Aquatic | AQ |
| Serpentine | SE |
| Spherical | SP |
| Soft Robot | SO |
| Wearable | WE |
| Vehicle | VE |
| Appliance | AP |
| Swarm Unit | SW |
| Hybrid | HY |

## Category Codes (CC)

| Category | RBC Code |
|---|---|
| Quality Control | QC |
| Production & Assembly | PR |
| Welding & Fabrication | WL |
| Heavy Industry | HV |
| Packaging & Logistics | PK |
| Medical & Healthcare | MD |
| Agricultural | AG |
| Construction & Building | CN |
| Transportation & Delivery | TR |
| Laboratory & Research | LB |
| Hospitality & Food Service | HS |
| Retail & Commerce | RT |
| Educational | ED |
| Infrastructure & Utilities | IF |
| Landscaping & Grounds | LD |
| Commercial Cleaning | CL |
| Security (Professional) | SQ |
| Sports (Professional) | ST |
| Office & Business | OF |
| Veterinary & Animal Care | VT |
| Home Cleaning | HC |
| Yard & Garden | YD |
| Kitchen & Cooking | CK |
| Entertainment & Gaming | EN |
| Companion | CM |
| Personal Care | CR |
| Home Security | SH |
| Sports & Fitness (Home) | SF |
| Childcare & Education | CH |

## Examples

| Robot | Code | Breakdown |
|---|---|---|
| ABB IRB 1400 (Industrial Arm, Production) | RBC-AR-PR-IRB1400 | AR = Robotic Arm, PR = Production |
| Spot Enterprise (Quadruped, Infrastructure) | RBC-QU-IF-SPOTENT | QU = Quadruped, IF = Infrastructure |
| Roomba j7+ (Appliance, Home Cleaning) | RBC-AP-HC-ROOMBAJ | AP = Appliance, HC = Home Cleaning |
| DJI Matrice 300 (Aerial, Transportation) | RBC-AE-TR-DJIMATR | AE = Aerial, TR = Transportation |
