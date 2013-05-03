---
layout: post
title: "Scripting with the azure cross platform CLI"
category: posts
tags: [ "CLI", "Windows Azure", "scripting", "bash" ]
---

Windows Azure provides you a couple of ways to manage the services you choose to run in it. The portal is the natural choice for many tasks, however, more advanced users (read, IT pros) typically are more confortable in a command line environment.
For those users Microsoft developed two different approaches: one specifically for Windows that provides the best experience possible there - through [Powershell](http://msdn.microsoft.com/en-us/library/windowsazure/jj156055.aspx) - and another one for the remaining operating systems (OS X, Linux, etc) where the power of node.js is put to good use through a [Cross Platform CLI](http://www.windowsazure.com/en-us/manage/linux/how-to-guides/command-line-tools/).

![Cross Platform CLI](/images/posts/cli.png)

One of the natural things to do with a CLI, is to script. For the cross platform CLI, as it is written in node.js, we decided that probably some folks out there besides the naturall way of scripting based on traditional grepping of columns, might also want to script straight from node.js. Glenn Block, actually built a module on top of our CLI to make this experience even easier - [azure scripty](https://npmjs.org/package/azure-cli). He also wrote a [blog post](http://codebetter.com/glennblock/2012/12/25/simple-bash-scripting-for-azure-cli/) on how to script without that module. 

Although both of them are great resources and should make your scripting needs really trivial, in this blog post, I'd like to present a different approach, using the format native to Javascript - JSON - straight from bash. All the cmdlets in our CLI can, as an option, output their results as JSON.

An example can see below for sites, for instance:

![Cross Platform CLI](/images/posts/json.png)

Using this functionality, together with a little tool called [jsawk](https://github.com/micha/jsawk) one can easily script much easier. jsawk can be easily installed from brew in an OS X environment with:

``` bash
$ brew install jsawk
```

After that, one can, for instance, use:

``` bash
$ azure site list --json | jsawk -n 'out(this.Name)' | xargs -L 1 azure site delete -q
```

To delete all sites in an account.

I hope this blog post makes your future Windows Azure scripting needs even easier.