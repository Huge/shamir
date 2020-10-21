## Welcome to GitHub Pages

Current path of implementation through Skulpt hangs on [this issue](https://github.com/Huge/shamir/edit/gh-pages/index.md):

I've been fighting a relevant issue with huge numbers, where the upper bound is `2**127 - 1`, which I'm able to `print` without a problem.
I asume my code fails in https://github.com/skulpt/skulpt/blob/b763d3e24860a8e3d303878e0035d8bad9f55578/src/lib/random.js#L268 .
I have only subtle awareness of Javascript, but I'd like to help in making this improvement/PR..is it the right way to just wrap all the calculations there into `BigInt()` or do we need to assemble the larger numbers from the 32b integers?

>> native BigInt is [not recommended yet](https://github.com/skulpt/skulpt/issues/1211#issuecomment-713691884) in the codebase as it's not backwards compatible for older browsers. (I think it was only added to safari in the last couple of months)

+ Examples in https://github.com/skulpt/skulpt/blob/master/src/lib/math.js#L226 where large numbers are allowed into factorial or gcd and are handled by the ~big_integer interface.

>> hoping that we can use the JSBI library at some point which has a nice functional approach to handling BigInt, here's an example of math.js function with a version of the JSBI library
https://github.com/s-cork/skulpt/blob/prototypical_getsets_mappingproxy/src/lib/math.js#L226

### Goals yet:

+ Integrate RNG from https://www.bitaddress.org or https://bitcoinpaperwallet.com/bitcoinpaperwallet/generate-wallet.html 
  - Generate seeds and shards( =sharing pieces) of them
+ Allow switching the hex, base64, BINARY, from which I can assemble backups
+ Naive sharing for 2/2, 2/3 and X/4 maybe

---- 

### Reference on MD syntax..:

Markdown is easy. It includes conventions for:

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).


GitHub Pages uses [Jekyll](https://jekyllrb.com/) to assemble these pages. gh/contact could support..
