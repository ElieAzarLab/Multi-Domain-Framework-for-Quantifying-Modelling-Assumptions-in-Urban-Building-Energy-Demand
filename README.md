# Multi-Domain-Framework-for-Quantifying-Modelling-Assumptions-in-Urban-Building-Energy-Demand
Reproducible CEA workflow and datasets for assessing urban context, climate, and EV charging modelling assumptions in urban building energy simulations.

## **Overview**
  This workbook documents the inputs, simulation settings, and workflow used to reproduce the City Energy Analyst (CEA) simulations conducted in this study. All simulations use a common base configuration, with scenario-specific changes applied independently across three modelling domains:

Domain 1 – Urban Context: adjacent buildings are either considered or neglected.
Domain 2 – Climate: the weather file used for the simulation is varied.
Domain 3 – EV Charging: the CEA database is varied to apply the corresponding prepared EV charging load profiles.

The Scenario_Matrix sheet identifies the specific combination of inputs required for each simulation. Settings that remain unchanged across simulations are documented separately in the Common_Settings sheet.

## **Software Overview**
| Item | Specification |
|---|---|
| City Energy Analyst version | 4.0.0-beta.4 |
| Operating system | Windows 11 |
| Computer type | Laptop |
| Processor | Intel Core i7 |
| Installed RAM | 16 GB |
| RAM speed | 4266 MHz |

The simulations were conducted using City Energy Analyst 4.0.0-beta.4. Reproduction of the study should use this version where possible because changes between CEA versions may affect available settings, workflows, databases, or simulation results. 

The CEA 4.0.0-beta.4 installation files used for this study are provided with the repository to preserve access to the original simulation environment. Users may alternatively obtain the same version from the official CEA release archive where available.

Each simulation required approximately 30 minutes on the computer described above when all required workflow steps were initiated consecutively. The simulation consists of multiple CEA workflow steps that must be run sequentially by the user. Actual runtimes may vary depending on computer hardware and the selected scenario.

## **Repository Structure**
Each simulation folder retains the corresponding CEA scenario structure, including its input and output files. These folders therefore provide the model inputs and reference outputs associated with each simulation.

The weather_files directory contains the weather files used for the Climate modelling domain. The exact weather file associated with each simulation is identified in the Scenario_Matrix sheet.

The databases directory contains the CEA databases used for the EV Charging modelling domain. The required EV charging load profiles are already prepared within the corresponding databases. The database associated with each simulation is identified in the Scenario_Matrix sheet.

If included, the software directory contains the CEA 4.0.0-beta.4 installation package used to establish the original simulation environment.

## **Simulation**
## **Before Running a Simulation**
1. Install City Energy Analyst 4.0.0-beta.4.
2. Download or clone the complete GitHub repository.
3. Locate the simulation to be reproduced in the Scenario_Matrix sheet.
4. Identify the required Domain 1, Domain 2, and Domain 3 inputs.
5. Open or create the corresponding CEA scenario using the provided simulation folder.
6. Apply the scenario-specific inputs identified in the Scenario_Matrix.
7. Confirm that all remaining simulation parameters are consistent with the Common_Settings sheet.

## **Domain-Specific Inputs**
The following inputs vary when each domain is applied.

| Modelling Domain | Parameter Changed | Required Action |
|---|---|---|
| Domain 1 – Urban Context | Treatment of adjacent buildings | Set adjacent buildings to **considered** or **neglected** as specified in the `Scenario_Matrix`. |
| Domain 2 – Climate | Weather file | Select the exact weather file identified in the `Scenario_Matrix` from the `weather_files` directory. |
| Domain 3 – EV Charging | CEA database | Select the database identified in the `Scenario_Matrix`. The required EV charging load profiles are already prepared within the corresponding database. |

All other inputs and simulation settings remain consistent unless explicitly stated otherwise.
## **Simulation Procedure Summary**
1. Setup the corresponding CEA scenario (includes Domain 2 weather file).
2. Choose the database (includes Domain 3 EV adoption)
3. Confirm that the common model inputs and parameters match the Common_Settings sheet.
4. Run the Solar Radiation Analysis module using DAYSIM (Domain 1 urban context)
5. Run the Energy Demand Forecasting module of Energy Demand Part 1: building occupancy
6. 5. Run the Energy Demand Forecasting - Energy Demand Part 2: load modelling 

[Note]
Allow each workflow step to finish before initiating the next required step.
The generated outputs are automatically retained within the corresponding CEA simulation folder.
## **Simulation Check**
Each simulation is assigned a unique Simulation ID in the Scenario_Matrix. The Simulation ID links the scenario configuration in the spreadsheet to its corresponding CEA simulation folder.

For example:
Simulation_05 → simulations/Simulation_05/
