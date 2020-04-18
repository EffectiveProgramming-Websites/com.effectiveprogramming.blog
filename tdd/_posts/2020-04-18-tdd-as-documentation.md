---
layout: post
title: TDD, Naturally
teaser: Test Driven Development is a documentation exercise
author: LB
---

## The Basics

How does a developer normally add functionality to a software application? Most developers first run the application (to confirm the proposed functionality doesn't already exist) and then repeatedly update the code and re-run the application until said functionality exists. Update code, rerun application; back and forth; yin and yang &hellip; manually testing to see if the new functionality is working as required.

Did you catch that?

> testing to see if the functionality is working as required

For clarity, let's define the term [test](https://dictionary.cambridge.org/us/dictionary/english/test)

> an act of using something to find out if it is working correctly or how effective it is

So clearly, the hypothetical developer personified in this example is "using something (the application) to find out if it (code changes) is working correctly." But, is this developer practicing _Test Driven Development?_ Well, the answer to that question depends on who you are talking to and the context of the conversation but in the case of this post, yes, it does. The developer is constantly changing code and _testing_ to see if those changes have the desired result. In addition, the developer is relying on the outcomes of those _tests_ to drive their work. Test. Driven. Development.

In this manner of speaking then, I suspect that most every developer practices (or has practiced) _Test Driven Development_ as described in the manner herein. That likely means you are, in fact, practicing Test Driven Development, whether you know it or not! This is an important realization as it lays the groundwork for which to improve.

## Can We Do Better?

Let's identify this as a "first order consequence":

> Developer delivers new functionality to the application by alternating between writing code and testing the changes (running the application, verifying outcomes by confirming specific outcomes in specific scenarios)

Can we do better?

How about the review process? How can reviewers better understand (and verify) what the new code should and shouldn't do (and shouldn't break)? Acceptance Criteria documented in the story? Personal discussions with the responsible parties? How well does that scale? And how long can that sort of documentation live and be accessible? "Word of mouth" development is tenuous at best. It doesn't scale. Rules and edge-cases constantly change. Teams change. What can we do, in terms of Test Driven Development, to help alleviate _these_ concerns?

What if we could **document** the tests the original developer was scoping their work to - enabling reviewers and collaborators to _read_ through the tests and validate a high level understanding of the scope the original developer considered? What if we could **automate** the tests the original developer was scoping their work to - enabling reviewers to run the automated tests to make sure, at the very least, that the tests actually confirm the appropriate functionality. Turns out we can do both of these - and, in fact, generally improve the quality of the code! &hellip; and with that, we've landed on what most folks means when they ask about, propose or perform **Test Driven Development.**

## Wrap Up

Automating tests indirectly documents tests since developers must code the tests to run. In most cases, automating tests also helps improve the quality of the codebase, in part, because automating tests creates a secondary consumer of the related code. This secondary consumer helps to triangulate and force the code design to scale better. Test Driven Development actually makes YOU a better developer since it forces you to solve the immediate problem for 2 immediate users. Keep in mind that developers must still follow established best practices, ie: don't suddenly start exposing private functions publicly just for the sake of testing. At the end of the day, this is why it is typically easier to write test cases _while_ you are writing code as opposed to following up at a later date or once the new functionality has been released. Some scenarios may be impossible to automate under the current design and who wants to go back in and change something that is provably working in release.

Yes, yes - there are good and bad practices around automating tests but we will save that discussion for a future post. The point here is that Test Driven Development can be considered a simple extension of what every developer is already doing - and in embracing that, developers can better scope, guide and align their future TDD acumen with the general problem it is solving.
