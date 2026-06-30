# arXiv Submission Packages — PINNED, DO NOT SUBMIT YET

> Status: Prepared and ready. Waiting for endorsement.
> Endorsement required for first-time submitters in q-fin categories.
> See ENDORSEMENT_REQUEST.md for the draft email.

---

## How arXiv endorsement works

1. You need one endorser per category (q-fin.ST, q-fin.MF, etc.)
2. An endorser is any active arXiv author in that category
3. You email them directly with a brief explanation and a draft of the paper
4. If they agree, they log into arXiv and endorse you — takes them 2 minutes
5. Once endorsed in a category, you never need endorsement again

Most researchers say yes if the work looks legitimate and the request is polite.
Target authors who cite the same prior work (Hill 1975, Taleb, Peters, Bailey/López de Prado).

---

## Paper 3 — Hill Estimator's Domain of Validity

**Target category:** q-fin.ST (Statistical Finance)
**Secondary:** math.ST (Statistics Theory)

**Title:** The Hill Estimator's Domain of Validity: Source-of-Tail Classification Reveals Systematic Misclassification in Power-Law Tail Analysis

**Abstract (arXiv format — 150 words max):**
The Hill (1975) estimator is consistent under regular variation of the survival function.
We argue this condition is violated, in the finite-sample sense, for equities whose extreme
returns arise from discrete binary events (FDA decisions, clinical trial readouts). For such
stocks, the top-k order statistics contain a non-vanishing fraction of jump observations as
n grows with k = ⌊0.10n⌋, making the estimator inconsistent for the structural tail exponent
α_S. The consequence is systematic misclassification within the Taleb (2025) taxonomy:
FAT_BINARY stocks (n=8) achieve −5.96% expected value per signal versus +7.74% for
FAT_STRUCTURAL stocks (n=70), a 13.7pp spread, across 106,163 stock-month observations
(715 U.S. equities, 2009–2025). Binary win rates are ~49% for both groups — the estimator
is blind to the distinction. Source-of-tail classification is a prerequisite for applying
the Hill estimator, not an extension of the existing taxonomy.

**MSC codes:** 62G32 (Statistics of extreme values), 60G70 (Extreme value theory)
**JEL:** C14, G11, G12, G14
**Keywords:** Hill estimator; regular variation; fat tails; source of tail; binary events;
mixture process; power law; misclassification; finite-sample consistency

**Files to upload:**
- [ ] Convert paper3_source_of_tail.md to LaTeX (paper3.tex)
- [ ] Compile to paper3.pdf
- [ ] Upload paper3.tex + paper3.pdf

---

## Paper 4 — Newey-West Two Problems

**Target category:** q-fin.ST (Statistical Finance)
**Secondary:** econ.EM (Econometrics)

**Title:** Two Problems, One Incomplete Fix: Newey-West Corrects for Overlap Autocorrelation But Not Overlap Bias, and Fat Tails Make the Uncorrected Problem Larger

**Abstract (arXiv format):**
The standard remedy for rolling-window statistics evaluated against overlapping outcome
windows is Newey-West HAC standard errors. This remedy is correct but incomplete: it
addresses serial correlation inflation (Problem 1) but not directional bias in the point
estimate (Problem 2). These require separate remedies. We formalize this decomposition for
the payoff asymmetry statistic PA = E[r|r>0]/E[|r||r<0] over a 756-day trailing window
evaluated against 60-day outcomes (overlap φ = 7.9%). Using 106,163 stock-month observations
(715 U.S. equities, 2009–2025), Problem 2 shifts the bottom-decile win rate by −12.9pp and
compresses a +11.3pp prospective spread to −5.2pp reversed — not corrected by Newey-West.
Under fat-tailed distributions (median α̂ = 2.69), Problem 2 is amplified ~1.6× beyond
O(φ) first-order prediction via a relative-influence mechanism on ratio statistics.

**MSC codes:** 62M10 (Time series), 62P05 (Statistical methods in finance)
**JEL:** C12, C14, G12, G14
**Keywords:** rolling-window statistics; Newey-West; overlap bias; serial correlation;
fat tails; payoff asymmetry; effective sample size; directional bias

**Files to upload:**
- [ ] Convert paper4_measurement_epistemology.md to LaTeX (paper4.tex)
- [ ] Compile to paper4.pdf
- [ ] Upload paper4.tex + paper4.pdf

---

## Paper 1 — The Predictable Tail

**Target category:** q-fin.PM (Portfolio Management)
**Secondary:** q-fin.ST

**SSRN:** 6899979 (already live — cross-link from arXiv)

**Abstract (arXiv format):**
We test whether payoff asymmetry (PA), computed prospectively from the Hill estimator of
individual equity return distributions, predicts forward equity returns. Using 106,163
stock-month observations (715 U.S. equities, 2009–2025), we find PA is a monotonic,
symmetric, inverted predictor: low-PA stocks (bottom decile) outperform with 63.6% win
rate and +4.90% 60-day median; high-PA stocks (top decile) underperform. The same tail
class (SUPER_FAT, α≤2) produces 70.4% win at the bottom of PA and 34.8% at the top.
Fama-MacBeth regressions fail to detect the signal (t=1.37) because it is nonlinear and
tail-concentrated. Common backtests are look-ahead-contaminated, overstating apparent
edge by 35+ percentage points. The mechanism is the equity lottery premium: high-PA stocks
exhibit positive-skew, negative-drift payoff structures; low-PA stocks exhibit positive
drift with occasional large left-tail events.

**Files:** See TrailMap/paper/payoff_asymmetry.pdf (existing PDF)

---

## Endorsement Request Draft

See ENDORSEMENT_REQUEST.md
