# markdown-linewrap

This illustrates a bug in some Markdown
viewers.  Affected viewers include:

- [Typedown](https://apps.microsoft.com/detail/9p8tcw4h2hb4?hl=en-US&gl=US) (Windows)
- [Simple Markdown](https://play.google.com/store/apps/details?id=com.wbrawner.simplemarkdown) (Android)
- [Obsidian](https://obsidian.md/) (Windows, Linux, Android)

Viewers that handle this correctly include:

- [Visual Studio Code](https://code.visualstudio.com/) (Windows and Linux, preview mode)
- [Okular](https://okular.kde.org/) (Windows)
- [Markdown View](https://apps.microsoft.com/detail/9pj021lr0m3g?hl=en-US&gl=US) (Windows)
- [EZ Markdown](https://apps.ape-apps.com/ez-markdown/) (Windows)
- [GitHub web interface](https://github.com/Keith-S-Thompson/markdown-linewrap)
- [Stack Overflow web interface](https://stackoverflow.com/)

All paragraphs in this file are wrapped
with `fmt -40`.  Such paragraphs should
still be wrapped to the width chosen
by the viewer software.

The following consists of 3 lines
of text with no trailing spaces.
When rendered, the entire block should
be filled and rendered as a single
paragraph.  With a sufficiently wide
display, it should be shown as a single
line "Line one Line two Line three".
Some Markdown viewers incorrectly pass
the line breaks through to the output.

*The following should be a single line:*  

Line one
Line two
Line three

---

The following is the same, but with
two trailing spaces on each line.
The trailing spaces should create a
line break in the output.  Most or all
Markdown viewers handle this correctly.

### The following should be a three lines:

Line one  
Line two  
Line three  

---

The following is the same rendered as
an unordered list, without the trailing
spaces.  Most or all Markdown viewers
handle this correctly.

### The following should be three bulleted lines:

- Line one
- Line two
- Line three

---

The following is the same, but as a
block of quoted text.

### The following should be a single line of quoted text:

> Line one
> Line two
> Line three

---
