<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-TECHNOLOGY — repository foundation
-->

# Architecture

## Current executable surface

The checkout contains:
- repository validation tooling;
- dedicated tests;
- workflow definitions;
- native documentation.

No domain component of Circuit Technology is implemented yet. The metadata keeps domain capabilities, claims and qualified record formats empty.

## Intended data flow

1. **Facility readiness** records cleanroom, electrostatic-discharge, laser, toxic-gas and oxygen-deficiency interlock state for admission gates.
2. **Initial technology and board profiles** bind process corners, errata digests, SRAM compilers, leaf-cell maps and board resource/surface constraints from admitted operation profiles.
3. **Downstream consumption** supplies immutable profile digests to digital, analogue, mixed-signal, physical, assembly, device, field, photonic, prototyping, lab, learning, flow and manufacturing steps.
4. **Post-silicon profile updates** incorporate approved compact-model updates, scribe-line electrical-test corner shifts and silicon errata workarounds as new versioned profiles.

## Ownership

**This project owns** the planned Circuit Technology records and boundary rules.

**Owned elsewhere:**

| Responsibility | Owner |
|---|---|
| contracts, admission and approval verification | Circuit Core |
| target-descriptor schema bytes and shared manifest tooling | Evidence Manifest Toolkit |
| equipment input-surface clamp registry | Circuit Automation |
| FPGA intake, partitioning and board runs | Circuit Prototyping |
| compact-model extraction and device studies | Circuit Devices |

## Interpretation

- **Profiles.** A profile describes constraints and capabilities; it is not a synthesis, timing or silicon measurement.
- **Built-stage targets.** Fitting a board profile in tools does not prove physical board behaviour.

Read [the documentation architecture](docs/ARCHITECTURE.md) for the planned records, domain rules and schema identifiers.
