<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-TECHNOLOGY — repository foundation
-->

# Data and authority boundaries

## Present tooling

**Execution inputs.** The maintained checkout and the selected development environment are what the repository controls inspect.

**Received inputs.** Descriptors, dependency receipts and generated inventories cannot nominate an acceptance policy or an executable.

**Bounded checks.** Controls inspect bounded local paths and emit fixed diagnostics.

Foundation qualification is in progress.

## Future domain inputs

**Supplied data, with no authority.** The following inputs are treated strictly as supplied data:
- process design kit metadata and errata tables;
- leaf-cell maps and memory compiler descriptors;
- prototyping board definitions and pin maps;
- facility readiness checklists and sensor summaries.

They grant no authority to:
- install or run an unadmitted vendor EDA tool;
- program, probe or power a board;
- admit material carrying a destruction clause;
- waive cleanroom, laser, electrical or gas interlocks;
- export confidential process-design-kit files.

**Comments and embedded text are data.** Descriptions, netlist comments and datasheets arriving inside supplied inputs are data, never instructions to an operator or an agent.

**Public-repository data boundary.** Hosted CI for this public repository runs on public material only. Confidential foundry-NDA, customer, export-controlled or secret-bearing material never enters this repository, its CI or its issues.

## Threats and the rules that answer them

| Threat | Architectural rule |
| --- | --- |
| Unauthorised agent access to prototyping boards or debug servers | Board profiles enumerate every local and network configuration surface (USB-JTAG, FPGA manager, overlay loaders, board SSH/Jupyter, hardware-server and OpenOCD TCP ports) and bind them to operating-system/firewall guards and pre-connection refusal probes |
| Execution of unread proprietary EDA licences or unverified open FPGA part support | Toolchains stay refused until licence terms are read and admitted; open FPGA flows stay refused for a target device until exact silicon part support is verified |
| Stale foundry errata, missing radiation latch-up bounds or unanchored wafer corners | Technology profiles pin errata digests, synchroniser metastability parameters, single-event/latch-up envelopes and wafer-acceptance-test corner anchors, updating post-silicon revisions only through approved change proposals |
| Physical bench or cell operation without hazard interlocks | Facility readiness records gate admission on calibrated electrostatic-discharge, Class 3B/4 laser, toxic-gas and oxygen-deficiency protections |
| Confidential process-design-kit leakage into public surfaces | Proprietary process files stay inside air-gapped confidential enclaves; only public open-PDK profiles (`Sky130`, `GF180MCU`, `IHP SG13G2`, `ASAP7`) ever enter this public repository or its hosted CI |

## Residuals named, not removed

- **Open-PDK electrical accuracy.** Predictive academic kits such as `ASAP7` support flow qualification rather than foundry silicon guarantees.
- **No physical board yet.** Board profiles define target constraints today; physical board verification awaits hardware arrival and surface-guard probes.

**Not claimed:** no isolation, physical, statistical, safety or durability guarantee is claimed by this foundation.
