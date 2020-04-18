---
published: false
title: "How to Search and Replace in Vim (Part 1)"
cover_image: "https://raw.githubusercontent.com/biancapower/my-dev.to/master/blog-posts/how-to-find-and-replace-in-vim/assets/cover.png"
description: "The basics of how to search and replace in vim"
tags: vim, tutorial, beginners
series: vim-tips
canonical_url:
---

Being able to quickly search a file for a word or phrase and replace it with something else is a task many of us do regularly. This post outlines the fundamentals to get started using search and replace in vim.

Let's build up from the most simple search and replace, to more complex ones. If you prefer a more visual guide, jump to the asciinema cast at the end of this post.

To search **only the current line** for 'eggs' and replace **the first instance** of it (if any) with 'fried eggs', we do the following:

`:s/eggs/fried eggs/`

To search **only the current line** for 'eggs' and replace **every instance** of it (if any) with 'fried eggs', we add the `g` option for global:

`:s/eggs/fried eggs/g`

To search **a range of lines** (in this case lines 2-16) for 'name' and replace **every instance** in that range with 'firstName', we specify the range and also add the global option (take away the `g` to just replace the first instance in that range):

`:2,16 s/name/firstName/g`

To search **a range of lines** (in this case the entire document) for 'name' and replace **every instance** in that range with 'firstName', we do the same as above, except we specify the range with `%` to indicate the whole file as the range:

`:%s/name/firstName/g`

{% asciinema 318544 %}

```js
// people.js
```

# Found a typo?

If you've found a typo, a sentence that could be improved or anything else that should be updated on this blog post, you can access it through a git repository and make a pull request. Instead of posting a comment, please go directly to https://github.com/biancapower/my-dev.to and open a new pull request with your changes.
