# Institutional Trust and Electoral Participation in the Arab World

Does trust in national institutions make people more likely to vote, or less?
The literature points both ways: trust can signal legitimacy and mobilise, or it
can signal satisfaction and demobilise. This repository holds the analysis behind
a two-part empirical test of that question across twelve Arab countries.

**Data.** Arab Barometer, Wave VII (2021–2022): Algeria, Egypt, Iraq, Jordan,
Kuwait, Lebanon, Libya, Mauritania, Morocco, Palestine, Sudan and Tunisia,
sampled by stratified probability design. Analytic sample **N = 20,034** after
excluding "Don't know" and "Refused" responses.

**Outcome.** Self-reported turnout in the most recent parliamentary election
(`Q301A`, binary).

**Main predictor.** Trust in the national government (`Q201A_1`), four-point
ordinal scale, reversed so higher values mean greater trust.

---

## Contents

| File | What it is |
| --- | --- |
| `RR1.qmd` / `RR1.html` | **Report 1** - main specification: linear probability and logistic models, country fixed effects, HC1 robust standard errors, average marginal effects |
| `Research_report.qmd` / `Research_report.html` | **Report 2** - extends the analysis to political interest and cross-country interaction models |

---

## Methods

- **Linear probability models** as the main specification, so coefficients read
  directly as percentage-point changes in the probability of voting. Logistic
  models reported alongside, with average marginal effects for comparability.
- **Country fixed effects** and **heteroskedasticity-robust (HC1) standard
  errors** throughout.
- **Missing data** handled by multiple imputation by chained equations (`mice`),
  with complete-case results reported for comparison.
- **Robustness** assessed by **specification-curve analysis** (`specr`) across
  the space of defensible control sets and codings, rather than a single
  preferred model.

---

## Reproducing the analysis

Arab Barometer microdata are free to use but require registration, and their
terms do not allow redistribution — so the data files are not in this repository.

1. Download the Wave VII cross-country file from
   <https://www.arabbarometer.org/survey-data/data-downloads/>
2. Place it in `data/raw/`
3. Restore the package environment and render:

```r
renv::restore()
quarto::quarto_render("RR1.qmd")
```

---

## Limitations

Turnout is self-reported, and over-reporting is well documented in survey
research. The design is cross-sectional, so all estimates are associational, not
causal. Country fixed effects absorb time-invariant national differences but do
not address individual-level confounding.

---

## Author

**Houda ES-SQALLI** — MSc student, Behavioral and Social Sciences for Public
Policy, Mohammed VI Polytechnic University (FGSES), Rabat.

## License

Code released under the MIT License. Arab Barometer data remain subject to the
Arab Barometer's own terms of use.
