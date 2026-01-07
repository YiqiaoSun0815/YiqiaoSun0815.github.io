---
title: "CFA-day-2"
date: "2026-01-07T09:00:00+01:00"
categories: ["financial"]
tags: ["CFA,Financial"]
draft: false
---
Day 2 — Compounding, Discounting, and Rate Conventions

In CFA-style valuation, compounding is the default: interest earns interest, and the timing of cash flows must be consistent with how the rate is quoted. The core idea is simple: a quoted rate is not always the rate you should use, unless its compounding frequency matches your cash-flow timeline.

The key relationship is the Effective Annual Rate (EAR), which converts a nominal quoted rate into the true annual growth rate:

EAR = (1 + r/m)ᵐ − 1

where r is the nominal annual rate and m is the number of compounding periods per year. Once compounding frequency is aligned, you can value cash flows using:

FV = PV × (1 + r/m)ᵐⁿ
PV = FV / (1 + r/m)ᵐⁿ

This matters everywhere: bond pricing (semiannual coupons), loans (monthly payments), and any DCF model. A common exam trap is using an annual rate directly on monthly cash flows, or mixing an effective rate with a nominal rate in the same calculation. Another frequent mistake is thinking “5% for 10 years ≈ 50% total return”—that’s linear thinking, not finance.

My takeaway: rate conventions are not “small details.” They are the bridge between a model and reality. If your rate and cash-flow timing are inconsistent, your valuation error can be larger than the difference between two investment choices—especially in bond and high frequence trading area.