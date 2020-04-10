---
published: false
title: 'My awesome title'
cover_image: 'https://raw.githubusercontent.com/biancapower/my-dev.to/master/blog-posts/my-first-draft/assets/rubberduck.png'
description: 'This is a demo article'
tags: tag1, tag2, tag3
series:
canonical_url:
---

# This is an example of how to structure a blog post.

The thing above delimited by `---` is called a "front matter" and it allows us to keep control over our article in a very easy way. Just edit it with your own data and CI will handle the rest to publish it to dev.to!

## Level 2

[![asciicast](https://asciinema.org/a/318544.svg)](https://asciinema.org/a/318544)

You can also take advantage of [embedme](https://github.com/zakhenry/embedme) to extract your code from the markdown file and make sure that what you're displaying in the markdown is always up to date too e.g.

```ts
// code/demo-code.ts

interface A {
  hello: string;
}
```

# Found a typo?

If you've found a typo, a sentence that could be improved or anything else that should be updated on this blog post, you can access it through a git repository and make a pull request. Instead of posting a comment, please go directly to https://github.com/biancapower/my-dev.to and open a new pull request with your changes.
