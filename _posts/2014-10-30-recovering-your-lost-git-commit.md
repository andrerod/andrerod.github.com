---
layout: post
title: "Recovering your 'lost' git commit"
category: posts
---

In my day to day projects, I mostly use [git](http://git-scm.com/) as the version control system.

Today I made a mistake on my local git clone and ended up discovering a neat functionality that I thought I should share.

Usually, before pushing my changes I do a “git reset –hard upstream/master” to reset my branch to whatever is latest, then I do a cherry pick to bring the change I worked on from another branch, and then I push it.

This ensures I have a clean history in git, without crazy merges that would make it harder to read / revert / tweak in the future.

Anyways...

So today what I did wrong was that I did a git reset –hard on the wrong branch and, fancy fancy, lost my change. After crying for the lost of hours of productivity (not really, but almost), I decided to investigate if there was a way to revert my mistake.

Turns out, there, usually, is.

"Git log –g" allows you to look into your git  "trash can" (i.e. what will be deleted in the next run of its garbage collector – which usually takes a few days of changes depending on how intensive / large are your coding sessions) and revert back to a commit.

In my case, I did:

``` bash
git log –g
```

Found the commit I wanted and did

``` bash
git reset –hard <commit id>
``` bash

And got my branch back to where I wanted it :)

Hopefully you won't ever need it, but in case you do, it may save you a few hours / days of redoing work.