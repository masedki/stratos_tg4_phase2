# stratos_tg4_phase2

This repository presents the datasets, calculation codes and evaluation results for phase 2 of STRATOS TG4. *Backup repository after cyberattack at Paris-Saclay university prevents access to original repository : <https://gitlab.dsi.universite-paris-saclay.fr/mohammed.sedki/stratos_tg4_phase2>*

## Presentation of different simulated data scenarios

The folder **datasets_phase2.zip** contains 5 folders **dataset1** to **dataset5** corresponding to **5** simulation scenarios and the script to generate them. Each **dataset1** to **dataset5** folder contains **15** datasets corresponding to **15** different combinations of parameters, as shown in the the section **Tables of datasets simulation parameters** below.

-   **Dataset 1 (J-shape)** : $`\text{logit}(\mathbb{P}(Y = 1)) =  -2.202 + 268 e^{-0.383 X} + 0.00197 e^{0.139 X} \quad \text{where} \quad \ln(X) \sim \mathcal{N}(3.3, 0.25^2)`$.

-   **Dataset 2 (Linear)** : $\text{logit}(\mathbb{P}(Y = 1)) =  -5.78 + 0.545 X$, where $X \sim \mathcal{N}(3.29, 0.24^2)$.

-   **Dataset 3 (Threshold with change-point below median and linear increase)** : $\text{logit}(\mathbb{P}(Y = 1)) =  -2.2 + 0.0135 T (X-90)$, where $T(W) =  W \mathbf{1}_{\{W \ge 0\}}$ and $X \sim \mathcal{N}(100,  19.4^2)$.

-   **Dataset 4 (Threshold with change-point above median and exponential increase)** : $\text{logit}(\mathbb{P}(Y = 1)) =  -3.2 + e^{0.02 T(X-120)}$, where $T(W) =  W \mathbf{1}_{\{W \ge 0\}}$ and $\ln(X) \sim \mathcal{N}(4.5,  23^2)$.

-   **Dataset 5 (Saturation)** : $\text{logit}(\mathbb{P}(Y = 1)) = \ln(\frac{3}{7} X^6 + \frac{1}{19} 50^6) – \ln(50^6 + X^6)$, where $X \sim \text{Unif}(30,80)$.

## Codes

There's a folder starting with **R_codes...** that corresponds to each team. In this folder, you'll have a main function declared in a script that performs the estimation for a single dataset, and a script ending with fullrun that executes the code on all $75  = 5 \times 15$ datasets in parallel. Please note that there is a parameter that allows you to reserve the number of cores to be used. Parallelization is adapted to Linux and MacOS servers and will not work under Windows.

## Results and figures :

For each team, there is a folder starting with **results....**, which contains 5 folders **res_dataset1_figures to res_dataset5_figures**. Each folder contains a comparison of the functions estimated by the team's methods with the true function for the 15 datasets. The **comparison_scripts_AllTeams.zip** folder contains all the scripts used to draw the different figures.

## A few details 
Here are the various abbreviations that can be found in the different files. 

- **fp** : Fractional polynomials
- **bs** : B-spline 
- **mi** : Multiple imputation 
- **rc** : Regression calibration 
- **ps** : Penalized spline
- **reml** : Restricted maximum likelihood 
-  skwn_"a given bayes method"_1 or bay.mlogit = Bayes logit of posterior mean on P(Y=1) scale
-  skwn_"a given bayes method"_2 or bay.logitm = Bayes posterior mean on logit(P(Y=1)) scale

## Tables of datasets simulation parameters

-   **nstudy** = sample size of main study; **vratio** = ratio of variance of measurement error to variance of X; **errdist** 0=normal, 1=shifted-gamma; **nrep** = sample size of replication sub-study.
-   Parameters **nstudy**, **vratio**, **errdist** and **nrep** have common values for all 5 scenarios.
-   **nsim** parameter has the same value for all datasets except **Dataset 2**.

### Dataset 1

