# The Fix That Fixes Half the Problem

*A non-technical introduction to "Two Problems, One Incomplete Fix"*

---

There is a standard procedure in quantitative finance research. When you are measuring
a signal that uses overlapping data windows, you apply something called Newey-West
standard errors. This corrects for a known statistical problem.

The procedure is correct. It is also incomplete. And the incomplete part is just as large
as the part it fixes — sometimes larger.

This post explains what Newey-West does, what it does not do, and why the distinction
matters especially when returns are fat-tailed.

---

## The setup

Imagine you are measuring a property of a stock using the last 3 years of its daily
return history. You update this measurement every month. Then you compare it to how the
stock performed over the following 3 months.

Here is the problem: that 3-month outcome period is partly in your 3-year measurement
window. The last 3 months of your measurement overlap with the outcome you are predicting.

This overlap creates two distinct statistical problems.

---

## Problem 1: The statistic is noisy in a predictable way

When you update your measurement each month, consecutive measurements share almost all
of their underlying data. Month 1 and Month 2 differ by only 21 days of a 756-day window.
Their measurements are almost identical.

This creates serial correlation — the mathematical term for "each measurement is highly
predictable from the previous one." When you run statistics on correlated data, standard
significance tests overstate how confident you should be. A result that looks like a
4-sigma finding might only be a 2-sigma finding once the correlation is accounted for.

**Newey-West fixes Problem 1.** It adjusts the standard error to account for this
correlation. The fix is correct and well-established. If all you had was Problem 1,
applying Newey-West and reporting the corrected result would be sufficient.

---

## Problem 2: The measurement itself is biased

Here is the part Newey-West does not fix.

The overlap between your measurement window and your outcome window does not just
create noisy statistics. It biases the *measurement itself*.

Consider a stock in a month when it had a strong 3-month return. Some of those strong
months are also in the historical window you used to compute your signal. Those good months
inflate your measurement — making the signal look stronger than it would look if you had
computed it without knowing the outcome.

The bias is *directional*: it pushes your measurement in the direction of the subsequent
outcome. And it is *systematic*: it happens for every observation, not just a few.

**Newey-West cannot fix Problem 2.** Standard errors describe the precision of an estimate.
They cannot correct for a bias in what is being estimated. The biased estimate, with
very precise Newey-West standard errors, is still wrong.

---

## How large is the bias?

In our data (106,163 stock-month observations, 2009–2025):

The clean, unbiased measurement shows: bottom-decile stocks outperform by +11.3 percentage
points over the following 2 months.

The biased measurement (same data, overlap not excluded): that spread collapses to −5.2
percentage points — the sign reverses entirely.

Newey-West applied to the biased measurement corrects the standard error. It does not
restore the +11.3pp result. The corrected test statistic on a biased estimate still
reflects the bias.

---

## The fat-tail amplification

This matters more for extreme stocks than for average ones.

Under normal (Gaussian) distributional assumptions, the bias from overlap is roughly
proportional to how much overlap there is. With 8% overlap, expect roughly 8% contamination.

Under fat-tailed return distributions — which are the typical condition for the extreme
stocks most researchers are interested in — this first-order estimate is too optimistic.
A single extreme return in the overlap period contributes disproportionately to the
measurement, because its magnitude relative to the average is much larger under fat tails.

We measured the amplification factor in our data: approximately 1.6 times the Gaussian
prediction. The bias is 60% larger than first-order analysis suggests.

---

## The diagnostic

There is a simple two-step test to tell whether your result reflects genuine signal or
Problem 2 bias:

1. Recompute the measurement excluding the overlap period entirely (use only data before
   the outcome window started). If your result changes dramatically — especially if the
   sign reverses — Problem 2 was driving it.

2. Apply Newey-West to the bias-free measurement (addressing Problem 1). If significance
   survives this, the signal is real.

A Newey-West result on a biased measurement does not pass this test. Our 12.9
percentage-point shift in the bottom-decile win rate shows exactly what "Problem 2 active"
looks like.

---

*The technical paper is available on SSRN (submitted June 2026, pending review). Chapter 4
of the working monograph at [book URL] contains the full mathematical decomposition and
the empirical results.*

*Next post: what all of this adds up to — a nine-question checklist for deciding whether
a quantitative signal is real or a measurement artifact.*
