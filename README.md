Bridge Strike Severity Analysis — Network Rail
Predicting which railway bridge strikes are "serious" using binomial logistic regression.
A consultancy-style analysis for Network Rail, identifying the characteristics that make a bridge strike serious or potentially serious. Built on 8,020 real incident records (2017–2024), the project moves from descriptive profiling to a multivariable logistic regression model and translates the statistics into clear operational recommendations.

The business question
Where should Network Rail target intervention spend?
Network Rail looks after the infrastructure of most of Great Britain's railways and records every bridge strike — whenever a bridge is struck by a vehicle or its load. They wanted to understand what distinguishes a strike assessed as "Serious" or "Potentially serious" from the rest, and a brief summary of the results.

Of 8,020 bridge strikes, only 104 (1.30%) were serious — a small but high-stakes minority. The goal was to find the factors that drive that 1.30%.

Headline findings

Bridge type is the dominant risk factor. Overline bridges (road over rail) are ~14× more likely to produce a serious strike than underline bridges, even after controlling for every other variable (OR = 14.08, 95% CI 8.35–23.77, p < .001). Raw rates back this up: 10.45% of overline strikes were serious vs 0.66% of underline strikes.
Three regions stay significant after controlling for bridge type — Wales & Western (OR = 3.22), Southern (OR = 3.09) and North West & Central (OR = 2.70) are each ~2.7–3.2× more likely than Eastern to produce a serious assessment, pointing to causes beyond bridge mix alone. Notably, Scotland's Railway had the highest raw serious rate (2.50%) but is not significant once bridge type is controlled for (OR = 2.14, p = .059) — its raw elevation is largely explained by bridge mix.
Seriousness is declining. The odds of a serious strike fell ~14% per year across 2017–2024 (OR = 0.864, p = .003) — evidence that existing safety measures are working.
What doesn't matter independently: vehicle type, month and delay minutes all lose significance once bridge type and region are accounted for. Cars looked risky in isolation (4.66% serious rate) but that effect disappears in the full model — a clear example of confounding.


Method

Outcome: binary — serious / potentially serious vs not serious — so binomial logistic regression was the appropriate model.
Approach: built and compared four models — bridge type alone, vehicle type alone, region alone, and a full multivariable model — to separate genuine independent effects from confounding.
Model selection: judged on McFadden's pseudo-R², AIC, and likelihood-ratio tests against the null.
Handling missing data: the full model uses listwise deletion (N = 7,050; 970 records dropped for missing bridge type). Descriptive tables use the full N = 8,020.
Interpretation: estimates reported as log-odds and exponentiated to odds ratios, with 95% confidence intervals and Wald p-values throughout.


Tool: analysis carried out in Jamovi.


Model comparison
ModelPredictor(s)McFadden R²AICLRT p-value1Bridge type only0.156865< .0012Vehicle type only0.0491068< .0013Region only0.0251094< .0014Full model0.188859< .001
The full model wins on every fit statistic (lowest AIC, highest pseudo-R²). Notably, bridge type alone (Model 1) explains almost as much variation as the full model — reinforcing it as the dominant driver.

Recommendations to Network Rail

Prioritise protection for overline bridges — height barriers, signage and monitoring — since they carry by far the greatest serious-strike risk.
Investigate the high-risk regions (Wales & Western, Southern, North West & Central) for explanations not captured by bridge type — older stock, traffic volumes, or fewer protective measures.
Maintain current safety interventions, which the declining year-on-year trend suggests are effective.


Repository contents
FileDescriptionbridge_strike_report.docxFull written analysis — all 12 tables, model outputs and findingsbridge_strike_data.xlsxThe underlying incident dataset (8,020 records)README.mdThis summary

Skills demonstrated
Statistical modelling (logistic regression) · model selection & comparison · confounding and multivariable control · odds-ratio interpretation · translating analysis into business recommendations · data storytelling for a non-technical stakeholder.

Author: Sakina Petiwala — MSc Business Analytics & Consultancy, University of Hertfordshire.
