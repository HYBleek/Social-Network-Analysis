# Social Network Analysis of the Chilean Power Grid

This repository contains the code and analysis for the "Complete Solution to Four SNA Tasks (WOR Version)" report, focusing on a simplified representation (WOR) of the Chilean high-voltage power grid. The analysis was performed by Henry Cui (haoyang.cui.gr@dartmouth.edu).

## Table of Contents

1.  [Introduction](https://www.google.com/search?q=%23introduction)
2.  [Dataset](https://www.google.com/search?q=%23dataset)
3.  [Analysis Tasks](https://www.google.com/search?q=%23analysis-tasks)
      * [Task 1: Network Identification](https://www.google.com/search?q=%23task-1-network-identification)
      * [Task 2: Graphical Display of the WOR Network](https://www.google.com/search?q=%23task-2-graphical-display-of-the-wor-network)
      * [Task 3: Structural Summary Measures](https://www.google.com/search?q=%23task-3-structural-summary-measures)
      * [Task 4: Research Questions and ERGM Testing](https://www.google.com/search?q=%23task-4-research-questions-and-ergm-testing)
4.  [Reproducibility](https://www.google.com/search?q=%23reproducibility)
5.  [Citation](https://www.google.com/search?q=%23citation)
6.  [Contact](https://www.google.com/search?q=%23contact)

## Introduction

This project conducts a comprehensive Social Network Analysis (SNA) on the Chilean high-voltage power grid, specifically using its "WOR" (Reduced) abstraction. The report addresses four classic SNA tasks: dataset identification, graphical visualization, structural summarization, and statistical modeling using Exponential Random-Graph Models (ERGMs).

## Dataset

The analysis utilizes the "WOR (Reduced)" version of the Chilean power-grid network. This curated dataset focuses on active facilities (Generators and Substations) and provides crucial relational data (edges) and node attributes (type, nominal voltage, geographic coordinates).

| Version        | Nodes | Edges | Node Types    | Remarks            |
| :------------- | :---- | :---- | :------------ | :----------------- |
| WT (With Taps) | 347   |       | Gen/SS/Conn/Tap | Most detailed      |
| WOT (Without Taps) | 318   |       | Gen/SS/Conn   | Tap nodes removed  |
| WOR (Reduced)  | 218   | 527   | Gen/SS        | Active facilities only |

## Analysis Tasks

### Task 1: Network Identification

This task involved selecting the appropriate dataset with rich relational and attribute information suitable for SNA. The WOR version was chosen due to its balance of detail and focus on active components.

### Task 2: Graphical Display of the WOR Network

This section provides visual representations of the WOR network.

  * **Topological Layout (Spring Layout)**: Highlights the structural properties of the network.
  * **Geographic Layout**: Displays the spatial distribution of the network nodes.

### Task 3: Structural Summary Measures

This task involved calculating and summarizing various global and actor-level network metrics.

#### Global Metrics for the WOR network ($n=218$):

| Metric                     | Symbol          | Value    |
| :------------------------- | :-------------- | :------- |
| Nodes                      | V               | 218      |
| Edges                      | E               | 527      |
| Density                    | P               | 0.0223   |
| Diameter                   | D               | 18       |
| Average shortest-path length |                 | 5.8117   |
| Global clustering coefficient | C               | 0.5583   |
| Average local clustering coefficient | $\\overline{C}\_{loc}$ | 0.5799   |
| Average degree             | $\\overline{k}$ | 4.8349   |

**Community Structure**: Ten well-defined communities were identified using Louvain modularity maximization, with the largest community (ID 9) containing 49 vertices.

#### Actor-Level Metrics: Top-5 Nodes

| Rank | Node (Degree) | deg   | Node (Betweenness) | BC\* |
| :--- | :------------ | :---- | :----------------- | :------ |
| 1    | Charrua       | 0.152 | Alto Jahuel        | 0.536   |
| 2    | Alto Jahuel   | 0.106 | Charrua            | 0.525   |
| 3    | Polpaico      | 0.101 | Ancoa              | 0.468   |
| 4    | Quillota      | 0.092 | Polpaico           | 0.398   |
| 5    | Ventanas      | 0.078 | Los Vilos          | 0.260   |

\*BC normalized to [0,1].

### Task 4: Research Questions and ERGM Testing

This task involved testing different Exponential Random-Graph Models (ERGMs) to understand the underlying mechanisms of network formation.

#### Model 0: Null (Edges-only) ERGM

This baseline model confirms the network's sparsity and serves as a reference point for more complex models.

#### Model 1: Community, Owner, Role & GWESP ERGM

This model demonstrates a significant improvement in fit compared to the null model. It highlights strong homophily effects based on community and owner attributes, and confirms systematic triangle closure.

#### Model 2: Role-Heterophily ERGM

This model isolates the effect of functional roles. While the coefficient remains negative for cross-role edges, the model's fit is not significantly better than the null model, suggesting that role alone does not explain much of the network's higher-order structure when other strong controls are absent.

## Reproducibility

All analyses presented in the report are fully reproducible. The repository includes Python and R code listings integrated into the report.

## Citation

The dataset used in this analysis is described in:

Kim, H., Olave-Rojas, D., Álvarez-Miranda, E. Son, S.-W. (2018). In-depth data on the network structure and hourly activity of the Central Chilean power grid. Scientific Data, 5, 180209. [https://doi.org/10.1038/sdata.2018.209](https://doi.org/10.1038/sdata.2018.209)

## Contact

For any questions or inquiries, please contact Henry Cui at haoyang.cui.hse@dartmouth.edu.
