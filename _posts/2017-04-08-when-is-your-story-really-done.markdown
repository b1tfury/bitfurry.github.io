---
title: "When is your story really **done** done !!"
layout: post
date: 2017-04-08 20:00
image: /assets/images/markdown.jpg
headerImage: false
tag:
- agile
- lean-development
- continuous-delivery
category: blog
author: sahilkharb
description: When is your story or feature really dev done.
---

"A story or feature is dev done only when it adds value to the users."


The first and foremost important principle suggested in the [Agile Manifesto](http://agilemanifesto.org/) states that:
 
 "Our highest priority is to statisfy the customer through the early and continuous delivery of valuable software."
 
 Again we talk about adding/giving value for the users of our software. 
 
Let me talk talk the full cycle of a new feature or a story:

* It all starts from requirements, so the requirements must be discussed properly and well estimated.
* After estimation the development procedure starts. We should follow the best practices along with BDD/TDD.
* Once the development is finished on local machine of a developer, the code is pushed to remote, after which your CI pipeline is triggered.
* Unit tests are ran with test configs.
* If all unit tests passes at your CI system then functional tests should be ran in an production like environment.
* Now after functional tests passes we should promote the build as a release candidate.
* That promoted candidate should be deployed in a production like environment.
* Thorough testing should be done against the build. If all tests passes here then, we should *deploy to production*

Once the changes made related to the estimated story are deployed to production then only we can truly call story be completed.

Notes:

* Whenever we deploy or run tests on remote machines the config provided should come from one central source in all environments.
* Testing should be done as frequently as possible.
* Try to automate most of the above mentioned steps.
* Devs, QA and OPs people should work together and participate heavily in all sorts of discussion related to the story. They should never work in silos.