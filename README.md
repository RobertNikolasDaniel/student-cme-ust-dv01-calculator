# student-cme-ust-dv01-calculator

A simple educational project for estimating CME Treasury futures DV01 exposure using CTD mechanics.

This is not meant to be a production risk engine or a Bloomberg replacement.  
The goal is much simpler:

> understand what Treasury futures are actually exposing you to.

Most students (and honestly a lot of finance people) think:
- “I own 10 contracts”
- “I’m long bonds”
- “I’m bearish yields”

…but the actual risk lives in the DV01.

---

# What This Calculator Does

The spreadsheet:
1. Takes the CTD bond characteristics
2. Estimates CTD DV01
3. Adjusts using the CME conversion factor
4. Calculates futures DV01
5. Calculates total position DV01

That’s it.

Simple.  
Clean.  
Functional.

---

# Core Concept

Treasury futures are deliverable contracts.

The short can deliver from a basket of Treasury securities, but the contract tends to behave like the:

> Cheapest-To-Deliver (CTD) bond.

Because of this, futures exposure is not simply:
- contract count
- notional size
- “long bonds”

The actual sensitivity depends on:
- CTD duration
- CTD price
- conversion factor

---

# Core Formula

## CTD DV01

\[
\text{CTD DV01}
=
\left(
\frac{\text{Price}}{100}
\right)
\times
\text{Face Value}
\times
\text{Modified Duration}
\times
0.0001
\]

## Futures DV01

\[
\text{Futures DV01}
=
\frac{\text{CTD DV01}}
{\text{Conversion Factor}}
\]

---

# Example

| Input | Value |
|---|---:|
| CTD Price | 108.50 |
| Modified Duration | 7.35 |
| Conversion Factor | 0.8125 |
| Face Value | 100,000 |

Results:

| Output | Value |
|---|---:|
| CTD DV01 | ~$79.75/bp |
| Futures DV01 | ~$98.15/bp |

Meaning:
- a 1bp move in rates changes the futures contract value by roughly $98.

---

# Why This Matters

Treasury futures are one of the largest interest rate markets in the world.

Understanding:
- DV01
- duration
- CTD mechanics
- conversion factors

is foundational for:
- macro trading
- fixed income relative value
- hedge funds
- rates desks
- Treasury basis trading

This project is intentionally lightweight and educational.

No overengineered dashboards.  
No fake machine learning.  
No “AI powered finance platform” nonsense.

Just:
- inputs
- formulas
- rate exposure

---

# Future Ideas

Potential future additions:
- CTD switching analysis
- Deliverable basket analytics
- Yield curve hedge ratios
- Treasury futures butterflies
- Implied repo calculations
- Historical futures DV01 tracking

But for now:

> the point is understanding the mechanics first.

---

# Disclaimer

This is an educational student project only.  
Not financial advice.  
No guarantee of pricing accuracy or production suitability.

---

# Final Thought

A surprising amount of finance becomes easier once you stop thinking in:
- price
- contracts
- notional

and start thinking in:
- exposure
- sensitivity
- risk per basis point.
