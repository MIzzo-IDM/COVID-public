---
title: 'nCoV: incubation period distribution'
author: "Mike Famulare (Institute for Disease Modeling)"
date: "January 26, 2020"
output:
  html_document:
    fig_caption: yes
    fig_width: 4
    keep_md: yes
  pdf_document: default
---



## Summary

There are conflicting reports about the incubation period-- the duration from exposure to symptom onset--and this is a critical parameter for modeling clinical surveillance latencies and transmission dynamics.  From the partial line list curated by [kaiyuan@nih.gov](mailto:kaiyuan@nih.gov) and maintained in [this google sheet](https://docs.google.com/spreadsheets/d/1jS24DjSPVWa4iuxuD4OAXrE3QeI8c9BC1hSlqr-NMiU/edit#gid=1187587451), we used information from 63 subjects with known or estimated dates of symptom onset and exposure to infer the distribution of incubation periods observed in clinically-detected cases.  We find that individual-level incubation periods appear to be log-normally distributed, with median duration 5.4 (95% CI 4.2, 6.7) days, and that 95% of cases are estimated to have incubation periods between 2.0 (1.3, 2.9) and 14.5 (9.5, 25.2) days. 

This data suggests that the individual-level variation in incubation times is large. During surveillance, contacts of known cases should be monitored for at least 14 and possibly as many as 25 days before being declared disease-free. 

Note that this analysis only applies to clinically-detected cases, most of whom show significant disease activity.  It is unknown at this time if viral shedding and thus likely transmissibility parallels clinical severity, or if asymptomatic cases follow similar shedding dynamics to symptomatic cases. Note that reports of shedding during the incubation period may be conflating shedding from asymptomatic infections with shedding prior to symptom onset. 

Thus, this analysis does not currently inform models of underlying transmission dynamics without additional assumptions about the relationships between symptoms and viral shedding.  


## Methods

For subjects with known travel history from Wuhan to other parts of China, We conducted an interval-censored survival analysis for the distribution of times from putative exposure to symptom onset. Methods available at [github.com/InstituteforDiseaseModeling/nCoV](https://github.com/InstituteforDiseaseModeling/nCoV)

## Results
We compared exponential, Weibull, and lognormal models and found that the lognormal had the best fit by AIC, with Weibull insignificanlty lower and exponential strongly disfavored. The estimated lognormal model parameters are $\mu = 1.678 (1.453, 1.902)$ and $\sigma = 0.505 (0.336, 0.759)$. 

![Estimated incubation duration distributions (Kaplan-Meier, red; lognormal, black (95% CI dashed)). Incubation times at the individual-level are highly variable.
](incubation_from_linelist.png){width=480px}


The median duration and 95\% probability ranges are shown in Figure 2.

![Median and 95\% probability intervals for individual-level variation in symptom onset for clinical cases).
](incubation_from_linelist_summary.png){width=480px}





