<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-TECHNOLOGY — repository foundation
-->

# Decision: centralise process, leaf-cell, board and facility descriptors in one solver-free technology layer

## Context

Digital, analogue, physical, assembly, prototyping, device, field, photonic, lab and manufacturing flows all depend on the same silicon process parameters, SRAM/leaf bindings, board pin/surface definitions and facility safety state. Scattering target constants across solver repositories causes silent corner drift.

## Decision

**What Circuit Technology owns:**
- facility readiness record;
- technology profile;
- prototyping board profile;
- leaf-cell binding map;
- target descriptor semantics;

**What it imports:** only Circuit Core. Fourteen circuit repositories import Circuit Technology, and SC-NC Hardware registers against it.

**Owned elsewhere:**

| Responsibility | Owner |
|---|---|
| contracts, admission and approval verification | Circuit Core |
| target-descriptor schema bytes and shared manifest tooling | Evidence Manifest Toolkit |
| equipment input-surface clamp registry | Circuit Automation |
| FPGA intake, partitioning and board runs | Circuit Prototyping |
| compact-model extraction and device studies | Circuit Devices |

## Consequences

**What can be qualified now:** repository governance and validation tooling, before domain code exists.

**What it cannot qualify:** unimplemented schemas, solvers, hardware or sign-off verdicts.

**Architectural consequences:**
- Circuit Technology imports only Circuit Core and holds all target, leaf, board and facility descriptors in one place;
- adding a profile remains a pure data declaration and never implies hardware, cloud or foundry availability;
- semantic ownership of target descriptors stays aligned with Evidence Manifest Toolkit without duplicating manifest code.