|         |  nsim | distind | mux | sigx | nstudy | vratio | errdist | nrep |
|:--------|------:|--------:|----:|-----:|-------:|-------:|--------:|-----:|
| comb_1  | 2e+05 |       1 | 3.3 | 0.25 |  30000 |    0.5 |       0 |  250 |
| comb_2  | 2e+05 |       1 | 3.3 | 0.25 |  15000 |    1.0 |       0 |  250 |
| comb_3  | 2e+05 |       1 | 3.3 | 0.25 |  30000 |    1.0 |       0 |  250 |
| comb_4  | 2e+05 |       1 | 3.3 | 0.25 |  15000 |    0.5 |       1 |  250 |
| comb_5  | 2e+05 |       1 | 3.3 | 0.25 |  30000 |    0.5 |       1 |  250 |
| comb_6  | 2e+05 |       1 | 3.3 | 0.25 |  15000 |    1.0 |       1 |  250 |
| comb_7  | 2e+05 |       1 | 3.3 | 0.25 |  30000 |    1.0 |       1 |  250 |
| comb_8  | 2e+05 |       1 | 3.3 | 0.25 |  15000 |    0.5 |       0 |  750 |
| comb_9  | 2e+05 |       1 | 3.3 | 0.25 |  30000 |    0.5 |       0 |  750 |
| comb_10 | 2e+05 |       1 | 3.3 | 0.25 |  15000 |    1.0 |       0 |  750 |
| comb_11 | 2e+05 |       1 | 3.3 | 0.25 |  30000 |    1.0 |       0 |  750 |
| comb_12 | 2e+05 |       1 | 3.3 | 0.25 |  15000 |    0.5 |       1 |  750 |
| comb_13 | 2e+05 |       1 | 3.3 | 0.25 |  30000 |    0.5 |       1 |  750 |
| comb_14 | 2e+05 |       1 | 3.3 | 0.25 |  15000 |    1.0 |       1 |  750 |
| comb_15 | 2e+05 |       1 | 3.3 | 0.25 |  30000 |    1.0 |       1 |  750 |

### Dataset 2 
|        |  nsim| distind|  mux| sigx| nstudy| vratio| errdist| nrep|
|:-------|-----:|-------:|----:|----:|------:|------:|-------:|----:|
|comb_1  | 1e+07|       0| 3.29| 0.24|  30000|    0.5|       0|  250|
|comb_2  | 1e+07|       0| 3.29| 0.24|  15000|    1.0|       0|  250|
|comb_3  | 1e+07|       0| 3.29| 0.24|  30000|    1.0|       0|  250|
|comb_4  | 1e+07|       0| 3.29| 0.24|  15000|    0.5|       1|  250|
|comb_5  | 1e+07|       0| 3.29| 0.24|  30000|    0.5|       1|  250|
|comb_6  | 1e+07|       0| 3.29| 0.24|  15000|    1.0|       1|  250|
|comb_7  | 1e+07|       0| 3.29| 0.24|  30000|    1.0|       1|  250|
|comb_8  | 1e+07|       0| 3.29| 0.24|  15000|    0.5|       0|  750|
|comb_9  | 1e+07|       0| 3.29| 0.24|  30000|    0.5|       0|  750|
|comb_10 | 1e+07|       0| 3.29| 0.24|  15000|    1.0|       0|  750|
|comb_11 | 1e+07|       0| 3.29| 0.24|  30000|    1.0|       0|  750|
|comb_12 | 1e+07|       0| 3.29| 0.24|  15000|    0.5|       1|  750|
|comb_13 | 1e+07|       0| 3.29| 0.24|  30000|    0.5|       1|  750|
|comb_14 | 1e+07|       0| 3.29| 0.24|  15000|    1.0|       1|  750|
|comb_15 | 1e+07|       0| 3.29| 0.24|  30000|    1.0|       1|  750|


### Dataset 3

