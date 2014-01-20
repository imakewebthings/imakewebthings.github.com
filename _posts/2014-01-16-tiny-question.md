---
layout: post
title: Tiny Question
tldr: Conference Q&A is broken. Tiny Question is one small tool to help fix it.
---

It's mid-afternoon on day 2 of the conference. Post-lunch sluggishness is wearing off and you're excited for the next session. You settle in, and for the next half hour watch the speaker completely nail it. Great topic, unique insights, and expertly presented. A well-deserved swell of applause.

> It looks like we have five minutes for questions.

Hands shoot up in the audience. The speaker scans the room and chooses one. You give no thought to how this hand was chosen. One of the conference volunteers runs a handheld microphone over to the questioner. This eats up some time considering the size of the room, but you're used to it. The conference last month used a standing microphone where inquiring minds hurried to queue. You also gave no thought to how that setup determined which questions were chosen.

The first question starts with some light self-promotion of the questioner's new startup. It isn't enough to force the conference volunteers to pull the mic away, but it is enough to make you roll your eyes. A question is eventually asked. The presenter answers. One&nbsp;down.

Hands up, volunteers run around, and question two begins. Except it's actually four questions, not that the questioner says this upfront. Once the first question is answered the questioner volleys with follow-up, then another answer and follow-up. This cycle continues until the presenter graciously asks the questioner to approach them later in private so that the room can move on to more questions. You sigh and wonder if the questioner is aware of their time monopolization.

The third question isn't a question. It's a long, meandering, incohesive statement only tangentially related to the topic. It's obvious that the questioner is only looking for a reaction from the presenter. Being a professional, the presenter gives their opinion despite the shaky intentions and form of the question.

Time is up. More applause. On to the next session.

## We Can Do Better

Odds are if you've been to a conference you've been to *that* conference, sat in *that* session. This is the status quo for conference Q&A sessions and it is broken. Among my complaints:

- **Question Quality**: Nobody has any idea how good a question will be until it leaves the questioner's mouth. By the time this happens the crowd and presenter have already promised to give the question time and attention, regardless of quality. This strikes me as backwards.
- **Questioner Selection**: In our prototypical example above, the best-case scenario when the crowd raises hands is *random questioner selection*. Worse yet, the speaker may select based on people they already know or by a bias, conscious or unconscious. If you use a first-come first-serve line, you're chosing questions by who has the fastest feet and least fear of speaking in front of a crowd.
- **Time Management**: There are probably no checks on how long it takes to ask a question. A long question may distill well into a five-second question, but what comes out at a microphone is typically a first draft. Are we surprised that first drafts are awkward, unclear, overly long, and stray off topic?
- **Identity**: Who the questioner is and what information you would like to know about them depends on which person you are in the room. If you are a fellow attendee, you probably don't need to know much. The question is the important part. For the presenter, the question is obviously still important but you may also be interested in connecting with the questioner later, perhaps to answer the question in more detail and provide additional resources. "Hi, my name is Questioner, I work at Company, and my question is," does a terrible job of providing a useful identity for both parties. For the rest of the crowd it is wasted time. The presenter isn't given a great way to connect with you again outside of a Hail Mary Google search.
- **Unasked Questions**: Not just the raised hands that never get chosen. There are tens or hundreds of questions, great questions, locked away in the heads of those unwilling to raise their hands. Maybe they're nervous. Maybe they think their question is stupid. We'll never know.

## Attempting to Do Better

[Tiny Question](http://tinyquestion.com) is a dead simple tool designed to improve the conference Q&A experience. Here's how it works.

1. The presenter logs in to Tiny Question (via Twitter) and creates a new&nbsp;question session.
2. The presenter shares the URL of this question session with the audience. This is usually done by putting the URL somewhere in the opening slides and telling the audience that there will be Q&A after the presentation, but that questions will be read from this session and not from the microphones.
3. Audience members who open the URL will also be asked to log in via Twitter. Once they do, they'll be able to ask questions on the page. As others ask questions, those too will be displayed.
4. Audience members can upvote questions. Questions stay sorted in vote order so higher upvoted questions float to the top.
5. After the presentation is over, the presenter opens the question session page, sees the questions sorted by upvotes, then reads and answers them as time permits.

Let's look at my complaints once again.

- **Question Quality**: Questions are now seen beforehand and voted on by the crowd. High quality popular questions float to the top.
- **Question Selection**: The idea of the presenter selecting a questioner is almost completely discarded. Selection is moved to the collective audience. The presenter does have final say on what's answered, as they could just skip over a highly upvoted question, but the crowd will be aware of what questions were skipped, which is interesting information as well.
- **Time Management**: Typing the question gives questioners the ability to pause, think, and self-edit questions. Presenters can also use their expertise to summarize and rephrase the question when reading it aloud.
- **Identity**: Questions are presented next to the Twitter thumbnail of the questioner, which links to their Twitter profile. Other audience members are no longer forced to hear the short bio of every questioner. Presenters are given an identity that they can contact after the presentation for followup.
- **Unasked Questions**: The pool of questioners is no longer limited to the outgoing and luckily chosen. There is a tradeoff though. The pool is limited to those with a Twitter profile and a connected device capable of loading a webpage. This limitation makes an argument for holding mixed sessions, where questions are fielded both on Tiny Question and live. It depends on the audience.

Like everything else on the web, this is an ongoing experiment. I hope this method can help solve some of the problems laid out above. We'll see if it does.

Tiny Question is free for anyone to use. The source is available on [GitHub](https://github.com/imakewebthings/tinyquestion) should you want to create your own version of the service. Pull requests are welcome.

## Ask Me Questions

Do you have a question about Tiny Question? <del>Ask it here (on Tiny Question) and I will update this post with answers.</del> Questions are closed. One more thing to note about Tiny Question: All question sessions are deleted 48 hours after creation. The tool is not meant as a permanent place for questions to live, but as an aid to a live event.
