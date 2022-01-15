---
layout: post
title: "git-blame-someone-else"
date: "2016-02-17 08:45:55 +1100"
category: link
tags: [git, authentication]
external-link: https://github.com/jayphelps/git-blame-someone-else
excerpt_separator: <!--more-->
---

<!--more-->

Neat hack: 

> Blame someone else for your bad code.
> "I love git-blame-someone-else!!" -[Linus Torvalds says](https://github.com/jayphelps/git-blame-someone-else/commit/e5cfe4bb2190a2ae406d5f0b8f49c32ac0f01cd7)

Essentially, this edits the (unsigned) git log and alters the listed author for the commit. Interestingly, GitHub seems to rely on this unauthenticated information when linking commits back to users, so the forged commit in the second link displays Linus' information. 

Mostly, this is amusing. It's also, though, a gentle reminder to problem and incident teams not to rely on unauthenticated data, even inside authenticated systems like source code control. If you need to rely on commit history, [sign your commits](https://git-scm.com/book/en/v2/Git-Tools-Signing-Your-Work).

([The comment thread](https://github.com/jayphelps/git-blame-someone-else/commit/e5cfe4bb2190a2ae406d5f0b8f49c32ac0f01cd7) is a weird journey in itself.)
