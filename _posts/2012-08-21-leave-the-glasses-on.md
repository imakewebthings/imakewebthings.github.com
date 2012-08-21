---
layout: post
title: Leave the Glasses On
tldr: When faced with a new programming paradigm just do what George Stratton did. Keep going and let your brain adapt.
---

115 years ago a UC Berkeley Psychology professor named George Stratton decided to [plaster a small tube to his face](http://www.cns.nyu.edu/~nava/courses/psych_and_brain/pdfs/Stratton_1896.pdf) for a total of 21&frac12; hours over three days. The lenses in this tube inverted his vision, turning the world upside down. Stratton theorized that with enough time the human brain could adapt to such a drastic change and function normally.

As expected, Stratton found his new spatial field difficult to navigate (emphasis mine):

> All images at first appeared to be inverted; the room and all in it seemed upside down. The hands when stretched out from below into the visual field seemed to enter from above. Yet although these images were clear and definite, they did not at first seem to be real things, like the things we see in normal vision, but they seemed to be misplaced, false, or illusory images between the observer and the objects or things themselves. **For the memory-images brought over from normal vision still continued to be the standard and criterion of reality.** The present perceptions were for some time translated involuntarily into the language of normal vision; the present visual perceptions were used simply as signs to determine how and where the object would appear if it could be seen with restored normal vision. **Things were thus seen in one way and thought of in a far different way.**

---

The Computer Science program at Cal Poly requires students to pass CSC 430: Programming Languages I. You might think by the title that this class teaches you various programming languages. It does not. You study the **anatomy** of languages but use just one: [Standard ML](http://www.smlnj.org/).

At the time, most coursework up to this point was written in Java or C. Standard ML is a relatively obscure functional programming language closely related to OCaml. This shift from object-oriented and imperative languages to a more functional one takes you out of your comfort zone. In C you might write a `sum` function for an array of integers like this:

{% highlight c %}
int sum(int arr[], int length) {
  int total = 0;
  for (int i = 0; i < length; i++) {
    total += arr[i];
  }
  return total;
}
{% endhighlight %}

In ML you might write it:

{% highlight ocaml %}
fun sum _ [] = 0
  | sum (x::xs) = x + sum xs
{% endhighlight %}

Initial reactions range from frustration, to panic, to depression. You don't know how to do the simplest things. This is one of the stated goals of the class, to throw students into the deep end of a different programming paradigm. After a couple years of navigating the [noun kingdom](http://steve-yegge.blogspot.com/2006/03/execution-in-kingdom-of-nouns.html) and finally getting comfortable, you're forced to start over.

With our knowledge and egos demolished we were tasked with a single ongoing quarter-long project: Write an interpreter. The language to interpret is D Flat, a fake stripped down subset of C#. Still, it's a sizeable task in a new field of study using an alien language. It can be daunting.

---

Stratton's preliminary attempt at his experiment left him more convinced than ever that the brain could adapt. It just needed more time. So he [strapped himself in](http://www.cns.nyu.edu/~nava/courses/psych_and_brain/pdfs/Stratton_1897.pdf) for longer, wearing his device for ~12 hours a day for eight days. After the third day he noticed some changes.

> It was becoming easier to follow a line in the field of sight and, continuing the line into this larger system of things, to know what it would lead to. The rooms beyond the one I was in, together with the scene out of doors, could be **represented in harmonious relation** with what I was actually looking at. Such representations, however, were more or less a **matter of voluntary effort**&hellip;

On the fourth day:

> By the fourth day the new experience had become even less trying. There was no sign of bodily discomfort, and for the first time during the experiment, **when nine o'clock in the evening came I preferred to keep the glasses on**, rather than sit blindfolded &mdash; which had hitherto been chosen as a welcome relief.

On day five:

> When the doors were open I could walk through the entire house by visual guidance alone, without holding out my hands in front of me to warn in case of a misinterpretation of the sight-perception. For the first time, I dared to turn and sit down on a chair **without beforehand assuring myself** with my hands that I had placed myself aright. My movements were of course still cautious and awkward.

Day six:

> Movements of the head or of the body, which shifted the field of view, seemed now to be in entire keeping with the visual changes thus produced; the motion seemed to be toward that side on which objects entered the visual field, and not toward the opposite side, as the pre-experimental representation of the movement would have required. And when, with closed eyes, I rocked in my chair, the **merely represented changes in the visual field persisted** with the same rhythmic variation of direction which they would have shown had I opened my eyes.

Stratton didn't just improved his hand-eye coordination. He began internalizing this new reality.

---

Like so many of of my CSC peers, I had to take 430 twice[^1]. The second time around was still a battle, but enough of the language's principles had seeped into my consciousness that I made it through. And while there were plenty of moments filled with pure frustration, those occasional dopamine-laden epiphanies made everything worth it.

Early in that same quarter our professor, Dr. Keen, shared with us his excitement over a language he'd been playing with during the summer. It had first-class functions, dynamic typing, and a **huge** install base. His enthusiasm was met with a typical mix of chuckles, eye rolls, and silent indifference as he went on to explain all the unexpectedly nice things he'd discovered about this language that was so often written off in academia: JavaScript.

---

Anyone coming to a new language, let alone a new family of languages, is going to face an upside down world. It's natural. For example, newcomers to JavaScript and Node.js might butt up against:

- Prototypal inheritance.
- Functional variable scope and the `this` keyword.
- Asynchronicity.
- Callback pyramids.

When we hit these snags we tend to do one of three things. Allow me to stretch this metaphor a bit further.

## Take the Glasses Off

You give up. You stop learning the new thing and go back to a stable reality. If that sounds condescending, know that I think this is **the best** option in many situations. If you need to get something done quick, that's hardly the time to explore a new technology. Stick with what you know. Be pragmatic.

But plenty of people get to this stage, meet resistance, take the glasses off, and declare their new subject broken. *Node Sucks*. *Ruby Sucks*. *NoSQL Sucks*. Articles of this ilk are scattered throughout space and time, and all but a rare few are written by people that have given up at [unconscious incompetence](http://en.wikipedia.org/wiki/Four_stages_of_competence#The_four_stages) out of impatience rather than pragmatism. Try not to be this person.

## Add a Second Pair of Glasses

That would certainly turn everything back upright. In Stratton's case, it would look ridiculous, but how does it look in our JavaScript scenario? Maybe you don't understand all these asynchronous callbacks in Node, so you start using [fibers](https://github.com/laverdet/node-fibers/). Prototypal inheritance is confusing, so you pick up [JS.Class](https://github.com/jcoglan/js.class) or [CoffeeScript](http://coffeescript.org/), something with a classical inheritance syntax. Are you nesting six anonymous callbacks and hate that all your code is so far to the right? [Async](https://github.com/caolan/async/) and [step](https://github.com/creationix/step/) have your back.

To be clear, I am **not** saying that these projects are bad and should be avoided. I think CoffeeScript can be great, and I use async constantly, but we need to recognize **why** we're using them. CoffeeScript is a great way to write clear, terse code and reduce the boilerplate that goes into the common patterns it abstracts away with new syntax. But using it to avoid learning how JavaScript works is a mistake. If you ever find yourself in a situation without your second pair of glasses (like say, the majority of Node modules) then you're right back where you started, lost.

Be conscious of why you're adding new technologies to your toolbox. Avoid doing it to cover up a fundamental knowledge gap.

## Leave the Glasses On

Yes, this is the hardest path, but it's ultimately the most rewarding. If you're serious about [mastering your craft](http://unicornfree.com/2012/why-blacksmiths-are-better-at-startups-than-you/), this is the only option. Push through and trust that your brain will adapt.



[^1]: In my defense, I didn't *exactly* fail the first time through. I had to bow out of all classes that quarter due to a serious illness. But in all honesty, I bet I would have failed anyway.