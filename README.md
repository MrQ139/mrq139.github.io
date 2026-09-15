# 139 — Aerospace Propulsion Research Portfolio

I am an aerospace engineering master's researcher focusing on pintle injectors, spray-combustion correlation, experimental data quality, and physics-informed digital twin workflows.

Current technical interests:

- Pintle injector cold-flow and hot-fire data correlation
- Spray angle, breakup, atomization, and combustion-performance linkage
- Orifice flowmeter design and calibration for repeatable experiments
- Obsidian-based engineering note automation
- CFD and machine-learning assisted propulsion research workflows

## Research Direction

My current research direction is to build a reliable experimental foundation first, then expand toward CFD/ML-assisted modeling.

The near-term priority is experimental repeatability:

1. establish stable cold-flow measurement procedures
2. validate flowmeter and pressure measurement quality
3. correlate spray characteristics with operating conditions
4. extend the workflow toward hot-fire data
5. prepare structured datasets for future digital-twin modeling

The long-term direction is a hybrid digital-twin workflow where spray behavior is constrained by physics-based modeling and combustion behavior is supported by data-driven prediction.

## Repository Map

### FormulaLab

Interactive engineering-equation visualizer for Obsidian notes.

Use case:

- visualize Reynolds number, Weber number, momentum ratio, and other engineering equations inside Markdown notes
- support fast conceptual reasoning during study and research logging
- connect formulas, sliders, and plots inside a local research note system

Repository:

- `MrQ139/FormulaLab`

### Orifice Flowmeter

Python CLI, library, and Streamlit GUI for orifice flowmeter design and calibration.

Use case:

- estimate flow rate from pressure drop
- size an orifice bore for a target flow condition
- calibrate discharge coefficient using reference flow data
- support repeatable cold-flow and propulsion test-bench measurements

Repository:

- `MrQ139/Orifice-Flowmeter` (private)

### OpenFOAM Automation

Local workflow project for OpenFOAM case generation, execution, validation, and dashboard integration.

Use case:

- build repeatable CFD workflows
- reduce manual case setup errors
- connect solver execution, validation, and documentation
- prepare future automation using LLM agents and structured runbooks

Repository:

- `MrQ139/openfoam-automation-tool` (private)

Status:

- active development
- distributed as a Windows release package; ParaView-based approval gates

### Injector Cold-Flow Supply Line Test Rig

Browser-based digital test rig for an injector cold-flow supply line.

Use case:

- inspect the supply-line P&ID interactively
- review STEP geometry and exploded part views in the browser
- preview atomization state and spray/momentum behaviour alongside the hardware layout

Repository:

- `MrQ139/procolab-coldflow-supplyline-simulator`

Live:

- https://mrq139.github.io/procolab-coldflow-supplyline-simulator/

## Working Philosophy

The main principle is not to maximize the number of repositories, but to keep each repository tied to a clear research function.

```text
Research question
  -> experimental data quality
  -> repeatable calculation tools
  -> CFD/automation workflow
  -> structured dataset
  -> future ML/digital-twin model
```

## Current Priority

The current priority is to keep the GitHub portfolio focused around three axes:

1. **Experimental support tools** — orifice flowmeter and calibration utilities
2. **Knowledge-system tools** — Obsidian-based formula visualization
3. **CFD automation** — OpenFOAM workflow automation and validation

Temporary AI experiments and empty sandbox repositories should remain private, archived, or excluded from the public portfolio.