|        |  nsim| distind| mux| sigx| nstudy| vratio| errdist| nrep|
|:-------|-----:|-------:|---:|----:|------:|------:|-------:|----:|
|comb_1  | 2e+05|       0| 100| 19.4|  30000|    0.5|       0|  250|
|comb_2  | 2e+05|       0| 100| 19.4|  15000|    1.0|       0|  250|
|comb_3  | 2e+05|       0| 100| 19.4|  30000|    1.0|       0|  250|
|comb_4  | 2e+05|       0| 100| 19.4|  15000|    0.5|       1|  250|
|comb_5  | 2e+05|       0| 100| 19.4|  30000|    0.5|       1|  250|
|comb_6  | 2e+05|       0| 100| 19.4|  15000|    1.0|       1|  250|
|comb_7  | 2e+05|       0| 100| 19.4|  30000|    1.0|       1|  250|
|comb_8  | 2e+05|       0| 100| 19.4|  15000|    0.5|       0|  750|
|comb_9  | 2e+05|       0| 100| 19.4|  30000|    0.5|       0|  750|
|comb_10 | 2e+05|       0| 100| 19.4|  15000|    1.0|       0|  750|
|comb_11 | 2e+05|       0| 100| 19.4|  30000|    1.0|       0|  750|
|comb_12 | 2e+05|       0| 100| 19.4|  15000|    0.5|       1|  750|
|comb_13 | 2e+05|       0| 100| 19.4|  30000|    0.5|       1|  750|
|comb_14 | 2e+05|       0| 100| 19.4|  15000|    1.0|       1|  750|
|comb_15 | 2e+05|       0| 100| 19.4|  30000|    1.0|       1|  750|

### Dataset 4 

|        |  nsim| distind| mux| sigx| nstudy| vratio| errdist| nrep|
|:-------|-----:|-------:|---:|----:|------:|------:|-------:|----:|
|comb_1  | 2e+05|       1| 4.5| 0.23|  30000|    0.5|       0|  250|
|comb_2  | 2e+05|       1| 4.5| 0.23|  15000|    1.0|       0|  250|
|comb_3  | 2e+05|       1| 4.5| 0.23|  30000|    1.0|       0|  250|
|comb_4  | 2e+05|       1| 4.5| 0.23|  15000|    0.5|       1|  250|
|comb_5  | 2e+05|       1| 4.5| 0.23|  30000|    0.5|       1|  250|
|comb_6  | 2e+05|       1| 4.5| 0.23|  15000|    1.0|       1|  250|
|comb_7  | 2e+05|       1| 4.5| 0.23|  30000|    1.0|       1|  250|
|comb_8  | 2e+05|       1| 4.5| 0.23|  15000|    0.5|       0|  750|
|comb_9  | 2e+05|       1| 4.5| 0.23|  30000|    0.5|       0|  750|
|comb_10 | 2e+05|       1| 4.5| 0.23|  15000|    1.0|       0|  750|
|comb_11 | 2e+05|       1| 4.5| 0.23|  30000|    1.0|       0|  750|
|comb_12 | 2e+05|       1| 4.5| 0.23|  15000|    0.5|       1|  750|
|comb_13 | 2e+05|       1| 4.5| 0.23|  30000|    0.5|       1|  750|
|comb_14 | 2e+05|       1| 4.5| 0.23|  15000|    1.0|       1|  750|
|comb_15 | 2e+05|       1| 4.5| 0.23|  30000|    1.0|       1|  750|

### Dataset 5 
|        |  nsim| distind| mux| sigx| nstudy| vratio| errdist| nrep|
|:-------|-----:|-------:|---:|----:|------:|------:|-------:|----:|
|comb_1  | 2e+05|       2|  30|   80|  30000|    0.5|       0|  250|
|comb_2  | 2e+05|       2|  30|   80|  15000|    1.0|       0|  250|
|comb_3  | 2e+05|       2|  30|   80|  30000|    1.0|       0|  250|
|comb_4  | 2e+05|       2|  30|   80|  15000|    0.5|       1|  250|
|comb_5  | 2e+05|       2|  30|   80|  30000|    0.5|       1|  250|
|comb_6  | 2e+05|       2|  30|   80|  15000|    1.0|       1|  250|
|comb_7  | 2e+05|       2|  30|   80|  30000|    1.0|       1|  250|
|comb_8  | 2e+05|       2|  30|   80|  15000|    0.5|       0|  750|
|comb_9  | 2e+05|       2|  30|   80|  30000|    0.5|       0|  750|
|comb_10 | 2e+05|       2|  30|   80|  15000|    1.0|       0|  750|
|comb_11 | 2e+05|       2|  30|   80|  30000|    1.0|       0|  750|
|comb_12 | 2e+05|       2|  30|   80|  15000|    0.5|       1|  750|
|comb_13 | 2e+05|       2|  30|   80|  30000|    0.5|       1|  750|
|comb_14 | 2e+05|       2|  30|   80|  15000|    1.0|       1|  750|
|comb_15 | 2e+05|       2|  30|   80|  30000|    1.0|       1|  750|
