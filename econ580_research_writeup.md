# Institutions, Networks, and Growth: Estimating Heterogeneous Spillover Transmission via Double Machine Learning

**Jesse Schmolze** | University of Wisconsin-Madison | Research in Progress

---

## Overview

When one country experiences a growth boom, does that prosperity travel to its trading partners, and if so, how much of it actually lands? Standard models in international macroeconomics treat the absorption of cross-border growth shocks as a uniform, fixed parameter. This paper challenges that assumption. I argue that political stability acts as a filter for shock propagation: the same exogenous growth impulse radiates very differently across a trade network depending on the institutional environment of the receiving country. Countries with strong, stable political institutions absorb substantially more of their trading partners' growth than countries mired in political fragility, and the difference is large enough to matter for how we think about the gains from trade.

The question sits at the intersection of two well-documented but typically separate literatures. The first, rooted in Acemoglu, Johnson, and Robinson (2001), establishes that institutional quality has a first-order effect on long-run growth. The second, following Frankel and Romer (1999), documents that growth shocks spill across borders through trade linkages. I bring these together and ask whether institutional quality moderates not just the level of growth, but the capacity to absorb growth transmitted through the network. The answer, I find, is yes, and the gradient is steep.

---

## Data and Identification Strategy

The empirical analysis draws on a panel of 120 countries from 1996 to 2023. Real GDP and standard growth controls come from the Penn World Tables. Institutional quality is measured using the World Bank's Worldwide Governance Indicators (WGI), with WGI Political Stability emerging as the most economically and statistically significant moderator across a broad comparison of institutional indicators. I construct two engineered variables central to the analysis. The first is a network spillover term, defined as the trade-weighted average of lagged partner growth rates. If a country trades heavily with the United States and Germany and both grow rapidly in a given year, this term will be high for that country. The second is a trade-weighted average of partners' political stability, which captures the institutional quality of the broader network.

Estimating causal effects in this setting is difficult. Institutional quality correlates with dozens of macroeconomic and political variables, many of which independently affect growth. A standard OLS regression would conflate the absorption channel with these confounders, making causal interpretation impossible. I address this using the Double Machine Learning (DML) framework of Chernozhukov et al. (2018), which uses cross-fitted machine learning models to partial out high-dimensional confounders from both the outcome and the treatment variable before estimating the coefficient of interest. This approach imposes no functional form on the control surface while preserving a clean, interpretable estimate of how political stability moderates the absorption rate.

To push toward causal identification, I implement two instrumental variable extensions within the DML framework. The first is a Leave-i-Out (LOO) instrument, which severs the feedback loop inherent in network spillover measures by constructing each partner's spillover term while excluding the focal country from the calculation. The second uses commodity terms-of-trade shocks from the IMF database as an exogenous source of variation in partner growth. Both instruments independently confirm the baseline finding, and notably, both suggest the baseline DML estimates are a conservative lower bound on the true effect.

---

## Results

The baseline OLS regressions already point in a clear direction. Own political stability has a large, statistically significant positive effect on the absorption of partner growth shocks. More striking is what happens when the interaction between own stability and partner network stability is included: the individual terms lose significance while the interaction becomes highly significant, suggesting a complementary relationship between domestic and partner institutional quality that the prior literature has not examined. This finding is suggestive but not causal, and I treat it as descriptive motivation for the DML analysis.

The DML results confirm and sharpen this picture. The estimated absorption rate varies dramatically across the distribution of political stability. Politically unstable countries, those below the 33rd percentile of WGI Political Stability, exhibit an absorption coefficient near zero and statistically indistinguishable from zero. Countries at average stability levels absorb roughly 52 to 59 percent of a given exogenous partner growth shock. The most stable countries, above the 67th percentile, absorb between 86 and 116 percent of the shock, with IV estimates suggesting stable institutions may allow firms and investors to leverage into a growth impulse and amplify it beyond the original shock. The estimated functional form is linear in political stability with a slope of approximately 0.30 (p = 0.008) under the baseline, rising to roughly 0.90 under both IV specifications.

A key finding from the DML relative to OLS is that the apparent role of partner political stability largely disappears once high-dimensional confounders are controlled for nonparametrically. The interaction structure that appears in OLS, which suggests stable countries only absorb shocks if their partners are also stable, flattens into a nearly vertical relationship in DML space: own domestic stability is the dominant determinant of absorption capacity, regardless of partner institutional quality. This reframes the mechanism as internal rather than relational, institutional filtering is a property of the receiver, not a joint property of the trading pair.

---

## Contributions and Next Steps

This paper makes two contributions to the literature. First, it provides causal evidence that the absorption rate of cross-border growth shocks is not a fixed parameter but a strongly increasing function of the receiving country's political stability. This suggests that past models imposing a uniform absorption rate have been systematically misspecified, and that the benefits of trade-led growth are deeply conditional on institutional capacity. Second, it demonstrates how the DML framework can be applied productively to a high-dimensional macroeconomic panel setting where OLS would be unreliable due to collinearity and confounding.

The current draft is preliminary. Planned additions before final submission include stronger quantitative justification for the instrument validity, formal statistical tests motivating the use of DML over OLS, a more developed literature review situating the paper within the institutions-and-growth and international spillovers literatures, and a policy-facing discussion section. I expect the core empirical findings to hold, and likely strengthen, as the identification strategy is refined.

---

*Questions or feedback welcome at jschmolze@wisc.edu. Draft available upon request.*
