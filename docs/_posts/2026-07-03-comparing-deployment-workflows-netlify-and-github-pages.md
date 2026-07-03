---
layout: post
title: "Comparing Deployment Workflows: Netlify and GitHub Pages"
date: 2026-07-03 11:27:59 -0400
categories: deployment github netlify
---

Publishing a website using GitHub Pages is basically the same as Netlify.

## The Similarities: Commit-Driven Builds

In both GitHub Pages and Netlify, you can deploy by committing to a branch (typically `main`). Pushing a new commit to that branch automatically kicks off a build process. The platform copies your code, runs any necessary build commands (like generating a Jekyll site), and publishes the resulting static files to their content delivery network.

## The Netlify Advantage: Flexibility

Netlify isn't tied to a single version control provider, so you can use GitHub, GitLab, or something else. 

Furthermore, Netlify easily allows you to upload a folder of assets to deploy it without a build process.

## Why GitHub Pages for this Journal?

I wanted to play with GitHub Pages for this coding journal. I probably won't use it again, but just for the experience (you always learn something when you try something new) I'll stick within the GitHub world and see how it goes.