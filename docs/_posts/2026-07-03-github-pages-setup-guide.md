---
layout: post
title: "GitHub Pages Setup Guide"
date: 2026-07-03 11:14:44 -0400
categories: general
---

Here's how I got this coding journal up and running:

1. **Create a new repository**: On GitHub create a new repository.
2. **Clone it locally**: Copy the HTTPS address to clone the repo to my local machine.
3. **Create a working branch**: Create a new branch called `antigravity` for the actual building before merging into `main`.
4. **Scaffold the site with Google Antigravity**: Prompt Google Antigravity to create a GitHub Pages site.
5. **Commit the changes**: Commit and push changes on the `antigravity` branch to my GitHub repo.
6. **Configure GitHub Pages settings**: On GitHub, go into the repository settings. Under the "Pages" section, set the build and deploy source to use the `docs` folder on the `main` branch. 
7. **Stick with Jekyll**: GitGub takes my Markdown files as input and generates HTML files.
8. **Keep the default domain**: Use the default `*.github.io` domain that GitHub provides.
9. **Merge to main**: Once GitHub Pages is configured, opening the `main` branch, merging from the `antigravity` branch, and then committing the merge publishes the site.
