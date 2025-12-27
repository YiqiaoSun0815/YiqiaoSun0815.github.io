---
title: "AI tools lerning day 3"
date: 2025-12-27
categories: ["ai"]
tags: ["Powershell,github"]
draft: false
---
Over the past two days, I ran into an unexpectedly frustrating issue while trying to customize the visual style of my Hugo site using custom.css. At first, it felt like nothing I changed actually worked.

The problem
I added a custom.css file and wrote several styles to improve typography and layout. However, no matter what I changed, the site looked exactly the same. Sometimes small changes appeared to work, sometimes nothing changed at all. This made the problem especially confusing, because I couldn’t tell whether my CSS was wrong or simply not being applied.

The debugging process
The first big mistake was assuming that “editing the file” meant “changing the active file.” In reality, my project had multiple possible CSS paths (assets/, static/, theme defaults), and I wasn’t always modifying the one Hugo was actually serving.

To isolate the issue, I stopped guessing and started verifying. I checked whether /css/custom.css could be opened directly in the browser. I inspected the page <head> to confirm whether the stylesheet was really being loaded. Finally, I added an extreme test style (changing the page background color) to prove whether the CSS was applied at all. When the entire page suddenly turned yellow, I finally knew the pipeline itself was working.

Another important realization was that PaperMod already looks quite “clean” by default. Subtle academic-style CSS changes can be technically correct but visually hard to notice. In some cases, my styles were also overridden by more specific theme rules, which required higher selector specificity.

The result and takeaway
In the end, the solution wasn’t just better CSS—it was a better workflow. I learned to verify the active file, confirm loading in the browser, and test changes in an obvious way before refining them. Most importantly, I realized that not all visual improvements should come from CSS alone. Structure and writing style matter just as much.

This experience reminded me that front-end debugging is often about eliminating uncertainty, not writing more code.