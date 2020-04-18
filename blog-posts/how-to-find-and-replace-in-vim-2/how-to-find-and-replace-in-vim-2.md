---
published: false
title: "Your title"
cover_image: "https://raw.githubusercontent.com/biancapower/my-dev.to/master/blog-posts/NAME-OF-YOUR-BLOG-POST/assets/cover.png"
description: "Description of the article"
tags: tag1, tag2, tag3
series:
canonical_url:
---

To do any of the previous but ask for confirmation before replacing, we add `c` on the end (c for confirm):

`:%s/name/firstName/gc`

This will ask us to confirm, in a prompt that looks something like this:

`replace with firstName (y/n/a/q/l/^E/^Y)?`

Our options are:

`y` for yes
`n` for no
`a` for replace all instances
`q` for quit
`l` for last (make the current change, then stop)
`^E` means ctrl+e, pressing this allows you to scroll through the text
`^Y` means ctrl+y, pressing this allows you to scroll through the text

This is an example of how to structure a blog post.

Here's an example of embedding an asciinema video:

{% asciinema 318544 %}

To use `embedme`, put the relevant code in a file inside the code folder, then add a code block specifying language, and comment with a filename in it, as below. Then run the command `embedme blog-posts/name-of-your-blog-post/name-of-your-blog-post.md` to embed the code.

```js
// code/demo-code.js
```

# Found a typo?

If you've found a typo, a sentence that could be improved or anything else that should be updated on this blog post, you can access it through a git repository and make a pull request. Instead of posting a comment, please go directly to https://github.com/biancapower/my-dev.to and open a new pull request with your changes.
