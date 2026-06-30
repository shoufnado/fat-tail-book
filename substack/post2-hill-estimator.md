# The Measuring Tool That Cannot Tell Two Opposite Things Apart

*A non-technical introduction to "The Hill Estimator's Domain of Validity"*

---

Imagine you have a thermometer that reads 38°C whether you have a fever or whether
you just stepped out of a hot shower. Both readings are accurate, in a narrow sense.
But the thermometer cannot tell you which situation you are in — and those two situations
require very different responses.

Something similar happens with one of the most commonly used tools in financial tail-risk
analysis. It is called the Hill estimator. It produces a number — a tail exponent — that
summarizes how extreme a stock's return distribution is. The lower the number, the fatter
the tail, the more prone to extreme swings.

The problem: it produces the same number for two very different types of stocks, whose
actual investment outcomes are almost opposite.

---

## Two types of extreme stocks

The first type I call **structurally fat-tailed**. These are companies — often in energy,
financials, or utilities — whose extreme return days are just the natural result of their
business: volatile, but following a continuous distribution. Think of a leveraged real
estate company during a rate shock, or an oil producer during a commodity swing.

The second type I call **binary-event driven**. These are companies — almost entirely in
biotech and pharmaceutical development — whose extreme return days happen for a specific
reason: an FDA approval or rejection, a clinical trial success or failure. On those days,
the stock can move 50–80%. On all other days, it is relatively quiet.

Both types show up as "SUPER_FAT" in the standard tail-risk taxonomy. The measuring tool
cannot distinguish them.

---

## What the data shows

In a sample of 715 U.S. stocks measured over 16 years:

**Structurally fat-tailed stocks (70 stocks):** expected outcome of +7.74% per signal.

**Binary-event stocks (8 stocks):** expected outcome of −5.96% per signal.

That is a 13.7 percentage-point gap — between stocks that the standard tool classifies
as equivalent.

Here is the most revealing statistic: if you ask "what fraction of signals for each group
result in a positive return over the next two months?", the answer is approximately 49%
for *both* groups. The measuring tool cannot even tell you which direction to expect.
It is as informative as a coin flip on that question — for both types of extreme stock.

---

## Why does the tool fail?

The Hill estimator works by looking at a stock's most extreme return days — the top 10%
of its largest moves. It measures how rapidly these extremes thin out as you go further
into the tail.

For structurally fat-tailed stocks, this works as designed. The extreme days are
samples from a continuous distribution, and the estimator correctly characterizes it.

For binary-event stocks, the extreme days are not samples from a continuous distribution.
They are the resolution of a discrete binary event — approve or reject, success or failure.
Those events occupy specific, stable positions among the most extreme return days.
They do not blend into the continuous tail the way the estimator assumes.

The mathematical consequence: the estimator converges to a number that mixes together
the continuous structural tail and the discrete event component — in a way that cannot
be untangled from the output alone.

---

## What to do instead

Before applying the tail estimator, classify the stock by source of tail:

- Is the company subject to large, scheduled binary events with known structure?
  (Phase 3 readout, FDA PDUFA date, regulatory vote) → classify as binary-event driven.
- Otherwise → apply the estimator normally.

This is not a criticism of the underlying taxonomy (which is valuable and correct for
continuous power-law distributions). It is a prerequisite step: know whether the measuring
tool is appropriate for this specific stock before using it.

---

*The technical paper, including the full mathematical inconsistency argument, is available
on SSRN (submitted June 2026, pending review). Chapter 3 of the working monograph at
[book URL] contains the complete formal treatment.*

*Next post: why applying Newey-West standard errors to overlapping-window statistics
fixes one problem but misses an equally large second problem — and leaves researchers
thinking they have solved something they have not.*
