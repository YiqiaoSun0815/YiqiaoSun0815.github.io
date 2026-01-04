---
title: "AI tools lerning day 4"
date: 2026-1-4
categories: ["ai"]
tags: ["github,Hugo,page lesson"]
draft: false
---
Today I ran into a familiar but still frustrating problem:
everything looked fine locally, GitHub Actions showed a green checkmark, yet my new content simply didn’t appear online.

At first glance, it felt like a failed push. But it wasn’t.

The truth is, with Hugo + GitHub Pages, push success, build success, and site update are three different things. I had just added a new section (financial) instead of posting under the old posts folder. Locally, hugo server was forgiving and showed everything as expected. The production build was not.

The issue wasn’t the article. It wasn’t Git. It wasn’t even GitHub Actions.
It was configuration.

PaperMod, by default, treats only certain sections as “main content”. Since I never told Hugo that financial was a first-class section, the build technically succeeded but silently ignored what I cared about. No error. No warning,only leaving me confused and frustrated.

AI tools tould me to step back and look at the pipeline logically—source content → Hugo build → theme rules → deployment—it became obvious why this keeps happening. Static sites are brutally honest: they only generate what you explicitly describe.

The fix was simple: declare the new section properly, clean the build cache, and redeploy.

When local preview and production disagree, don’t panic and don’t rewrite content.
Check structure, sections, and assumptions. Most of the time, the system is doing exactly what you told it to do—even if that’s not what you meant.

This is one of those technical details that feels annoying in the moment, but quietly improves how you think about systems long term.

I'm thinking of restructure the website due to sooo many unexpected issues I had.