---
layout: default
title: Terms of Use & Governance
---

# Terms of Use & Governance

## 1. Status of the RoboCata Standard

The RoboCata Standard ("Standard") is an open, publicly documented classification and field reference framework for describing robots.

- Current version: **Version 1.0 (March 2026)**
- Document title: *RoboCata – Complete Field Reference*
- Maintained by: Martin Smit (standard@robocata.org)
- Standards website: https://robocata.org or https://github.com/robocata/robocata-standard

The Standard is published to enable interoperability, comparability, and structured robot data exchange across the robotics ecosystem.

The Standard is distinct from the RoboCata catalog database hosted at robocata.com.

## 2. Open Standard License

**You may:**

- Use the RoboCata field structure and taxonomy
- Implement the schema in your own systems
- Build APIs compatible with the RoboCata Standard
- Reference and cite the Standard
- Create derivative schemas or extensions

**Provided that:**

- You clearly reference the version used (e.g., "RoboCata Standard v1.0")
- You do not imply endorsement by RoboCata unless formally agreed
- You do not misrepresent modified versions as the official Standard

The RoboCata Standard text and schema are licensed under Creative Commons Attribution 4.0 (CC BY 4.0).

The RoboCata Standard is free to implement. Commercial use is permitted. Redistribution of modified versions must clearly indicate deviations from the official specification.

## 3. Intellectual Property

The RoboCata name and logo are proprietary. The Standard itself (field names, structures, codes) is open for implementation under the terms above.

## 4. Versioning & Governance

### Versioning Model

- V1.x — backward-compatible updates
- V2.0 — structural or breaking changes
- Minor updates (typos, clarifications) do not change V1
- Minor updates (V1.x) may introduce new optional fields but shall not alter or remove existing field semantics. Field deletions or major field updates require major version increment
- Each official version is date-stamped
- Archived versions remain publicly accessible

### Change Process

Changes to the RoboCata Standard may be proposed by any stakeholder. Proposed changes are reviewed by the Editor and, where appropriate, incorporated into minor or major version updates. Minor updates shall maintain backward compatibility. Major version updates may introduce structural changes with documented migration guidance.

Proposals must include:

- Field impact
- Backward compatibility assessment
- Rationale
- Example implementation

The maintainer retains final authority over acceptance into official versions. Future governance models (e.g., advisory board or community review panel) may be introduced as adoption grows.

## 5. Conformance & Claims

Organizations may state:

> "Compatible with RoboCata Standard v1.0"

Provided that:

- Required fields are implemented
- Coded fields use enumerations and conventions as per this standard

RoboCata may publish optional conformance validation tools in the future. False or misleading claims of compliance may result in public clarification.

## 6. Separation from RoboCata Catalog

The RoboCata Standard is a specification framework and is independent of any specific database, website, or commercial implementation.

The RoboCata catalog available at https://robocata.com is one implementation of the RoboCata Standard. Other organizations may implement the standard independently without affiliation, permission, or partnership with the RoboCata catalog platform.

The RoboCata Standard is open and licensed under Creative Commons Attribution 4.0 (CC BY 4.0).

The RoboCata catalog dataset at robocata.com is proprietary unless explicitly licensed otherwise.

Use of the RoboCata Standard does not grant any rights to access, scrape, replicate, redistribute, or commercially exploit the RoboCata catalog dataset.

Conformance to the RoboCata Standard does not require use of the RoboCata website, database, infrastructure, or services.

## 7. Limitation of Liability

The Standard is provided "as is". RoboCata makes no guarantees regarding:

- Completeness
- Suitability for specific applications
- Regulatory compliance
- Safety certification interpretation

Implementers are responsible for validating data before operational use.

## 8. Future Development

The Standard is intended to evolve alongside robotics innovation.

Possible future directions:

- API specification (OpenAPI format)
- JSON Schema publication
- Machine-readable code registries
- Validation tools

## 9. Contact & Feedback

Feedback and proposals may be submitted via https://robocata.org or the official GitHub repository at https://github.com/robocata/robocata-standard.
