Stochastic Agent-Based Model of Tumor–Normal Cell Interactions

A NetLogo-based stochastic agent-based prototype exploring interactions between tumor and normal cells under changing tumor microenvironmental conditions, particularly hypoxic core and normoxic surroundings. The model focuses on glucose–lactate dynamics, cellular stress, metabolic behavior, and population changes.

Developed at the Department of Biochemistry, AIIMS Delhi, under scientist mentorship (Mathematical and Computational Biochemistry Lab).

Project Status: Working prototype. Current outputs represent implementation diagnostics and should not be interpreted as validated biological conclusions.

1. Biological Basis

Inspired by the metabolic symbiosis concept described in Jayathilake et al. (2024), PLOS Computational Biology.

The model considers:

* Hypoxic tumor cells relying on glycolysis and producing lactate.
* Better-oxygenated cells potentially taking up lactate and utilizing oxidative metabolism.
* Glucose and lactate availability within the tumor microenvironment.

GLUT1-mediated glucose uptake and MCT1-associated lactate transport are literature-supported mechanisms but are not yet explicitly parameterized as transporter kinetics in the current prototype.

2. Model Architecture

The model follows a hybrid agent-based and patch-based approach.

Agents:

* Tumor cells
* Normal cells
* Stress signals

Cell agents incorporate attributes such as age, stress, and metabolic state. Stress signals have random movement, source, age, and decay lifetime.

Patch-based microenvironment:

* Oxygen distribution
* Glucose concentration
* Lactate concentration
* Hypoxic core and normoxic surroundings

3. Simulation Workflow

Each simulation tick follows five major stages:

1. Move: Cells and signals undergo random movement.
2. Sense: Agents interact with local oxygen, glucose, lactate, and signals.
3. Interact: Stochastic signal encounters and cellular responses occur.
4. Update: Metabolism, stress, cell age, and survival states are updated.
5. Divide / Die: Probabilistic cell fate and signal decay are processed.

Cell-cycle delay (hatching time) and individual signal lifetime (decay time) are incorporated as timing rules.

4. Model Interface

The NetLogo interface provides adjustable parameters, a spatial simulation environment, and live plots for monitoring population and metabolic dynamics.

5. Running the Model

Requirements:

* NetLogo 7.0.4
* My_ABM_Model.xml

Steps:

1. Install NetLogo from https://ccl.northwestern.edu/netlogo/
2. Download the model file My_ABM_Model.xml from this repository.
3. Open the model file in NetLogo.
4. Click Setup to initialize the simulation.
5. Click Go to start the simulation.
6. Adjust the available sliders to explore different microenvironmental conditions.

6. Default Model Parameters

Parameter	Default Value
Initial tumor cells	100 agents
Initial normal cells	60 agents
Initial glucose	5 mM
Hypoxic-core oxygen	3 (model setting)
Normoxic oxygen	40 (model setting)
World dimensions	33 × 33 patches
Tumor population cap	400 agents
Normal population cap	300 agents

7. Preliminary Observations

The current simulation run shows the following implementation-level patterns:

* Cell populations: Rise and subsequently plateau, potentially influenced by population caps.
* Glucose: Remains nearly constant around baseline levels.
* Lactate: Initially decreases and subsequently stabilizes.
* Cellular stress: Both traces remain close to zero, suggesting weak signal exposure relative to recovery in the current configuration.

These observations are implementation diagnostics, not evidence of validated biological outcomes.

8. Assumptions and Limitations

* Cell counts represent agents, not cells/mL.
* Glucose and lactate are represented as patch concentrations (mM).
* Oxygen slider values require explicit unit definition.
* Uptake, release, and cell-division probabilities are provisional.
* Tick duration and patch volume are not yet defined for calibrated rates.
* Model calibration and replicate simulation runs are required.

9. Future Development

* Separate simulation outputs by cell type and oxygen region.
* Introduce region-specific glucose and lactate plots.
* Strengthen and calibrate signal-response mechanisms.
* Implement concentration-gradient diffusion.
* Define patch volume, tick duration, and rate units.
* Introduce GLUT1/MCT1 interventions after baseline validation.

10. Reference

Jayathilake PG et al. (2024). Metabolic symbiosis between oxygenated and hypoxic tumour cells: An agent-based modeling study. PLOS Computational Biology.

Author

Khushi Sharma
B.Tech Bioinformatics (AI/ML)
IILM University
