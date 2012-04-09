---
layout: post
title: Automating Tedium
tldr: Love the command line? Hate the command line? Either way, you should consider using a terminal automator.
---

On a [recent episode](http://shoptalkshow.com/episodes/011-with-jina-bolton/) of [ShopTalk Show](http://shoptalkshow.com) Chris Coyier voiced his personal preference for using a suite of UI applications over running a bunch of shell commands in the terminal.

<script src="http://api.html5media.info/1.1.5/html5media.min.js"></script>
<audio src="http://s3.amazonaws.com/imakewebthings-blog/ShopTalk_011_Clip.mp3" controls="controls">&nbsp;</audio>

> I should say that I'm not afraid of it, I just prefer most things &mdash; like I use Sass all day long, right? I don't want to go into the terminal, `cd` to where my thing is, and go `sass --watch` and then `--` and then the stupid formats and all that stuff. And then every time I restart my computer I have to open it up and do it again. I would rather use something like [LiveReload](http://livereload.com) or [CodeKit](http://incident57.com/codekit/) that just automatically starts when I turn on my computer, it's automatically watching those directories for changes. I prefer UIs.

Here's where I'm supposed to say, "Bullshit! Learn the command line," and then check my d20 to see if the hit was critical. Except he's right. Doing all that stuff **is** annoying. Between CSS preprocessing, JavaScript transcompilation, image optimization, concatenation, minification, and source control, your average dev needs to launch a navy just to make their Hello World blink. Nobody wants to have to remember and type all this crap.

## Another Option

I'm no command line junkie. Borderline competent, at best. Yet I find myself in projects that require something to happen in the command line. Spin up a node.js process. Connect to a local Mongo database. `rails c`. There's no fancy omnipotent Cocoa app that will manage these things for me. The good news: I don't even try to remember it all.

{% highlight ruby %}
before { run 'cd ~/Sites/imakewebthings.github.com' }

tab :name => 'Jekyll' do
  run 'rvm 1.8.7'
  run 'jekyll --server'
end

tab :name => 'Sass' do
  run 'sass --style expanded --watch css:css'
end

tab :name => 'Git' do
  run 'git st'
end

run 'subl .'
run 'open http://0.0.0.0:4000'
run 'exit'
{% endhighlight %}

This is a [Consular](https://github.com/achiu/consular) script. The Consular script for this blog, as a matter of fact. Consular is a terminal automator written by [Arthur Chiu](https://github.com/achiu). You create projects which are nothing more than a Ruby file like the one above. This file defines any number of terminal tabs and the processes to run within them. From then on you can just type a few words into the command line and the whole thing is executed. No more trying to remember the tedious crap.

To install Consular:

1. `gem install consular`
2. Install the consular core for whatever terminal app you use. I use [iTerm2](http://www.iterm2.com/) so it's `gem install consular-iterm`. The project page has a list of all the supported cores and their corresponding gem names.
3. `consular init`
4. Open the newly created `~/.consularc` file and add a require statement for your core to the top. The project page for each core will have this snippet. For iTerm it's `require 'consular/iterm'`.

Now you can create projects with `consular create projectname`. Write the "Termfile" like the one above. Then you can launch the project with `consular start projectname`. Let's take a look at that project definition from earlier, line by line, to see what it does.

{% highlight ruby %}
before { run 'cd ~/Sites/imakewebthings.github.com' }
{% endhighlight %}

Anything in a `before` block is executed immediately and at the beginning of every new tab creation. Since I may be anywhere in the file system when I run the `consular start` command, I want to make sure I go to the project directory. Many terminal apps also have a default setting to go to the home directory when creating new tabs rather than keep the location from the previous tab. There are settings to change this, but it's good to know this annoyance is out of the way regardless.

{% highlight ruby %}
tab :name => 'Jekyll' do
  run 'rvm 1.8.7'
  run 'jekyll --server'
end
{% endhighlight %}

If you can believe it, `tab` blocks create a new tab. You don't have to name your tabs, but I prefer it. Inside that tab I switch to ruby 1.8.7 and start up [Jekyll](https://github.com/mojombo/jekyll/wiki), the static site generator that powers this blog.

{% highlight ruby %}
tab :name => 'Sass' do
  run 'sass --style expanded --watch css:css'
end
{% endhighlight %}

Here is the `sass` watcher Chris brought up. For tabs that only have one command you don't even need to place commands inside a block, you can just pass it the string to execute. For example: `tab 'tail error.log'`.

{% highlight ruby %}
tab :name => 'Git' do
  run 'git st'
end
{% endhighlight %}

Runs `git status` just to see where things are. Since this tab doesn't have a running process like the others, it's also where I do any terminal work going forward. Because our original tab that everything started from is about to go away.

{% highlight ruby %}
run 'subl .' #Opens project directory in Sublime Text 2
run 'open http://0.0.0.0:4000/blog'
run 'exit'
{% endhighlight %}

It is in no way a requirement of a Consular script, but if I'm using it to create tabs I run `exit` at the end. This closes the original tab. That original tab may be unnamed or named from a previously run script, and I no longer need or want it. Before exiting I launch anything that needs launching but doesn't concern itself with the terminal. In this case, I open the local Jekyll instance in my default browser and open the project directory in [Sublime Text 2](http://www.sublimetext.com/2).

## Who Shouldn't Use This

**If you're a purely front-end developer**, you work on mostly static web projects, and *never* need to touch the shell then by all means, grab CodeKit and [GitHub for Mac](http://mac.github.com/) and be happy. This is probably your ideal setup. If you can avoid using the command line altogether, that's awesome. But keep reading. You may have reasons for using a terminal automator beyond your development projects.

**If you do everything in vim**, remote pair-program, have never sullied the hair on your neck with the edge of a razor, or otherwise spend **a lot** of time on the command line then you want something more advanced. But if you fit this description, you already know about [tmux](http://tmux.sourceforge.net/) and [tmuxinator](https://github.com/aziz/tmuxinator) and stopped reading a long time ago.

## Not Black and White

Here's a false dichotomy for you. *Either you use the UI tools or you rock the command line.* Keep this from creeping into your head. These tools don't have to be used exclusive of each other. You can easily use something like Consular to launch a bunch of apps and quit the terminal altogether. Let's take a look at my script for [Waypoints](http://imakewebthings.com/jquery-waypoints):

{% highlight ruby %}
run "cd ~/Sites/waypoints/jquery"
run "subl ."
run "open http://local.jquery.waypoints.com/test"
run "open http://github.com/imakewebthings/jquery-waypoints/issues"
run "git st"
{% endhighlight %}

Aside from the `git st` I'm just launching applications. Two Chrome tabs and Sublime. If I didn't use git from the command line this could just as easily end with&hellip;

{% highlight ruby %}
run "github" # You've installed the GitHub for Mac command line tool, right?
run "exit"
{% endhighlight %}

I find this terminal-less ending appealing because it hints at what we're **really** doing with these scripts.

## Come for the Terminal Automation, Stay for the Context Switches

If there's anything we can agree on as an industry it's this: [Context switches are bad](http://www.joelonsoftware.com/articles/fog0000000022.html).[^1] But even in the most optimal environment &mdash; free from interrupting phone calls, hour long "design meetings", and shoulder-perched micromanagers &mdash; there will come a time when you need to switch contexts on purpose. Let's look at a contrived but plausible day in the life of yours truly (computer activities only):

- Wake up. Check email.[^2]
- Work on *Client Project*.
- Eat lunch. Check email.
- Work on *Client Project*.
- After dinner, fix a bug in Waypoints.
- Make an improvement to a transition theme in deck.js.
- Work on a draft of this blog post.
- Check email.
- Screw around. Facebook, games, read blogs, fantasy baseball, etc.

You know what I do when I want to work on *Client Project*, Waypoints, this blog, or any other coding project. But what about the other stuff? Each one of these items is a context switch, **including the email and screwing around**. And every time I want to switch contexts I go through the same three steps, no matter the type of task.

1. Quit everything. By everything I mean every visible window. When I activate Exposé/Mission Control I just see background.[^3]
2. Launch iTerm2.
3. `consular start contextname`

That's right. `consular start email`. `consular start dickaround`. Now my day turns into a series of *Quit, Run Script, Do Work*, *Quit, Run Script, Do Work*, ad infinitum. That may sound boring or robotic, but I see it as relief for the brain. I don't need to ask myself what programs and files to open. I just need to ask myself what I should be working on **right now**. Then focus on doing that thing.

This probably won't help your brain get into flow with each switch &mdash; only doing the work will get you there &mdash; but having simple repeatable steps certainly makes the transition smoother and quicker. I dare you to give it a try &mdash; start small, one or two projects at first &mdash; then try to go back. I can't.


[^1]: While they didn't coin the phrase, perhaps the most important work on the subject of context switches and software development environments in general is [Peopleware](http://www.amazon.com/Peopleware-Productive-Projects-Teams-Second/dp/0932633439) by Tom DeMarco and Timothy Lister. I was lucky enough to have a teacher who made this required reading for intro Software Engineering courses. Go read it, now.

[^2]: I don't want to get sidetracked on how to do email, but these usually get answered, deleted, or tagged and filed away in 15 minutes or less.

[^3]: I leave the programs that live in the taskbar or dock alone, such as Adium, Twitter, and Skype. I have one windowed program that I want to keep open across all contexts, and I keep it in a separate Space/Desktop for that reason: iTunes.