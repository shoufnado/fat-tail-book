# The Stock Market Punishes You for Wanting Big Winners

*A non-technical introduction to "The Predictable Tail"*

---

Here is a thing that should not be true, but is: stocks with the most dramatic upside
potential — the ones with the biggest wins relative to their losses — tend to underperform
the boring ones over the following months.

Not by a little. At the extremes, the gap is enormous.

I measured this across 715 U.S. stocks over 16 years (2009–2025), using a simple metric:
for each stock, what is the ratio of average winning-day gains to average losing-day losses?
I call this payoff asymmetry (PA). A high-PA stock has gains that systematically dwarf
its losses in magnitude. A low-PA stock has losses that dwarf its gains.

The intuition says: own the high-PA stocks. They make more when they win.

The data says: own the low-PA stocks. They win more often, by more, over the following
two months.

**The numbers:**

Among the top 1% of stocks by PA (the most "lottery-like"), only 40.6% of signals
resulted in a positive 2-month return. The median return was −4.6%.

Among the bottom 10% (the least lottery-like, most "boring"), 63.6% of signals resulted
in a positive 2-month return. The median return was +4.9%.

That is a 23-point gap in win rate and a 9-point gap in median return, between stocks
that look exciting and stocks that look boring.

---

## Why does this happen?

The answer has a name: the equity lottery premium.

High-PA stocks attract a specific type of investor — one who is drawn to the possibility
of a large, infrequent win. Think of a small biotech that might find a cancer cure, or
a company riding a new technology wave. The story is compelling. The upside is real.

But enough investors chase that story that the price rises above what the fundamentals
justify. And when the exciting thing doesn't happen — which is most of the time — the
stock drifts down.

The exciting stocks are correctly described as exciting. The problem is that by the time
you have noticed they are exciting, their price already reflects it.

---

## The trap that fools most backtests

There is a reason most quantitative research does not find this. It is a measurement trap.

If you compute PA using *today's* data and then compare it to *past* returns, you will
find a completely different result: high-PA stocks appear to be strong performers.
Sometimes the apparent win rate is over 90%.

This is wrong. And the reason it is wrong is simple:

A stock that has already gone up dramatically will *also* show high PA — because those
dramatic up days are in the data you just used to compute it. You are measuring "stocks
that have recently won" and calling it "stocks with high upside asymmetry." Those are not
the same thing.

The correct measurement uses only data that existed *before* the evaluation period.
When you do that, the result flips. High PA underperforms. The gap between contaminated
and clean results is 35 percentage points.

This gap is not a quirk of our data. It is a consequence of how rolling-window statistics
behave. We work through the mathematics in detail in the technical paper (linked below).

---

## What this means

The standard mental model — "asymmetric upside is good" — is correct as a description
of how high-PA stocks *feel*. It is wrong as a prediction of how they *perform*.

The equity market prices excitement into the stock. You are paying for the experience of
potential; you are not getting paid extra for it.

The boring stocks — the ones with steady, unremarkable return histories — are
systematically underpriced relative to their actual subsequent performance. Not always.
Not everywhere. But systematically, across 16 years of data, across hundreds of stocks.

---

*The technical paper is available on SSRN (abstract_id=6899979). The full mathematical
treatment, including the Fama-MacBeth results and the look-ahead contamination analysis,
is in Chapter 1 of the working monograph at [book URL].*

*This is part of a series on fat-tail statistics and what standard financial methodology
gets wrong. Subscribe for future posts.*
