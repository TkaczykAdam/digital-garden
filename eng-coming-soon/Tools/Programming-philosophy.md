---
title: 👨‍💻 Programing philosophy
description: My opinions
---

# ✨ Programming Philosophy

> Simplicity is a key to better maintainability.

## ORMy

I'm not a fan of ORMs. I prefer query builders, they are closer to the SQL and you can use the full power of SQL. Very often, developers are picking the ORM because they don't want to learn SQL. For the hello world app - that is enough but if we need more data (and *No God, Please No* compute something *in the fly*) the problems begin. So, developers are learning HQL or something similar. And at the end, the query is not working as we want, performance is bad, generated SQL is crap 🙂. Don't learn bloody ORMs, learn SQL!

My favorite combo is [knex](https://knexjs.org/) + [objection](https://vincit.github.io/objection.js/). My opinion about ORM is similar with this [post](https://blog.logrocket.com/why-you-should-avoid-orms-with-examples-in-node-js-e0baab73fa5/). 

## TS

Many developers things that *if you know JavaScript, you can switch to TypeScript*. No, you can't. Before you start rewriting your codebase, consider these things:

- explicit and implicite typing (we want to use the first one only if we have no choice (+ there are exceptions 🙃)),
- types as sets,
- type guards and control flow analysis,
- build-in types,
- tooling (bundling, eslint, yarn berry support, etc.),
- advanced TS (exhaustive checks, discriminated unions, etc.)
- limitations and traps in TS,

Additionally:

- why do you need TS in your project? If the codebase is large but well tested and there is no need to develop/maintain, adding types because of YEY TYPES is pointless,
- can you prepare the **whole** tooling? Remember about Docker and CI too,
- Does your team know TS? Do they know about the things listed above?

If you are not prepared for any of these points, you are unlikely to be ready for TS. 

## Error handling

Error handling should be a first-class citizen in every app. Especially in JS apps, when you can even throw a unicorn emoji 🦄. Normally it should be in pair with proper monitoring (e.g. Sentry)

## Performance

> premature optimization is the root of all evil

This famous quote by Sir Tony Hoare (popularized by Donald Knuth) has become a best practice among software engineers. Performance optimization isn't an easy thing. During performance optimization, you cannot rely on intuition. *Oh, **looks** like it's loading faster. Fixed.* You should always have a unit to measure. For frontend, it could be devtool and lighthouse. For backend, it could be more complex but the average request time or some data from K8s dashboard could be useful.

## Battle-tested solutions

Getting excited about new trends is not good. I like the statement that every time you say * JS library *, a new lib has been added to the npm registry 🙂. Recently (December 2021) I faced a challenge. I had to migrate the legacy frontend written in HBS to something else. I had the privilege of being able to choose what I wanted. SvelteKit, something custom with Tailwind, or something new from Shopify - Hydrogen? None of these things. I chose NextJS + MUI. The oldest of the above, but also the most popular and best supported. Almost every problem to google, lots of good practices, good performance, secure, etc.

## Motivation

Sleeping with a problem, going for a run, talking to other devs - it's all cool, but nothing is as motivating as Steve Ballmer chanting: DEVELOPERS, DEVELOPERS, DEVELOPERS...!

{% embed url="https://www.youtube.com/watch?v=Vhh_GeBPOhs" %}
