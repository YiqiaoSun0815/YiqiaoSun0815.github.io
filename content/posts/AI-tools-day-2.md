---
title: "AI tools lerning day 2"
date: 2025-12-23
categories: ["ai"]
tags: ["Powershell,github"]
draft: false
---
Today I encountered a question uploading my new post to my project.
The new Hugo post seems totally fine when I ran hugo server locally, but did not show up on my project page after deployment.I checked the Markdown file was in the correct directory, draft was set to false, the GitHub Actions workflow completed successfully, and there were no error messages. 

So I call GPT for help.The root cause turned out to be Hugo’s handling of “future” posts combined with a time zone difference. My post used a date of 2025-12-22. Locally, in Switzerland (CET, UTC+1), that date was already valid, so the post appeared during local development. However, GitHub Actions runs its build environment in UTC. At the time of deployment, the UTC date was still 2025-12-21, so Hugo interpreted the post as being dated in the future. By default, Hugo does not publish future-dated content, and it silently skips such posts without any error message.

Gpt helped me to find the solution.It's to make the build behavior explicit in the GitHub Actions workflow. By adding the --buildFuture flag to the Hugo build command, future-dated posts are included during the build, ensuring consistent behavior between local previews and the production site. And more importantly,changing the hogu.toml does not mean the post would be uploaded automatically,so I had to repost manually.After triggering a new workflow run, the post immediately appeared on the website.

The main lesson from this experience is that local builds and CI/CD builds are not the same. Time zones, default build flags, and environment differences can all affect the final output. When working with static site generators like Hugo, it is important to be explicit about build rules and to always consider how dates and times are interpreted in automated build environments.