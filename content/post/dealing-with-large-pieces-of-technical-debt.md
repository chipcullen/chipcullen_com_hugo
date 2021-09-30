---
title: "How to Deal With Large Pieces of Technical Debt"
date: 2021-09-30T08:33:32-04:00
draft: true
slug: "how-to-deal-with-large-pieces-of-technical-debt"
description: "te"
tags: ["technical debt"]
custom_properties: []
---

At my work we've successfully navigated a few very large chunks of technical debt. One instance was [removing an old dependency](/how-we-removed-jquery/), but there has also been fixing issues picked up by linters, and converting to Typescript large pieces of applications. Having seen this happen, but also having seen instances where technical debt hasn't been addressed, I've come to learn this:

**The smaller the individual pieces of work, the greater the chance that a large piece of technical debt will eventually be addressed.**

And I mean _small_ - like, atomic level. One ticket = one file. _Really_ small.

Don't get me wrong - this will mean some up front problem solving and work. But I cannot stress enough how critical this is to success.

## Problem one: how can this improvement be made incremental?

The biggest obstacle to technical debt getting addressed is the change required being huge and being done all at once. If at all humanly possible, try to figure out how to incorporate the kinds of changes necessary on one file at a time without affectig other pieces of the application. For example, converting one file to TypeScript means other, non-TS-javascript files can still import from it. So, take it one file at a time.

There are, however, times when a massive change is just unavoidable. Things like switching from one major version of a language to the next (e.g. Python 2 to Python 3). The best advice I can give in a situation like this is to make sure you have good tests covering your critical functionality in place. And, ideally, those tests are observing your application from another point in the stack (e.g. front end e2e tests that verify a backend upgrade doesn't break anything).

## Problem two: identify each tiny piece of work, and turn it into an actionable task

If you're a manager, or anyone else responsible for creating tickets, I'm not gonna lie - this part is a slog. However, this kind of sweat up front will pay off huge dividends in terms of the work actually getting done.

If at all possible, investigate ways to [bulk-create tickets from a CSV](https://confluence.atlassian.com/servicemanagementserver/creating-issues-using-the-csv-importer-939937206.html). That is a _game changer_ for dealing with these kinds of issues.

## Problem three: get team buy in on how it's getting addressed, and the overhead involved

For the team involved, talk through what these atomic level pieces of work will mean. Things like: there will be a lot of PR's, so get ready for a lot of notifications.

## Benefits to atomic level pieces of technical debt
- Easy to pick up and work on, while between other tasks, or waiting on other people
- Easy to review when in a pull request. The smaller the changes = the easier it is for others to understand the changes and approve them with confidence.
- Easy to test the changes - if it's kept to say, one file,

