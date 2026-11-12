HQBOM: Hybrid Quantum-Based Optimization Method with Pattern Search
Overview
This repository contains the complete implementation, experimental framework, benchmark suite, engineering test problems, and statistical analysis associated with the Hybrid Quantum-Based Optimization Method (HQBOM).

HQBOM combines the Quantum-Based Optimization Method (QBOM) with Pattern Search (PS) to improve both global exploration and local exploitation during optimization. Two hybrid variants are investigated:

HQBOM-I: QBOM performs the global search, and Generalized Pattern Search is subsequently applied to refine the best solution identified by QBOM.
HQBOM-II: QBOM is embedded within Pattern Search and is activated whenever the polling phase fails to improve the incumbent solution.
The study presents directly implementable algorithms for QBOM, PS, HQBOM-I, and HQBOM-II, including function-evaluation accounting, Deb's feasibility rules for constrained optimization, and discrete-variable handling procedures.

The proposed methods are evaluated against 20 optimization algorithms, including:

HQBOM-I
HQBOM-II
QBOM
Pattern Search (PS)
Five classical optimization algorithms
Ten recent state-of-the-art algorithms
L-SHADE
Experiments are conducted on the CEC2017 constrained benchmark suite and a collection of constrained engineering design problems.

Methodological Background
Quantum-Based Optimization Method (QBOM)
QBOM is a population-based metaheuristic inspired by principles of quantum representation and quantum state evolution.

Each candidate solution is represented using qubit amplitudes, and the search process evolves these amplitudes through the application of quantum gates. The probabilistic representation enables a balance between exploration and exploitation while maintaining population diversity.

Key features include:

Quantum-inspired solution encoding
Quantum gate-based update mechanism
Population diversity preservation
Constraint handling based on Deb's feasibility rules
Support for mixed continuous and discrete decision variables
Pattern Search (PS)
Pattern Search is a derivative-free optimization method based on exploratory polling around incumbent solutions.

Key characteristics:

No gradient information required
Local search capability
Deterministic polling operations
Robust performance on constrained engineering problems
HQBOM-I
In HQBOM-I:

QBOM performs global exploration.
The best solution found by QBOM is extracted.
Generalized Pattern Search refines the solution in a local search phase.
This architecture aims to combine:

QBOM's global exploration ability
PS's local exploitation capability
HQBOM-II
In HQBOM-II:

Pattern Search serves as the primary optimizer.
When a polling step fails to improve the incumbent solution,
QBOM is launched to generate promising search directions and candidate points.
PS resumes from the improved region.
This creates an adaptive interaction between local and global search mechanisms.

Repository Structure
HQBOM/
│
├── QBOM/
│   └── Quantum-Based Optimization Method implementation
│
├── PS/
│   └── Pattern Search implementation
│
├── HQBOM-I/
│   └── Hybrid QBOM-I implementation
│
├── HQBOM-II/
│   └── Hybrid QBOM-II implementation
│
├── Competitors/
│   └── 16 competitor algorithm implementations
│
├── CEC2017/
│   └── CEC2017 constrained benchmark functions
│
├── Engineering_Problems/
│   ├── Engineering objective functions
│   ├── Constraint evaluators
│   └── Design-variable definitions
│
├── Constraint_Handling/
│   ├── Deb feasibility rules
│   ├── Penalty procedures
│   └── Constraint violation calculations
│
├── Discrete_Variables/
│   └── Discrete-variable treatment procedures
│
├── Parameter_Settings/
│   └── Parameters used in all experiments
│
├── Seeds/
│   └── Random seed generation and initialization protocol
│
├── Results/
│   └── Run-level experimental results
│
├── Statistical_Analysis/
│   └── Statistical analysis workbook and test outputs
│
└── README.md
