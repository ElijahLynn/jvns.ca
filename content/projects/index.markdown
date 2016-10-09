---
title: "Projects"
staticpage: true
categories: []
---

A few projects I worked on in 2013 and before. Mostly  for fun, mostly when at the [Recurse Center](https://recurse.com).

* [Operating system in Rust](#os-rust) (2013)
* [Visualizing Git workflows](#visualizing-git) (2013)
* [Python TCP stack](#python-tcp-stack) (2013)
* [Gunzip in Julia](#gunzip-in-julia) (2013)
* [Fun with kernel modules](#kernel-module-fun) (2013)
* [Visualizing Unix command usage](#unix-command-survey) (2013)
* [Bike availability map](#bixi-map) (2011)
* [Master's thesis](#masters-thesis) (2011)

<h2>
    <a name="os-rust" class="anchor"> </a>
    <a href="http://github.com/jvns/rustboot"> Operating system in Rust </a> (2013)
</h2>

A toy operating system in [Rust](http://rust-lang.com) for x86. It
only has a basic keyboard driver.

I've also written a pretty popular series of blog posts about this
process, like
[programming without malloc](http://jvns.ca/blog/2013/12/03/day-36-programming-without-malloc/)
and
[struggling with getting keyboard interrupts to work](http://jvns.ca/blog/2013/12/04/day-37-how-a-keyboard-works/).
You can see
[all my OS-hacking related posts](http://jvns.ca/blog/categories/kernel/).

It was really fun to learn Rust -- the community is really friendly, and
I've been able to contribute back to the documentation.

[[Source]](http://github.com/jvns/rustboot)

<h2>
    <a name="visualizing-git" class="anchor"> </a>
    <a href="http://visualize-your-git.herokuapp.com"> Visualizing Git workflows</a> (2013)
</h2>

[<img src="/images/selenamarie.png">](http://visualize-your-git.herokuapp.com/display/223/sparse)

When [Philip Guo](http://www.pgbovine.net/) was a resident at Hacker
School, we had some interesting discussions about how to automatically
learn people's programming workflows and generate information for
novices or tool-creators to use.

After that, I built a tool to visualize your Git workflow. As of Dec.
2013 about 2300 people have used it.

[Source](https://github.com/jvns/git-workflow),
[Try it out](http://visualize-your-git.herokuapp.com),
[Blog post](http://jvns.ca/blog/2013/11/13/day-27-magic-testing-functions/)


<h2>
    <a name="python-tcp-stack" class="anchor"> </a>
    <a href="https://github.com/jvns/teeceepee">Python TCP stack</a> (2013)
</h2>

This was an exercise in learning how TCP works. It works exactly
well enough to implement a slow and finicky version of `curl`, which
is pretty exciting.

It is also a huge pain because it turns out writing a TCP stack when
you already *have* a TCP stack in your kernel is hard. I needed to
invent an IP address and send gratuitous ARPs to the router so that
all my connections didn't get reset.

One thing I found while writing this is that it's important for a TCP
stack to be *fast* -- this implementation lags pretty badly because a
pure Python implementation is just too slow to handle incoming packets
as quickly as they come in. It sends an ACK for each packet and a
backlog develops pretty quickly.

[Source](https://github.com/jvns/teeceepee), Blog posts [[1]](http://jvns.ca/blog/2013/11/06/day-23-started-writing-a-socket-library/)
[[2]](http://jvns.ca/blog/2013/11/07/day-24-unit-testing-this-tcp-library/)
[[3]](http://jvns.ca/blog/2013/11/12/day-25-ack-all-the-things/)
[[4]](http://jvns.ca/blog/2013/11/12/day-26-trying-to-describe-the-tcp-state-machine/)

<h2>
    <a name="gunzip-in-julia" class="anchor"> </a>
    <a href="http://github.com/jvns/gzip.jl">Gunzip in Julia</a> (2013)
</h2>

<iframe width="100%" height="300" src="http://www.youtube.com/embed/SWBkneyTyPU" frameborder="0" allowfullscreen></iframe>

I wanted to understand how `gzip` works, so I wrote `gunzip` from
scratch in Julia.

It then turned out that unzipping the Raven and printing out the
intermediate results made a really compelling visualization of how
LZ77 compression works. The internet liked it a lot.

[Source](http://github.com/jvns/gzip.jl),
[Video](http://www.youtube.com/SWBkneyTyPU),
[Blog post](http://jvns.ca/blog/2013/10/24/day-16-gzip-plus-poetry-equals-awesome/), 
[HN discussion](https://news.ycombinator.com/item?id=6609586)

<h2>
    <a name="kernel-module-fun" class="anchor"> </a>
    <a href="https://github.com/jvns/kernel-module-fun">Fun with kernel modules</a> (2013)
</h2>

[<img src="/images/rootkit.png">](https://github.com/jvns/kernel-module-fun)

When I arrived at Hacker School I had *no idea* about what the Linux
kernel did or how to make it do anything. So my first action was to
find out. I wrote a couple of blog posts about
[what the Linux kernel does](http://jvns.ca/blog/2013/10/02/day-3-what-does-the-linux-kernel-even-do/)
and
[processes vs threads](http://jvns.ca/blog/2013/10/04/day-4-processes-vs-threads/)
before deciding to learn by writing a kernel module.

It turns out that writing silly kernel modules is not too hard! I
wrote a module that writes to the log every time a packet arrives and
a small rootkit (via a lot of copying and and pasting).

This is more of a "fun exploration" than a "serious project".

[Source](https://github.com/jvns/kernel-module-fun)


<h2>
    <a name="unix-command-survey" class="anchor"> </a>
    <a href="http://jvns.ca/projects/unix-command-survey/graph.html"> Visualizing Unix command usage</a> (2013)
</h2>

[<img src="/images/command-graph-small.png">](http://jvns.ca/projects/unix-command-survey/graph.html)

A few months ago I got curious about which unix command line utilities
were the most popular, so I ran a survey on Hacker News. I ended up
getting 1,500 responses or so.

Once I had that, I wanted to know how commands are related to each
other: do people who use `gcc` use `python`? What about `scala` and
`clojure`?

Useful for fun times and discovering new tools to use. It's a bit
computationally intensive, so best viewed in Chrome. 

[Source](http://github.com/jvns/unix-command-survey)

<h2>
    <a name="bixi-map" class="anchor"> </a>
    <a href="http://jvns.ca/bixi/map">Bike availability map</a> (2011)
</h2>

[<img src="/images/biximap.png">](http://jvns.ca/bixi/map)

This was my first Javascript project. I wrote it a few years ago when
I got frustrated with [Bixi](http://montreal.bixi.com)'s map. It's a
realtime app and they take the bikes out in the winter, so it's only
useful from April to mid-November.

[Source](http://github.com/jvns/biximap).

<h2>
    <a name="masters-thesis" class="anchor"> </a>
    Master's thesis (2011)
</h2>

[<img src="/images/thesis-picture.png">](http://github.com/jvns/masters-thesis)

This is certainly the project I've spent the *longest* on. I wrote my
master's thesis on the algebra of topological quantum computing.

The idea is that in order to understand the algebra behind topological
quantum computing, one needs to understand

* quantum groups, in particular quantum groups at roots of unity
* how to get from the category of representations of those quantum groups to modular tensor categories, 
* How topological quantum computing happens in these modular tensor categories

My advisor [Prakash Panangaden](http://www.cs.mcgill.ca/~prakash/) and
I found it hard to find a good reference which tied all these things
together, so I wrote my thesis about it.

[PDF](https://github.com/jvns/masters-thesis/raw/master/thesis.pdf)
