---
layout: post
title: "My Sublime Text 2 javascript environment"
category: "dev tools"
tags: [ "sublime text 2", "node.js", "javascript", "plugin", "IDE", "jshint", "git" ]
---

While I love [Webmatrix](http://www.microsoft.com/web/webmatrix/) as a lightweight web editor in Windows, I had to look for alternatives for those times when I want to code on an OS X or Linux environment.  
One of the first steps I take when starting out with a new language, is to investigate and choose an IDE that works well for me. For Javascript here's a few things I was looking for:
* Being stable, fast and lightweight
* Reasonable autocomplete support
* Have a wide variety of plugins so that my experience can be improved over time
* Support for git integration and typical javascript tools as jshint would be welcomed

[Sublime Text](http://www.sublimetext.com/) provides a good match for these requirements and is, in fact, one of the most widely used editors in the [node.js](http://nodejs.org/) community.

![Sublime Text 2](/images/posts/sublime.png)

Although it provides a very solid base, it's functionality can be greatly improved through plugins. So, without further ado, here's the list of plugins I use.

Package Control
---------------

[Package control](http://wbond.net/sublime_packages/package_control) is a full-featured package manager that helps discovering, installing, updating and removing packages for Sublime Text 2. It features an automatic upgrader and supports GitHub, BitBucket and a full channel/repository system.

![Package Control](/images/posts/packageManager.png)

I love this plugin because it provides me an easy to use way to explore and manage (both install and uninstall) my Sublime Text plugins. Because of this, it's usually the first one that I install.

GitGutter
---------

[GitGutter](https://github.com/jisaacks/GitGutter) shows an icon in the gutter area indicating whether a line has been inserted, modified or deleted.

{:.center}
![GitGutter](/images/posts/GitGutter.png)
Notice the squares in the gutter area indicating which lines were changed

Most projects that I contribute to today use git. Even if they don't, many times I setup a local git repository to keep track of the changes I make to then locally, in my computer, without having to rely on a remote server. GitGutter provides an integrated way of seeing each change you make right from the text editor.

SublimeLinter
-------------

[SublimeLinter](https://github.com/SublimeLinter/SublimeLinter) provides the ability to "highlights lines of code the linter deems to contain (potential) errors. It also supports highlighting special annotations (for example: TODO) so that they can be quickly located.".

{:.center}
![SublimeLinter](/images/posts/SublimeLinter.png)
Notice the highlight when there's a missing trailing semicolon.

I like this plugin because it allows me to see, almost in real time, about any jsHint / jsLint errors that I may have produced in my Javascript code.

BracketHighlighter
------------------

[BracketHighlighter](https://github.com/facelessuser/BracketHighlighter) matches a variety of brackets.

{:.center}
![BracketHighlighter](/images/posts/BracketHighlighter.png)
Notice the bracket matching in the gutter area.

Node.js is great but being a functional language, made asynchronous through callbacks sometimes those brackets can become quite confusing to follow. I found that this plugin helps me with finding where each scope starts / ends.

Others
------

The list of sublime plugins is already big and it keeps on growing as the community builds more of them. Do you others that you think that are usefull as well when doing Javascript / node.js development ? Drop me a comment and I'll gladly add it to the list. :)