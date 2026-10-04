# 139 — Aerospace Propulsion Research Portfolio

I am an aerospace engineering master's researcher at the Propulsion and Combustion Laboratory (ProCo Lab), Korea Aerospace University. My work focuses on pintle injectors, spray atomization, experimental data quality, and CFD-assisted spray analysis.

Current technical interests:

- Pintle and coaxial gas–liquid injector cold-flow experiments
- Spray angle, liquid-sheet breakup, droplet size (SMD), and their link to momentum ratios (TMR, LMR, q, We)
- High-speed imaging analysis of sprays and jets in crossflow
- Agentic CFD workflows on OpenFOAM, currently for spray problems
- Obsidian-based engineering notes and tools

## Research Direction

Build a reliable experimental foundation first, then extend it toward CFD- and data-assisted modeling.

1. run repeatable cold-flow experiments with a single control and logging program
2. predict supply-line operating points and calibrate the model against measurements
3. extract spray quantities from high-speed images with recorded, reproducible settings
4. turn CSV data into experiment tables, reports, and paper-ready figures
5. compare measurements with CFD (VOF/LPT, LES) and correlations

The long-term direction is a hybrid digital-twin workflow where spray behavior is constrained by physics-based modeling and supported by measured data.

## Repository Map

```text
procolab-sqspray            run the experiment, predict the supply line
      │  CSV, HELOS, .cine
      ▼
procolab-image-analysis     spray images: static and dynamic
procolab-data-agent         CSV → tables → reports and paper figures
      │
      ▼
QFD                         OpenFOAM agentic CFD, compared with experiments
```

### 1. Spray Experiment — `procolab-sqspray` (private)

Control and prediction for the lab's spray test rig.

- **SQSPRAYINTEGRATION**: Windows program that runs one experiment as a single timeline — pressure DAQ, valves, Coriolis flowmeters, laser-diffraction sizing, and high-speed camera trigger — and logs each run
- **Supply-line simulator** (`supplyline/`): P&ID-based 1-D line solver, pintle spray design checker, and orifice flowmeter design / discharge-coefficient calibration engine

### 2. Image Analysis — `procolab-image-analysis` (private)

Quantitative analysis of high-speed spray images.

- Static: time-averaged images, spray angle, liquid-sheet length, jet-in-crossflow penetration trajectory compared with Wu et al. (1997)
- Dynamic: instantaneous shape time series, FFT, DMD/POD (in progress)
- Runs as Claude Code skills today; standalone Python / executable planned

### 3. Data and Reports — `procolab-data-agent` (private)

From raw CSV to experiment tables and reports.

- Weber number, momentum flux ratio, and momentum ratios against x50 and SMD
- Korean lab-format reports (A4) and slide decks, with PDF export
- Planned: conversational post-processing and paper-ready figure styles

### 4. CFD — `QFD` (private)

Agentic CFD program built on OpenFOAM for Windows.

- Problem definition → mesh → solver plan → monitoring → post-processing and validation, with a user approval gate at each step
- Works with the user's own LLM API key; no developer tools needed at runtime
- Current focus: spray problems such as liquid jet in crossflow (VOF-LPT, LES)

### 5. Obsidian Plugins

Tools for engineering notes in Obsidian.

- [`obsidian-formulalab`](https://github.com/MrQ139/obsidian-formulalab) (public): interactive formula plots, animated textbook flows, and teaching-scale finite-volume and 2-D Navier–Stokes blocks inside notes
- `obsidian-q-assistant` (private): vault-scoped sidebar assistant that works with Codex, Claude Code, Gemini, or OpenAI and can write FormulaLab blocks

## Working Principles

- One repository per research function
- Raw data is never overwritten; every result keeps the settings that produced it
- Tools must run on another lab Windows PC from a GitHub download alone
