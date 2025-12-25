When Rule-Based Screening Misses Judgment

Evidence from Synthetic ERP Simulations

Overview
-------------------------
This repository contains a minimal simulation framework designed to illustrate a structural limitation of rule-based screening systems commonly used in accounting, auditing, and tax enforcement.

Specifically, the simulation demonstrates how judgment-based risks, which appear statistically regular at the transaction level, can become systematically invisible to rule-based detection when data linkage quality deteriorates—even slightly.

The goal of this project is not to propose a new detection algorithm, but to highlight a structural mismatch between:
	
    the level at which screening rules operate (transaction-level), and
	
	the level at which professional judgment and economic substance reside (case-level).



Core Research Question
-----------------------
Why do rule-based screening systems continue to flag numerical anomalies reliably, while missing judgment-intensive risks—even as screening effort increases?

Key Idea
-----------
We introduce Linkage Quality (λ) as an experimental parameter representing how accurately transactions are associated with their underlying economic cases (e.g., contracts or projects).

By degrading linkage quality in a controlled synthetic environment, we show that:
	
  •	Numerical anomalies (e.g., unusually large amounts or frequencies) remain relatively detectable.
	
  •	Judgment-based risks experience a sharp and non-linear collapse in detection rates.
	
  •	Increasing review capacity does not proportionally improve the discovery of judgment-based risks.

This asymmetric sensitivity persists even when simple repair heuristics are applied.



Simulation Design (High-Level)
-----------------
Scenarios

Each case belongs to one of four stylized categories:
	
  •	S0 — Normal cases
Statistically and economically regular.
	
  •	S1 — Large-amount cases
High transaction amounts; numerically salient.
	
  •	S2 — High-frequency cases
Elevated transaction counts; numerically salient.
	
  •	S3 — Judgment-based cases
Statistically regular at the transaction level, but aggressive in aggregate (e.g., accounting discretion).

Key Parameters
	
  •	Linkage Quality (λ)
Probability that a transaction is correctly linked to its true case.
	
  •	Review Capacity (K)
Number of flagged cases that can be reviewed in detail.
	
  •	Aggregation Threshold (τ)
Case-level rule threshold (e.g., share of asset-type transactions).



Detection Rules
---------------------
  •	Transaction-level rules
	
  •	Amount-based outlier detection
	
  •	Frequency-based detection
	
  •	Simple AND combinations
	
  •	Case-level aggregation rule
	
  •	Flags cases exceeding a threshold share of asset-type transactions

The framework intentionally keeps rules simple to isolate structural effects rather than model sophistication.



Key Metrics
-------------	
  •	Detection Rate by Scenario
Fraction of cases flagged within each scenario.
	
  •	Opportunity Cost Index (OCI)
Measures how much judgment-based risk remains undiscovered given a fixed review capacity.



Main Finding
-----------------------
As linkage quality deteriorates, judgment-based risks collapse in detectability much faster than numerical anomalies, even when review capacity increases.

This suggests that the blind spot is structural, not merely a consequence of insufficient rules, manpower, or data cleaning.



Repository Structure
------------------------
.

├── sim_v12_min.py        # Single-file simulation script

├── README.md             # Project overview (this file)

└── figures/              # Example output figures (optional)

The project intentionally avoids complex pipelines or configuration files to maintain transparency and reproducibility.



Data and Ethics
-----------------------
  •	No real firm-level or proprietary data are used.
	
  •	All data are synthetically generated for illustrative purposes.
	
  •	The simulation is intended for conceptual and methodological exploration only.



Status
---------------------
This repository reflects an early-stage research note / working prototype.
The current focus is on clarifying the structural mechanism rather than producing a finalized empirical study.



Citation
-------------------------
If you reference this work, please cite it as:

MINSUK KIM (2025). When Rule-Based Screening Misses Judgment: Evidence from Synthetic ERP Simulations. Working paper.



Contact
-------------------------
For questions, comments, or discussion, feel free to open an issue or contact the author directly.
hjjy151225@snu.ac.kr 

