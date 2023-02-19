# longitudinal_minority_stress_BDD
## Overview
<p>This repository contains R coding files used to manage and analyze data supporting the following journal article:</p>
<p>
McGuire, F.H., Goldbach, J.T., Senese IV, J.G., Cabrera Jr., J.R., Schrager, S.M., & Duncan, A.E. (in press). Longitudinal association of homonegative school climate with body dysmorphic disorder among cisgender sexual minority adolescents: Testing mediation through proximal minority stressors. <i>Body Image</i>.
</p>
<p>
  <b>Abstract:</b> In a US national cohort study of cisgender sexual minority adolescents (SMAs), we prospectively (1) assessed whether within-person changes in homonegative school climate (i.e., school contextual factors that lead SMAs to feel unsafe or threatened) were associated with risk of probable body dysmorphic disorder (BDD) and (2) tested whether internalized homonegativity and negative expectancies mediated this association. Data came from consecutive time points (18-month, 24-month, 30-month) of the Adolescent Stress Experiences over Time Study (ASETS; N=758). The Body Dysmorphic Disorder Questionnaire measured probable BDD. Sexual Minority Adolescent Stress Inventory subscales measured past 30-day minority stress experiences. Multilevel models were specified with person mean-centered predictor variables to capture within-person effects. Across one year of follow-up, 26.86% screened positive for probable BDD at least once. Model results indicated significant total (risk ratio [RR]=1.43, 95% credible interval [CI]=1.35–1.52) and direct effects (RR=1.18, 95% CI=1.05–1.34) of homonegative school climate. Internalized homonegativity was independently associated with probable BDD (RR=1.28, 95% CI=1.12–1.46) and mediated 49.7% (95% CI=12.4–82.0) of the total effect. There was limited evidence of mediation via negative expectancies. Implementing SMA-protective school policies and targeting internalized homonegativity in clinical practice may reduce the prevalence and incidence of probable BDD among cisgender SMAs.
  </p>
This work was supported through funding from the National Insitutes of Health:
<li> National Institute of Minority Health and Health Disparities (grant number 1R01MD012252, PI: Goldbach)</li>
<li> National Institute of Mental Health (grant number T32MH19960, PI: Cabassa)</li>

## Structure of files in this respository
<ol>
  <li><b>Step 1: Data management.</b> The file "asets_dataManagement.Rmd" completes the following data management/cleaning tasks:</li>
  <ul>
    <li>Load the full cohort study data frame and identify the analytic sample.</li>
    <li>Derive variables (e.g., body dysmorphic disorder screening results) prior to missing data imputation.</li>
    <li>Impute missing data using multiple imputation with chained equations (`mice`).</li>
    <li>Derive/transform variables (e.g., person mean-centered predictor variables) after missing data imputation.</li>
  </ul>
  <li><b>Step 2: Regression analysis with brms.</b> The file "asets_regressionAnalysis.Rmd" completes the following data analysis tasks:</li>
  <ul>
    <li>Load the analytic sample data frame (with imputed data) produced in the data management file.</li>
    <li>Define regression model specifications (i.e., multilevel with random intercepts/slopes and Poisson outcome distribution to estimate risk ratios with binary data).</li>
    <li>For each imputed data frame, fit regression models using Bayesian Markov chain Monte Carlo (MCMC) sampling.</li>
    <li>Conduct sensitivity analyses (described in the journal article appendix).</li>
  </ul>
  <li><b>Step 3: Summary and interpretation of results.</b> The file "asets_results.Rmd" completes the following data/model summarization tasks:</li>
  <ul>
    <li>Create a directed acyclic graph (Figure 1) to visualize causal inference assumptions in the current study.</li>
    <li>Summarize sample demographic characteristics (Table 1).</li>
    <li>Create a correlation matrix of study variables across and within time points (Table 2).</li>
    <li>Summarize regression model results (Table 3).</li>
    <li>Report regression model convergence diagnostics (i.e., r-hat values, trace plots, posterior distribution skewness/kurtosis).
  </ul>
  <li><b>Step 4: Sensitivity analysis.</b> The file "asets_sensitivity.Rmd" completes the following sensitivity analysis summarization tasks:
  <ul>
    <li>Summarize results from sensitivity analysis 1 (including fixed effects of race/ethnicity and gender identity).</li>
    <li>Summarize results from sensitivity analysis 2 (respecifying the main analysis model with binary minority stress predictor variables).</li>
    <li>Respecify and report prevalence estiamtes where the "probable BDD" outcome variable includes those who primary concern was being "too fat" or "not thin enough."</li>
  </ul>
</ol>
