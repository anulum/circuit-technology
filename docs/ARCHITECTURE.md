<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-TECHNOLOGY — repository foundation
-->

# Repository architecture

## Current executable tooling

**What it contains:** the repository's metadata, source-provenance, workflow, dependency-alignment, documentation, inventory and preflight controls.

**What each control does:** it inspects its fixed, declared local scope.

**What received metadata cannot do:** select another acceptance policy or grant domain authority.

Foundation qualification is in progress.

## Intended domain boundaries

| Record | Responsibility | Required evidence |
| --- | --- | --- |
| Facility readiness record | Cleanroom class, electrostatic-discharge controls, Class 3B/4 laser interlocks, toxic-gas monitoring and cryogenic oxygen-deficiency readiness for a laboratory or cell | Verified calibration and person-in-role sign-off before admission of any physical bench or cell task |
| Technology profile | Process node, supply corners, metal stack, SRAM/BIST compilers (`OpenRAM`, `sram22`, `autoMBIST`), edge-target limits, bit widths, bipolar encoding rules, on-chip plasticity capabilities, synchroniser metastability parameters, radiation latch-up/upset bounds, wafer-acceptance-test corners and digest-pinned process-design-kit and post-silicon errata | Digest-pinned open or enclave-mounted process files with explicit compartment tags |
| Prototyping board profile | Board identity (such as `PYNQ-Z2` `xc7z020clg400-1`), utilisation ceiling (`70 %` max), positive timing-slack requirement, admitted toolchain profile and complete inventory of local and network configuration/debug surfaces | Operating-system and firewall surface guards plus real-surface agent-refusal probes before any physical board is attached |
| Leaf-cell binding map | Mapping of abstract platform primitives across four leaf classes (standard logic, clock/reset/synchroniser cells, compiled memories and analogue/physical macros) to target cells | Explicit substitution flags when a prototyping target replaces a physical macro or entropy source |
| Target descriptor semantics | Semantic definition of `technology_kind` paired alongside Evidence Manifest Toolkit's `target_kind` | Conforming adapter descriptors validated through Evidence Manifest Toolkit |

## Board configuration-surface enumeration

- **Every programming and debug path is listed.** A prototyping board profile enumerates USB-JTAG devices, Linux FPGA manager and `devcfg` nodes, Python overlay loaders, board SSH and Jupyter endpoints, vendor `hw_server` (`TCP 3121`) and OpenOCD `telnet`, `GDB` and `Tcl` ports.
- **Built versus physical stages.** Built-stage synthesis and place-and-route against a board profile need no physical board. Connecting a physical board later requires every listed surface to be registered in the equipment clamp registry, guarded by operating-system permissions and firewall rules, and proven closed to unapproved agent access by a live refusal probe.

## Planned record schemas

- `circuit_technology.facility_readiness_record.v1`
- `circuit_technology.technology_profile.v1`
- `circuit_technology.prototyping_board_profile.v1`
- `circuit_technology.leaf_cell_binding_map.v1`

These are planned identifiers. None of them is registered or qualified here.

Read [validation tooling](validation-tooling.md) for the executable repository interfaces.
