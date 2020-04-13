---
published: false
title: "Writing a Bash function to automate Exercism.io exercise setup"
cover_image: "https://raw.githubusercontent.com/biancapower/my-dev.to/master/blog-posts/a-bash-function-for-exercism.io/assets/cover.png"
description: "An example of writing a bash function to automate the repetitive stuff"
tags: bash, javascript, beginners
series:
canonical_url:
---

Lately I've been working my way through the JavaScript track on [Exercism.io](https://exercism.io/). It's an excellent website and I highly recommend checking it out if you either want to work on your skills in a particular language (there are 50 to choose from), or are comfortable in a particular programming language and interested in mentoring others.

[![Exercism.io](https://raw.githubusercontent.com/biancapower/my-dev.to/master/blog-posts/a-bash-function-for-exercism.io/assets/exercism-site.png)](https://exercism.io/)

Something I found a little repetitive was the process of setting things up to work on an exercise. The process went something like this:

1. open the exercise in the browser
2. copy the download command (e.g. `exercism download --exercise=collatz-conjecture --track=javascript`) from the browser window, and paste it into terminal
3. cd into the correct folder (e.g. `cd Exercism/javascript/collatz-conjecture`)
4. run `npm install` so that the tests are ready to be run

Pretty straightforward, but also a predictable and repeatable pattern... perfect for a bash function! Here's the command I want to be able to run in order to make all of the above execute:

`$ devil collatz-conjecture`

To make this possible, here's the bash function that I added to my `.zshrc` (I use zsh so added it to my `.zshrc`, but if you're using bash, add it to your `.bashrc`):

```
1. devil() {
2.     exercism download --exercise=$1 --track=javascript && cd ~/Exercism/javascript/$1 && npm install;
3. }
```

Let's break it down. Line 1 is the name I've given to the function, followed by parentheses and an open curly brace (standard function syntax). I named my function 'devil' because it's easy to type, and something I associate easily with 'exercism' (making it easy to remember).

Line 2 is where the awesomeness happens. These are all the steps I was previously doing 'manually', run for me by executing only one command. The `&&` between each command means that each command must succeed in order for the next one to execute. This makes sense in this context, because each command relies on the previous commands's success. For example, we can't cd into the folder in step 2 if it wasn't created in step 1. But what about the `$1`? That's the bash way of saying "grab the first argument passed in when the function is run, and use it here". So in our example above, `$1` would hold the value `collatz-conjecture`.

Line 3 is the closing brace to end the function.

So now all I need to know is the name of the next exercise I want to attempt on [Exercism.io](https://exercism.io/), and I can simply run `devil exercise-name` to have my bash function do all the setup work for me!

Here's what it looks like in action:

{% asciinema 319489 %}

# Found a typo?

If you've found a typo, a sentence that could be improved or anything else that should be updated on this blog post, you can access it through a git repository and make a pull request. Instead of posting a comment, please go directly to https://github.com/biancapower/my-dev.to and open a new pull request with your changes.
