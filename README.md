# Stochastic Agent-Based Model of Tumor–Normal Cell Interactions

A NetLogo agent-based prototype comparing how **tumor** and **normal** cells behave under changing microenvironmental conditions (hypoxic core vs normoxic surroundings), with a focus on glucose–lactate dynamics and cellular stress.

Developed at the **Department of Biochemistry, AIIMS Delhi**, under scientist mentorship (Mathematical and Computational Biochemistry Lab).

> **Status: working prototype.** Outputs are implementation diagnostics, not validated biological conclusions.

## Biological basis
Inspired by the metabolic symbiosis concept in Jayathilake et al. (2024), *PLOS Computational Biology*: hypoxic cells rely on glycolysis and produce lactate, while better-oxygenated cells may take up lactate and use oxidative metabolism.

![Metabolic framework](metabolic_framework.png)

GLUT1-mediated glucose uptake and MCT1-associated lactate transport are literature mechanisms; they are **not yet explicitly parameterized** as transporter kinetics in this prototype.

## Model architecture
Agent-based + patch-based hybrid:
- **Agents:** tumor cells, normal cells (cell age, stress, metabolic state) and stress signals (random movement, source, age, decay lifetime)
- **Patches:** oxygen, glucose and lactate fields; hypoxic core with normoxic surroundings

![Model architecture](model_architecture.png)

## One simulation tick
Move → Sense → Interact → Update → Divide / Die. Cell-cycle delay (hatching time) and signal lifetime (decay time) act as timing rules.

![Simulation workflow](simulation_workflow.png)

## Running the model
1. Install [NetLogo](https://ccl.northwestern.edu/netlogo/) (model saved in NetLogo 7.0.4).
2. Download `Tumor_Normal_ABM.nlogox` and open it in NetLogo.
3. Press **Setup**, then **Go**.

| Control | Default |
|---|---|
| Initial tumor cells | 100 agents |
| Initial normal cells | 60 agents |
| Initial glucose | 5 mM |
| Hypoxic-core oxygen | 3 (model setting) |
| Normoxic oxygen | 40 (model setting) |

World: 33 × 33 patches (wrapping on). Population caps: tumor 400, normal 300.

![NetLogo interface](netlogo_interface.png)

## Preliminary observations (implementation diagnostics)
Populations rise then plateau (likely cap-influenced); glucose stays near baseline; lactate falls then flattens; stress stays near zero because signal exposure is weak relative to recovery.

![Preliminary observations](preliminary_observations.png)

## Assumptions and limitations
- Cell counts are agents, not cells/mL; glucose and lactate are patch concentrations (mM)
- Oxygen slider units need explicit definition
- Uptake, release and division probabilities are provisional
- Tick duration and patch volume are not yet defined for calibrated rates
- Calibration and replicate runs are required

![Parameters and assumptions](parameters_assumptions.png)

## Next steps
Split outputs by cell type × oxygen region · region-specific glucose/lactate plots · calibrate signal-response rules · concentration-gradient diffusion · define patch volume, tick duration and rate units · add GLUT1/MCT1 intervention only after baseline validation.

![Status and next steps](status_next_steps.png)

## Reference
Jayathilake PG et al. (2024). Metabolic symbiosis between oxygenated and hypoxic tumour cells: An agent-based modeling study. *PLOS Computational Biology*.

## Author
Khushi Sharma — B.Tech Bioinformatics (AI/ML), IILM University
