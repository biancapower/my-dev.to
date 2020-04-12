---
published: false
title: "How to add ASCII Art around code comment blocks in vim"
cover_image: "https://raw.githubusercontent.com/biancapower/my-dev.to/master/blog-posts/quick-comment-boxes-in-vim/assets/cover.png"
description: "How to install and use `boxes` to wrap your comments in sweet ASCII art!"
tags: vim, bash, tutorial
series:
canonical_url:
---

While browsing Twitter this morning I came across this awesome gem

{% twitter 1249081168072282113 %}

and started experimenting! The full article is [here](https://www.cyberciti.biz/tips/unix-linux-draw-any-kind-of-boxes-around-text-editor.html), but here's my quick guide on how to get started.

# Installation

What we're going to use is a text filter program called [boxes](https://boxes.thomasjensen.com/about.html). Step 1 is installation.

Debian-based systems:

`$ sudo apt-get install boxes`

Mac (OSX):

`$ brew install boxes`

Here's what that process looks like on OSX:

{% asciinema 318770 %}

We can check that boxes has installed successfully by running `boxes -v`. If we get something like `boxes version 1.3`, that means boxes is installed (it's ok if your version number is different).

# Command line use

Now we have boxes. Great! What next? Before we go using it in vim, let's play around with it a bit on the command line. The asciinema video below captures the main commands and a demo (you can copy the text out of the video - try it!), or scroll down for a list of the commands to try.

{% asciinema 318773 %}

To use boxes on the command line, we pipe some text into it. For example:

`$ echo "Here's some text I want to put a box around!" | boxes`

To list all available box designs in the config file (my install came with 65!), we run:

`$ boxes -l | less`

The `less` isn't strictly necessary, but it allows us to more easily navigate through the lengthy output.

To use a particular design, append `-d [designname]` to the command. For example:

`$ echo "Here's some text I want to put a box around!" | boxes -d cat`

# Use in vim

Now comes the super fun part! We can use vim to add any of these boxes around some lines in a file. Think multi-line code comments we really want to stand out, or making documentation files more interesting!

Here's how (written steps below video):

{% asciinema 318775 %}

1. write some lines of plain text (we'll wrap comments around them in the next steps)
2. place the cursor in the first of the lines to be commented
3. specify the number of lines to comment, followed by `!!`, then the boxes command you want to use. E.g.: to comment 4 lines, and use the cat design, do the following:

`4!!boxes -d cat`

and you'll have something like...

```
            /\             /\
           |`\\_,--="=--,_//`|
           \ ."  :'. .':  ". /
          ==)  _ :  '  : _  (==
            |>/O\   _   /O\<|
            | \-"~` _ `~"-/ |
           >|`===. \_/ .===`|<
     .-"-.   \==='  |  '===/   .-"-.
.---{'. '`}---\,  .-'-.  ,/---{.'. '}---.
 )  `"---"`     `~-===-~`     `"---"`  (
(  I'm a cat                            )
 ) I'm a kitty cat                     (
(  And I dance dance dance              )
 ) And I dance dance dance             (
'---------------------------------------'

```

There are several configuration options, including alignment of the text within the box. It's also possible to create your own designs and add them to the config. For all this and more, check out the man page by running `man boxes`.

Happy commenting!

# Found a typo?

If you've found a typo, a sentence that could be improved or anything else that should be updated on this blog post, you can access it through a git repository and make a pull request. Instead of posting a comment, please go directly to https://github.com/biancapower/my-dev.to and open a new pull request with your changes.
