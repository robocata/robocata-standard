# RoboCata Standard

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Version](https://img.shields.io/badge/Version-1.0-blue.svg)](https://github.com/robocata/robocata-standard/blob/main/CHANGELOG.md)
[![Standard](https://img.shields.io/badge/Standard-March%202026-green.svg)](https://github.com/robocata/robocata-standard/blob/main/pdf/RoboCata-Standard-V1.pdf)

**An Open Global Standard for Cataloging Robots**

---

## Abstract

The RoboCata Standard defines a structured, machine-readable classification and specification framework for cataloging robots across industrial, professional, and consumer domains.

The standard establishes:

- A unified taxonomy of domains, categories, and robot types
- A canonical set of technical specification fields
- Defined coded option values for structured comparison
- A unique robot identification code format
- Conformance requirements for interoperable implementations

The purpose of the RoboCata Standard is to enable comparability, interoperability, and structured aggregation of robot data across manufacturers, researchers, integrators, and digital platforms.

## Why It Matters

- **No universal robot schema exists** — manufacturers, researchers, and platforms each define their own fields
- **Comparison requires structure** — free-text specs cannot be filtered, ranked, or aggregated
- **Interoperability needs codes** — coded values enable cross-platform data exchange
- **Open standards accelerate adoption** — CC BY 4.0 licensing ensures anyone can implement

## Quick Start

A minimal conformant record requires only 6 fields:

```json
{
  "_canonical_version": "1.0",
  "robot_code": "RBC-AR-MD-DAVINCI",
  "info_name": "da Vinci Xi Surgical System",
  "manufacturer_text": "Intuitive Surgical",
  "type": "ARM",
  "domain": "PRO",
  "category": "MED"
}
```

See the [`examples/`](https://github.com/robocata/robocata-standard/tree/main/examples) directory for more complete records.

## Required Fields

| Field | Label | Description |
|---|---|---|
| `robot_code` | Robot Code | Unique identifier (format: `RBC-TT-CC-XXXXXXX`) |
| `info_name` | Robot Name | Full product name |
| `manufacturer_text` | Manufacturer | Company name |
| `type` | Type | Physical form factor (15 codes) |
| `domain` | Domain | Application domain (3 codes) |
| `category` | Category | Primary application category (29 codes) |

## Taxonomy

### Type (15 codes)

Physical form and morphology.

| Code | Name | Description |
|---|---|---|
| ARM | Robotic Arm | Fixed-base manipulator arm |
| MOBI | Mobile Platform | Wheeled or tracked ground robot |
| BIPD | Biped | Bipedal/humanoid walking robot |
| QUAD | Quadruped | Four-legged walking robot |
| HEXA | Hexapod+ | Six or more legged robot |
| AERI | Aerial | Flying robot (drone, VTOL, fixed-wing) |
| AQUA | Aquatic | Underwater/surface water robot |
| SERP | Serpentine | Snake-like, limbless robot |
| SPHR | Spherical | Ball or rolling form factor |
| SOFT | Soft Robot | Soft-bodied, flexible material robot |
| WEAR | Wearable | Body-worn, exoskeleton, prosthetic |
| VEHI | Vehicle | Autonomous vehicle platform |
| APPL | Appliance | Robot built into appliance |
| SWRM | Swarm Unit | Designed for swarm operations |
| HYBR | Hybrid | Hybrid or multi-modal form factor |

### Domain (3 codes)

High-level market segmentation. Each robot belongs to exactly one domain.

| Code | Name | Description |
|---|---|---|
| IND | Industrial & Manufacturing | Factory floors, production lines, heavy industry |
| PRO | Professional & Services | Commercial, professional, and institutional use |
| HOME | Home & Consumer | Residential and personal use |

### Category (29 codes)

Primary application sector, grouped by domain.

**Industrial (5):** Quality Control (QC), Production & Assembly (PROD), Welding & Fabrication (WELD), Heavy Industry (HEAVY), Packaging & Logistics (PACK)

**Professional (15):** Medical & Healthcare (MED), Agricultural (AGR), Construction & Building (CONST), Transportation & Delivery (TRANS), Laboratory & Research (LAB), Hospitality & Food Service (HOSP), Retail & Commerce (RET), Educational (EDU), Infrastructure & Utilities (INFRA), Landscaping & Grounds (LAND), Commercial Cleaning (CLEAN), Security - Professional (SQP), Sports - Professional (SPORTP), Office & Business (OFF), Veterinary (VET)

**Home (9):** Home Cleaning (HCLEAN), Companion & Social (COMP), Entertainment (ENT), Home Security (SQH), Cooking (COOK), Childcare (CARE), Sports - Home (SPORTH), Yard & Outdoor (YARD), Background (Background)

## Robot Code Format

Every robot receives a globally unique RoboCata identifier:

```
RBC-TT-CC-XXXXXXX
 |    |  |    +-- Unique identifier (up to 7 alphanumeric chars)
 |    |  +------- Category code (2 letters)
 |    +---------- Type code (2 letters)
 +--------------- Prefix (always "RBC")
```

**Examples:**
- `RBC-AR-MD-DAVINCI` — Robotic Arm, Medical, da Vinci
- `RBC-MO-TR-STARSHI` — Mobile Platform, Transportation, Starship
- `RBC-AE-AG-DRONESE` — Aerial, Agricultural, DroneSeed
- `RBC-AP-CL-ROOMBAS` — Appliance, Cleaning, Roomba

## Repository Structure

```
robocata-standard/
├── README.md                          # This file
├── LICENSE                            # CC BY 4.0
├── CHANGELOG.md                       # Version history
├── CONTRIBUTING.md                    # How to propose changes
├── CODE_OF_CONDUCT.md                 # Contributor guidelines
├── SECURITY.md                        # Reporting issues
├── docs/
│   ├── specification.md               # Full specification (Sections 1-24)
│   ├── appendix-a-data-types.md       # Data type definitions
│   ├── appendix-b-unit-conventions.md # Unit conventions
│   ├── appendix-c-code-format.md      # Robot Code format
│   ├── conformance.md                 # Conformance requirements
│   └── governance.md                  # Terms, governance, versioning
├── schema/
│   └── robocata.robot.v1.schema.json  # JSON Schema (Draft 2020-12)
├── codelists/                         # Machine-readable coded values
│   ├── type.json                      # 15 type codes
│   ├── domain.json                    # 3 domain codes
│   ├── category.json                  # 29 category codes
│   └── ... (63 codelist files total)
├── examples/
│   ├── robot.minimal.json             # Minimal valid record (6 required fields)
│   ├── robot.industrial-arm.json      # Industrial arm example
│   ├── robot.mobile-platform.json     # Mobile delivery robot example
│   └── robot.home-cleaning.json       # Home consumer robot example
└── pdf/
    └── RoboCata-Standard-V1.pdf       # Official PDF document
```

## Specification Sections

The standard defines fields across 24 sections:

1. Identification & Description
2. Media Requirements
3. Physical Dimensions & Weight
4. Motion & Kinematics
5. Navigation & Localization
6. Power & Energy
7. Performance & Throughput
8. Environment & Operating Conditions
9. Safety & Certifications
10. Connectivity & Communication
11. Control & Programming
12. Software & Operating Systems
13. Sensors & Perception
14. AI & Autonomy
15. Hardware & Actuators
16. Features & Capabilities
17. Installation & Space
18. Commercial & Pricing
19. Support & Maintenance
20. Applications & Use Cases
21. Certifications & Standards
22. Ratings & Metrics
23. Manufacturer & Origin
24. Research & Popularity

See the [full specification](docs/specification) for the complete field reference.

## Validation

Validate a robot record against the schema:

```bash
# Using ajv-cli (Node.js)
npx ajv validate -s schema/robocata.robot.v1.schema.json -d examples/robot.minimal.json

# Using jsonschema (Python)
pip install jsonschema
python -c "
import json, jsonschema
schema = json.load(open('schema/robocata.robot.v1.schema.json'))
record = json.load(open('examples/robot.minimal.json'))
jsonschema.validate(record, schema)
print('Valid!')
"
```

## Separation of Standard and Platform

**robocata.org** — The RoboCata Standard. This open specification, its schema, and governance documentation. Maintained as a public standard.

**robocata.com** — The RoboCata Catalog. A commercial implementation of the standard. The catalog is one of potentially many implementations and does not define the standard.

The standard exists independently of any implementation.

## License

The RoboCata Standard is licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).

You are free to share and adapt the standard for any purpose, including commercial use, provided you give appropriate attribution.

## Contact

- **Standard website:** [https://robocata.org](https://robocata.org)
- **Email:** [standard@robocata.org](mailto:standard@robocata.org)
- **GitHub:** [https://github.com/robocata/robocata-standard](https://github.com/robocata/robocata-standard)

---

*RoboCata Standard V1.0 — March 2026*
