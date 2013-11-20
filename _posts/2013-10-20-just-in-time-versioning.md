---
layout: post
title: Just-In-Time Versioning
tldr: Deck.js spent two years without any semantic versioning. Nobody complained. Here's why.
---

When [deck.js](http://imakewebthings/deck.js/) was published I didn't give it a version number. The first time I did this it was an accident, or at least innocent oversight, as I was making public a project without a long-term plan. This lack of versioning system has lasted to this day. In place of proper versions were two branches, `stable` and `master`. Changes were made to master. When they were vetted and felt right, they were merged into stable.

## It Worked for Two Years

Never in the history of the project have I received a complaint about the lack of semantic versioning. I'm inclined to chalk it up to people having the problem and not complaining to me, but considering that my inbox is full of complaints about every other conceivable matter I'm left to conclude that it *just isn't that important to the average user*. That is... for a project like this.

When an average user consumes deck.js they download it, edit slides, tweak a theme or two, give their presentation, and then they are **done**. There's no updating modules, no merging changes, no outdated plugins. Versioning never comes into play for these users. And for the power users or extension authors that rely on the core project, the fact of the matter is the API has not significantly changed in two years. In the world of semver, we'd probably be on the same minor release as day one.

But there comes a time where the API needs to become unstable, and that time is now.

## 1.0, 1.x, and 2.0

Deck.js version [1.0.0](https://github.com/imakewebthings/deck.js/archive/1.0.0.zip) is now available. 1.0 is nothing more than the current API that has existed for months (with a recent push of bug fixes.)

The important thing about a 1.0 release isn't the 1.0 code. It's that you have a code base against which to make minor and major changes. 2.0 means nothing without the 1.0 to compare it against. And I'm excited to work towards a 2.0. If you would like to follow along with the deck.js changes going forward from 1.0, take a look at [this GitHub ticket](https://github.com/imakewebthings/deck.js/issues/140).

