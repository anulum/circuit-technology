<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-TECHNOLOGY — repository foundation
-->

# Circuit Technology

Circuit Technology is being built as the single repository that holds semiconductor process technology profiles, four-class leaf-cell bindings, prototyping board profiles, target descriptor semantics and laboratory or cleanroom facility readiness records. No physical prototyping board is present yet. This checkout contains repository validation tooling and documentation only. Full foundation qualification is in progress. There is no installed technology-profile package, leaf-cell binder, board-profile loader or qualified facility record.

Circuit Technology is part of the **SC Neuromorphic Computing Systems** group (SC-NEUROMORPHIC-COMPUTING-SYSTEMS). The [group and project map](https://github.com/anulum/sc-neurocore/blob/main/docs/ecosystem.md) shows the whole programme and where this repository sits in it.

**What does not exist yet:**
- a technology-profile, leaf-binding, board-profile or facility-readiness package;
- a registered runtime record schema;
- a connected prototyping board, foundry shuttle slot or qualified process design kit mount.

## Boundary

**What this project owns:**

| Record | Scope |
|---|---|
| Facility readiness record | Cleanroom class, electrostatic-discharge controls, Class 3B/4 laser interlocks, toxic-gas monitoring and cryogenic oxygen-deficiency readiness for a laboratory or cell |
| Technology profile | Process node, supply corners, metal stack, SRAM/BIST compilers (`OpenRAM`, `sram22`, `autoMBIST`), edge-target limits, bit widths, bipolar encoding rules, on-chip plasticity capabilities, synchroniser metastability parameters, radiation latch-up/upset bounds, wafer-acceptance-test corners and digest-pinned process-design-kit and post-silicon errata |
| Prototyping board profile | Board identity (such as `PYNQ-Z2` `xc7z020clg400-1`), utilisation ceiling (`70 %` max), positive timing-slack requirement, admitted toolchain profile and complete inventory of local and network configuration/debug surfaces |
| Leaf-cell binding map | Mapping of abstract platform primitives across four leaf classes (standard logic, clock/reset/synchroniser cells, compiled memories and analogue/physical macros) to target cells |
| Target descriptor semantics | Semantic definition of `technology_kind` paired alongside Evidence Manifest Toolkit's `target_kind` |

**Static imports:** only Circuit Core. Fourteen circuit repositories import Circuit Technology, and SC-NC Hardware registers against it.

**Records read without importing domain code:**

| Source | Records consumed |
|---|---|
| Circuit Core | entity references, data-handling profiles, operation profiles and person approvals |
| Circuit Automation | equipment profiles and state observations |
| Circuit Devices | approved compact-model candidates |
| Circuit Lab | measurement associations |
| Circuit Manufacturing | change proposals, wafer-sort scribe-line distributions and corrective-action errata |

**Capability registration and handoffs:** Registers its technology, leaf-cell and board-profile manifest with Circuit Core, owns the semantic definition of the target descriptor view hosted in Evidence Manifest Toolkit, and receives generic leaf and board profiles split from SC-NeuroCore.

**Explicit non-claims and operating boundaries:**
- Adding a technology or board profile never implies cloud FPGA rental, foundry shuttle access, cleanroom readiness or silicon availability.
- It runs no synthesis, place-and-route, circuit simulation or board programming itself.
- Proprietary vendor toolchains stay refused until their licence terms are read and admitted; open FPGA flows stay refused for a silicon part until exact part support is verified.
- Material carrying a contractual obligation to destroy on expiry is refused at intake under current owner policy.

## Current tooling

Repository controls inspect:
- metadata and source attribution;
- workflows and dependency alignment;
- native documentation and repository inventory;
- preflight orchestration.

Metadata declares architecture-only maturity with empty implemented domain capability and claim inventories.

- Use the exact environment in [Contributing](CONTRIBUTING.md).
- Full CI and preflight belong in CI or in an explicitly admitted pre-push environment.
- See [Validation](VALIDATION.md) for the maintained validation scope.

## Intended evidence

Every future domain artefact will carry the platform's common provenance envelope, its source and environment digests, its confidentiality compartment and its explicit verification boundary. None of the planned record schemas is registered or qualified by this foundation.

## Documentation and support

Read [Architecture](ARCHITECTURE.md), [support](SUPPORT.md), [security reporting](SECURITY.md) and [citation metadata](CITATION.cff).

**Not claimed:**
- a hosted service, released package or DOI;
- a public CI status;
- a performed simulation, hardware measurement or sign-off verdict.

## Licence

Source is licensed under [AGPL-3.0-or-later](LICENSE). A commercial licence is available through the contact in [NOTICE](NOTICE.md).

![ANULUM](docs/assets/anulum_logo_company.jpg)

![Fortis Studio](docs/assets/fortis_studio_logo.jpg)

## Text and data mining reservation
The rightsholder, Miroslav Šotek (ANULUM), expressly reserves the use of the
works in this repository for text and data mining, including the collection of
this content for, and its use in, training, fine-tuning or evaluating machine
learning and artificial intelligence models, in accordance with Article 4(3) of
Directive (EU) 2019/790 and the national provisions transposing it.

No permission for such use has been granted beyond what the licence in
`LICENSE` grants. This reservation does not change that licence: uses the
licence permits remain permitted on its terms, including its attribution and
share-alike conditions.

Reservation made on 2026-11-22. Requests for permission: contact the
rightsholder through the contact listed in this repository.
