# Paper Airplane Experiment: A Factorial Design on Flight Distance

## Overview  
This project investigates how the **placement of paper clips** on a paper airplane impacts flight distance. Using a **$2^3$ full factorial design**, the study evaluates aerodynamic performance across eight weight configurations in a controlled indoor setting.

## Methodology  

This study followed a controlled factorial experiment using a **$2^3$ between-subjects design** to explore how **clip placement on the nose, middle, and rear** affects distance traveled.

### Trials  
- **8 unique treatment combinations** from three binary factors  
- **3 replicates per treatment** → 24 trials total  
- Trials conducted in random order to minimize bias

### Experimental Factors  
- **Clip on Nose (2 levels):**
  - *Present*
  - *Absent*  
- **Clip on Middle (2 levels):**
  - *Present*
  - *Absent*  
- **Clip on Rear (2 levels):**
  - *Present*
  - *Absent*  

### Controls  
- All planes constructed identically from the same template  
- Tosses executed by the same individual using a consistent motion  
- Environment: Indoor hallway with no wind interference  
- Flight distance measured using iPhone's built-in measuring app  
- Planes repaired or replaced after damage to maintain consistency  

### Procedure  
- Each configuration tested 3 times  
- Paper airplane was restored to its original condition after each flight  
- Data logged manually after each toss  

### Analysis  
- A linear model with interaction terms was fitted to predict flight distance  
- Assumptions (normality, independence, homoscedasticity) were validated  
- Post-hoc power analysis was conducted using a custom R simulation script  

## Results  

The linear model analysis revealed how different clip placements affected flight distance.

### Main Findings  
- **Nose clip** significantly increased flight distance  
  - *p* = 0.020  
  - Estimated increase of **+9.47 units**
- **Middle clip** also improved distance  
  - *p* = 0.017  
  - Estimated increase of **+9.77 units**
- **Rear clip** significantly reduced distance  
  - *p* = 0.021  
  - Estimated decrease of **−9.37 units**

### Interaction Effects  
- **Nose × Middle**: significant negative interaction  
  - *p* = 0.031  
  - Suggests overweighting the front half impairs flight
- **Other interactions** were not statistically significant  
  - Nose × Rear: *p* = 0.584  
  - Middle × Rear: *p* = 0.133  
  - 3-way interaction: *p* = 0.062 (marginal)

### Model Performance & Power  
- **Overall model p-value**: < 0.001  
- **Post-hoc power analysis**:  
  - Achieved statistical power = **0.823** with 24 trials  
  - Confirms adequacy of sample size and design  

### Assumption Checks  
- **Shapiro-Wilk test**: *p* = 0.991 → residuals are normally distributed  
- **Residual vs. Fitted plot**: showed no pattern, confirming homoscedasticity  
- **QQ plot & histogram**: confirmed bell-shaped distribution  

# View the Full Report  
- [paperairplaneproj.pdf](https://github.com/alexqiuu/Airplane_Factorial/blob/main/paperairplaneproj.pdf)

## Project Structure  
paperairplaneproj/
├── Data/ # Raw dataset from 24 trials
│ └── plane_data.xlsx
│
├── Images/ # Photos of hallway and clip positions
│ └── [pre-launch and toss visuals]
│
├── Report/ # Rmd report and supporting scripts
│ ├── paperairplaneproj.Rmd
│
├── power_factorial_23.R # Power simulation function
├── paperairplaneproj.pdf # PDF output of the report
├── .gitignore # Ignore list for Git
└── README.md # Overview of project and analysis steps

## Dependencies  

This project was developed in R. Install the following packages to reproduce the results:

### Required R Packages  
```r
install.packages(c(
  "tidyverse",     # For data manipulation and plotting
  "knitr",         # For tables and Rmd rendering
  "rmarkdown",     # To compile the report
  "kableExtra",    # Enhanced HTML/PDF tables
  "ggplot2",       # Visualization
  "dplyr",         # Data wrangling
  "tidyr",         # Data reshaping
  "broom"          # For tidying model outputs
))
```
### How to Run
1. Clone the repository:
```
git clone https://github.com/alexqiuu/Airplane_Factorial.git

cd Airplane_Factorial
```
2. Open paperairplaneproj.Rmd in RStudio

3. Install the required dependencies

4. Knit to PDF or HTML to generate the final report

