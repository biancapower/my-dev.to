---
published: false
title: "How to change your default text editor for git (and avoid vim)"
cover_image: "https://raw.githubusercontent.com/biancapower/my-dev.to/master/blog-posts/how-to-change-your-default-text-editor/assets/cover.png"
description: "How to change your default text editor for git (and avoid vim)"
tags: git, tutorial, beginners
series:
canonical_url:
---

We've all done it. `git add .` then... `git commit`. Big mistake. We forgot to add a `-m` with a message! Now we're in the dreaded vim text editor...

{% asciinema 318599 %}

_But what if there was another way?_ By changing the git config, we can specify **a different editor for git to launch us into** if it needs to do so. Below is how to do this on a unix (OSX or Linux) system.

First, **check what your current system default is** (you can pause the video below and copy the text command out of it - try it now!):

{% asciinema 318597 %}

In the example above, as on many systems, the default editor is vim. Personally, I love vim, but if you're not familiar with it it can make things a bit difficult and really mess up your flow. First let's look at **how to change git's default text editor to nano**, and what nano looks like in practice:

{% asciinema 318600 %}

As you can see, nano is much more straight forward than vim (not least because it gives you the commands you need at the bottom of the screen!), but it still exists completely in the terminal (which has pros and cons).

What if you want to change the editor used by git to something external to the terminal, like **VS Code**? Here's how:

{% youtube R9u2e66IKzc %}

Note that changing the editor to `code` didn't work quite as we wanted it to - because we're leaving the terminal environment in order to go and edit the file in VS Code, we need to tell git to wait for us. We do that by specifying `code --wait`, which basically says "Hey git, I'm gonna go over to VS Code to edit that file now, just hang about, and once I've closed that file you can read it and finish processing the command".

The process for changing the default to other text editor is basically the same, it's just a matter of finding the correct key word(s) for launching the editor.

What do you use as your default text editor? Comment below!

# Found a typo?

If you've found a typo, a sentence that could be improved or anything else that should be updated on this blog post, you can access it through a git repository and make a pull request. Instead of posting a comment, please go directly to https://github.com/biancapower/my-dev.to and open a new pull request with your changes.
