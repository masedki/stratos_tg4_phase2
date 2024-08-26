# stratos_tg4_phase2
This repository presents the datasets, calculation codes and evaluation results for phase 2 of STRATOS TG4. *Backup repository after cyberattack at Paris-Saclay university  prevents access to original repository : https://gitlab.dsi.universite-paris-saclay.fr/mohammed.sedki/stratos_tg4_phase2*



## Presentation of different simulated data scenarios

The folder **datasets_phase2.zip** contains 5 folders **dataset1** to **dataset5** corresponding to **5** simulation scenarios and the script to generate them. Each **dataset1** to **dataset5** folder contains **15** datasets corresponding to **15** different combinations of parameters, as shown in the the section **Tables of datasets simulation parameters** below. 


- **Dataset 1 (J-shape)** : $\text{logit}\big(\mathbb P(Y = 1)\big) =  -2.202 + 268 e^{-0.383 X} + 0.00197 e^{0.139 X}$, where $\ln(X) \sim \mathcal{N}\big(3.3, 0.25^2\big)$.

- **Dataset 2 (Linear)** : $\text{logit}\big(\mathbb P(Y = 1)\big) =  -5.78 + 0.545 X$, where $X \sim \mathcal{N}\big(3.29, 0.24^2\big)$.

- **Dataset 3 (Threshold with change-point below median and linear increase)** : 
$\text{logit}\big(\mathbb P(Y = 1)\big) =  -2.2 + 0.0135 T \big(X-90\big)$, where $T(W) =  W \mathbf{1}_{\{W \ge 0\}}$  and $X \sim \mathcal{N}\big(100,  19.4^2\big)$.

- **Dataset 4 (Threshold with change-point above median and exponential increase)** : 
$\text{logit}\big(\mathbb P(Y = 1)\big) =  -3.2 + e^{0.02 T(X-120)}$, where $T(W) =  W \mathbf{1}_{\{W \ge 0\}}$  and $\ln(X) \sim \mathcal{N}\big(4.5,  23^2\big)$.

- **Dataset 5 (Saturation)** : $\text{logit}\big(\mathbb P(Y = 1)\big) = \ln\big(\frac{3}{7} X^6 + \frac{1}{19} 50^6 \big) – \ln\big(50^6 + X^6\big)$, where $X \sim \text{Unif}(30,80)$.


- Parameters **nstudy**, **vratio**, **errdist** and **nrep** have common values for all 5 scenarios.
- **nsim** parameter has the same value for all datasets except **Dataset 2**. 

## Tables of datasets simulation parameters

### Dataset 1

|        |  nsim| distind| mux| sigx| nstudy| vratio| errdist| nrep|
|:-------|-----:|-------:|---:|----:|------:|------:|-------:|----:|
|comb_1  | 2e+05|       1| 3.3| 0.25|  30000|    0.5|       0|  250|
|comb_2  | 2e+05|       1| 3.3| 0.25|  15000|    1.0|       0|  250|
|comb_3  | 2e+05|       1| 3.3| 0.25|  30000|    1.0|       0|  250|
|comb_4  | 2e+05|       1| 3.3| 0.25|  15000|    0.5|       1|  250|
|comb_5  | 2e+05|       1| 3.3| 0.25|  30000|    0.5|       1|  250|
|comb_6  | 2e+05|       1| 3.3| 0.25|  15000|    1.0|       1|  250|
|comb_7  | 2e+05|       1| 3.3| 0.25|  30000|    1.0|       1|  250|
|comb_8  | 2e+05|       1| 3.3| 0.25|  15000|    0.5|       0|  750|
|comb_9  | 2e+05|       1| 3.3| 0.25|  30000|    0.5|       0|  750|
|comb_10 | 2e+05|       1| 3.3| 0.25|  15000|    1.0|       0|  750|
|comb_11 | 2e+05|       1| 3.3| 0.25|  30000|    1.0|       0|  750|
|comb_12 | 2e+05|       1| 3.3| 0.25|  15000|    0.5|       1|  750|
|comb_13 | 2e+05|       1| 3.3| 0.25|  30000|    0.5|       1|  750|
|comb_14 | 2e+05|       1| 3.3| 0.25|  15000|    1.0|       1|  750|
|comb_15 | 2e+05|       1| 3.3| 0.25|  30000|    1.0|       1|  750|

