---
layout: default
title: Conformance Requirements
---

# Conformance Requirements

This document specifies the conformance requirements for implementations of the RoboCata Standard V1.0.

## Conformance Definition (Normative)

A robot record shall be considered conformant with RoboCata Standard V1.0 (March 2026) if:

1. **Required Fields** — It contains all six required fields:
   - `robot_code` — Unique RoboCata identifier (format: RBC-TT-CC-XXXXXXX)
   - `info_name` — Full product name
   - `manufacturer_text` — Company name
   - `type` — Physical form factor classification (must use a valid Type code)
   - `domain` — Application domain (must be IND, PRO, or HOME)
   - `category` — Primary application category (must use a valid Category code)

2. **Coded Fields** — All coded fields (single code or list of codes) use only values defined in the codelist files (Appendix E). Custom or undefined codes are not conformant.

3. **Unit Conventions** — All numeric fields follow the unit conventions defined in Appendix B. For example, weight must be in kilograms, dimensions in millimeters, speed in meters per second.

4. **Field Identifiers** — Field names match exactly the canonical field identifiers defined in the specification. Renaming or aliasing fields does not constitute conformance.

5. **Optional Fields** — A conformant implementation may omit non-required fields, but must not redefine or alter field semantics.

## Conformance Claims

Organizations may state:

> "Compatible with RoboCata Standard v1.0"

Provided that:

- Required fields are implemented
- Coded fields use enumerations as defined in the standard
- Units follow the conventions specified

RoboCata may publish optional conformance validation tools in the future. False or misleading claims of compliance may result in public clarification.
