# 0 - The Problem

I'm trying to make an animation where user-settable text gets displayed on a balloon as the balloon floats across the screen, but…I'm stuck! 🥺

Specifically, I've got two issues, one of which seems to be a `d3plus` issue.

> [This video](https://github.com/clozach/d3plus-refresh-issue/blob/master/d3plus-refresh-issue.mov?raw=true) demonstrates both problems.

# Issue 1 - Text placement [Solved]

Initial rendering in Svelte works fine, but as soon as I change the text (by typing or pasting into the text field), the text renders in the balloon's "home" position, rather than rendering with the same offset as the balloon.

# Issue 2 - Text clipping
Some text wraps "better" than others, and, sadly, none of it gets hyphenation. But why does this display in its entirety…

> Why is it so difficult to center text in a shape like this while specifying curved outer bounds?

…and this…

> This is a wrapped sentence that I want on the bloody balloon! And without effin' ellipses!

…ends up as…

```
     This is a
      wrapped
  sentence that I
want on the bloody
   balloon! And
     without...
```
---

# Quick Start

To play around with the code directly:

```
git clone https://github.com/clozach/d3plus-refresh-issue.git
npm install
npm run dev
```
