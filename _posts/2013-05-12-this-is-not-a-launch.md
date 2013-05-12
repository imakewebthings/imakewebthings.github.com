---
layout: post
title: This Is Not a Launch
tldr: A how-to guide for creating a product with no features on purpose.
---

![A sketch of a rocket, under it written: Ceci n'est pas une lancement](https://s3.amazonaws.com/imakewebthings-blog/launch.jpg)

Two months ago I had a conversation with a potential new client over Skype. They said, "I've been reading through your blog posts. You mention how most people can [code in the open](/blog/deck-js-post-mortem-quick-hits/) and nobody will care, but then you [allude to a mysterious new thing](/blog/more-upfront-less-available/) you're working on without giving details. What's up with that?"

If that sounds combative, it was not. A friendly call-out. And the best question I've been asked in a while. These two statements absolutely contradict each other and I intend to resolve that dissonance with this post.

## Defining v1

Label it however you want &mdash; [MVP](http://en.wikipedia.org/wiki/Minimum_viable_product), [Lean](http://en.wikipedia.org/wiki/Lean_software_development), [Agile](http://en.wikipedia.org/wiki/Agile_software_development) &mdash; but let's make an assumption. You want to get a minimal core product out to the public, gather feedback, and start iterating as quickly as possible. This reduces wasteful upfront work and gets you listening to your customers instead. I buy into this.

The question becomes: What features should be included day one? We could come up with a wide array of ways to evaluate the necessity of features.

- Say yes/no to each feature.
- Select an arbitrary number of features and cull.
- Prioritize and build as many features as possible before a certain date.
- Do whatever The Boss says.

But I don't want to argue for these or any other way to evaluate features. If we accept that the waste and risk reduction of a minimal first release is good, and that fewer features minimizes that waste, the math says debating features is pointless. We should ship with zero features.[^1]

Well that's obviously stupid. So let's try it&hellip;

## Announcing DeckCloud's <del>Launch</del> <ins>First Feature</ins>

[DeckCloud](https://deckcloud.com) is a product with one feature: [Free and Pro accounts](http://blog.deckcloud.com/free-and-pro-accounts/). There's nothing else to do. You can create an account, and you can upgrade that account to a Pro account for $9/mo. The $9 subscription gives you zero extra functionality on top of the zero existing functionality.

**Great. Who cares?**

Exactly. You shouldn't care. Nobody should care about this product. Now that *that's* out of the way, now that I've subverted the importance of the "launch", I can start working on features and releasing them. Maybe, in time, those iterations will add up to something worthy of another human's money.

## All the Caveats

I'm not recommending everyone (or really, anyone) do this with their own apps. People have great reasons for building out a more mature app before the inititial release. But I don't have investors paying close attention to the size and growth rate of my user base. I'm not seeking a writeup in Forbes, a front-page Hacker News link, or a viral Twitter run. I don't need paying users right now. If these things describe you and your app, thank you for reading so long after it was obvious that this article was not aimed your way.

## The Answer to the Original Question

*How do you create a new product and do it in the open[^2] in a way that nobody will care?* Like this, by releasing a useless v1 and developing every feature "post-launch". From here forward I'll be announcing new features on the [DeckCloud Blog](http://blog.deckcloud.com) as soon as they're ready and not a second before. If you're interested in keeping up with the project, subscribe or sign up for the newsletter on the DeckCloud [homepage](https://deckcloud.com).

[^1]: Ok, so zero features may be where the math leads but it's logistically difficult. What does an app with zero features look like? A URL that resolves to a blank page? That **is** what DeckCloud has been for months&hellip;

[^2]: The DeckCloud app code will remain closed-source, but I intend to open-source as many pieces as possible. One such open-source component already exists: [jquery-confirms](http://imakewebthings.com/jquery-confirms)