### Dataset 2 

|        |  nsim| distind|  mux| sigx| 
|:-------|-----:|-------:|----:|----:|
|comb_1  | 1e+07|       0| 3.29| 0.24|  
|comb_2  | 1e+07|       0| 3.29| 0.24|  
|comb_3  | 1e+07|       0| 3.29| 0.24|  
|comb_4  | 1e+07|       0| 3.29| 0.24|  
|comb_5  | 1e+07|       0| 3.29| 0.24|  
|comb_6  | 1e+07|       0| 3.29| 0.24|  
|comb_7  | 1e+07|       0| 3.29| 0.24|  
|comb_8  | 1e+07|       0| 3.29| 0.24| 
|comb_9  | 1e+07|       0| 3.29| 0.24|  
|comb_10 | 1e+07|       0| 3.29| 0.24|  
|comb_11 | 1e+07|       0| 3.29| 0.24| 
|comb_12 | 1e+07|       0| 3.29| 0.24|  
|comb_13 | 1e+07|       0| 3.29| 0.24|  
|comb_14 | 1e+07|       0| 3.29| 0.24|  
|comb_15 | 1e+07|       0| 3.29| 0.24|  


### Dataset 3

|        | distind| mux| sigx|
|:-------|-------:|---:|----:|
|comb_1  |       0| 100| 19.4| 
|comb_2  |       0| 100| 19.4| 
|comb_3  |       0| 100| 19.4| 
|comb_4  |       0| 100| 19.4|  
|comb_5  |       0| 100| 19.4|  
|comb_6  |       0| 100| 19.4|  
|comb_7  |       0| 100| 19.4|  
|comb_8  |       0| 100| 19.4|  
|comb_9  |       0| 100| 19.4| 
|comb_10 |       0| 100| 19.4| 
|comb_11 |       0| 100| 19.4|  
|comb_12 |       0| 100| 19.4|  
|comb_13 |       0| 100| 19.4|  
|comb_14 |       0| 100| 19.4|  
|comb_15 |       0| 100| 19.4|  

### Dataset 4 

|       | distind| mux| sigx|
|:------|-------:|---:|----:|
|comb_1 |       1| 4.5| 0.23| 
|comb_2 |       1| 4.5| 0.23|  
|comb_3 |       1| 4.5| 0.23|  
|comb_4 |       1| 4.5| 0.23|  
|comb_5 |       1| 4.5| 0.23| 
|comb_6 |       1| 4.5| 0.23|  
|comb_7 |       1| 4.5| 0.23|  
|comb_8 |       1| 4.5| 0.23|  
|comb_9 |       1| 4.5| 0.23|  
|comb_10|       1| 4.5| 0.23|  
|comb_11|       1| 4.5| 0.23|  
|comb_12|       1| 4.5| 0.23|  
|comb_13|       1| 4.5| 0.23| 
|comb_14|       1| 4.5| 0.23|  
|comb_15|       1| 4.5| 0.23|  

### Dataset 5 

|        | distind| mux| sigx| 
|:-------|-------:|---:|----:|
|comb_1  |       2|  30|   80|  
|comb_2  |       2|  30|   80| 
|comb_3  |       2|  30|   80|  
|comb_4  |       2|  30|   80|  
|comb_5  |       2|  30|   80|  
|comb_6  |       2|  30|   80|  
|comb_7  |       2|  30|   80|  
|comb_8  |       2|  30|   80|  
|comb_9  |       2|  30|   80|  
|comb_10 |       2|  30|   80|  
|comb_11 |       2|  30|   80|  
|comb_12 |       2|  30|   80|  
|comb_13 |       2|  30|   80|  
|comb_14 |       2|  30|   80|  
|comb_15 |       2|  30|   80|  
