# Small Tabular Reliability Framework

This repository contains the computational materials associated with the manuscript:

**A Framework for Reliability Assessment of Binary Classification Models in Small Tabular Datasets**

## Purpose

The framework evaluates binary classification models in small tabular datasets by combining predictive performance and stability. The simulation compares Logit, Firth logistic regression, Elastic Net, and CART using repeated bootstrap resampling.

The reliability profile contains five dimensions:

1. Mean AUC
2. Standard deviation of AUC
3. Mean Brier Score
4. Standard deviation of Brier Score
5. Prediction variability

Pareto dominance is used to identify non dominated models. Convergence and the number of valid bootstrap repetitions are reported separately.

## Repository files

`framework_simulation.ipynb` contains the simulation workflow, summary analyses, figure generation, and the comparison between AUC only selection and the multiobjective reliability profile.

`real_case_analysis.ipynb` contains the computational workflow used for the methodological real case study. The participant level dataset is not included in the public repository.

`results_simulation_complete_v3.csv` contains the final simulation results used in the manuscript.

`requirements.txt` lists the Python dependencies.

`CITATION.cff` provides citation metadata for this repository.

`LICENSE` contains the MIT License for the software.

## Simulation design

The simulation combines:

1. Sample sizes: 30, 50, 75, 100, and 150
2. Predictors: 5, 10, and 15
3. Expected outcome prevalence: 0.20 and 0.50
4. Predictor correlation: 0 and 0.5
5. Independent datasets per scenario: 50
6. Bootstrap repetitions per dataset: 100

This produces 60 scenarios and 3000 independent simulated datasets.

## Reproducing the reported results

Install the dependencies:

```bash
pip install -r requirements.txt
```

Open the notebook:

```text
framework_simulation.ipynb
```

By default, the notebook uses:

```text
results_simulation_complete_v3.csv
```

to reproduce the analyses and results reported in the manuscript without rerunning the complete simulation.

To regenerate the complete simulation, change:

```python
RUN_FULL_SIMULATION = False
```

to:

```python
RUN_FULL_SIMULATION = True
```

The complete simulation may require considerable computation time.

## Real case study data

The participant level dataset used in the methodological case study is not included in this public repository because it contains information collected from human participants.

The computational code and simulation results that can be shared publicly are provided in this repository.

## Authors

Héctor Alejandro Acuña Cid  
Ana Gabriela Galicia Rodríguez  
Anayancin Acuña Ruiz  
Ana María Herrera Medrano  
Julia Elena Hernández Ríos  
Gael Nájera De Lira

## License

This project is distributed under the MIT License. See the `LICENSE` file for details.

## Citation

Citation information is provided in the `CITATION.cff` file.

The archived version of this repository is available in Zenodo:

**DOI: 10.5281/zenodo.22018948**
