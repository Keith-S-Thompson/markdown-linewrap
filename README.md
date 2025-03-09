# markdown-linewrap

This illustrates a bug in some Markdown
viewers.  Examples are at the bottom
of this file.

The bug is that line endings within
a paragraph are rendered as line
breaks in the displayed output.  The
[Daring Fireball Markdown Syntax](https://daringfireball.net/projects/markdown/syntax#p)
and
[CommonMark Spec](https://spec.commonmark.org/0.31.2/#paragraphs)
both make it clear that line breaks
within a paragraph are to be ignored,
unless the line ends with two or
more spaces.

Viewers that exhibit the bug include:

- [Typedown](https://apps.microsoft.com/detail/9p8tcw4h2hb4?hl=en-US&gl=US) (Windows)
- [Obsidian](https://obsidian.md/) (Windows, Linux, Android)  
  Obsidian has an option in settings: Editor > Display > Strict line breaks.  
  This option is disabled by default.  Enabling it make it display
  paragraphs correctly, but only in "reading view".
- [SimpleNote](https://simplenote.com/) (Windows, Linux, web interface) (Android app is ok))  
  I emailed the author and got a reply:  
  > Hello, thank you for using this app, a new version of this app
  > completely refactored is in development. But I'm very sorry, as
  > this is a hobby project and I'm currently busy with work, the old
  > version didn't have time to fix the known issues, which will be
  > fixed along with the new version.

Viewers that handle this correctly include:

- [Visual Studio Code](https://code.visualstudio.com/)
  (Windows and Linux, preview mode)
- [Okular](https://okular.kde.org/) (Windows)
- [Markdown View](https://apps.microsoft.com/detail/9pj021lr0m3g?hl=en-US&gl=US)
  (Windows)
- [EZ Markdown](https://apps.ape-apps.com/ez-markdown/) (Windows)
- [UpNote](https://getupnote.com/) (Windows)
- [Simple Markdown](https://play.google.com/store/apps/details?id=com.wbrawner.simplemarkdown)
  (Android)
- [SimpleNote](https://simplenote.com/) (Android (Windows app is affected))
- [GitHub web interface](https://github.com/Keith-S-Thompson/markdown-linewrap)
- [Stack Overflow web interface](https://stackoverflow.com/)
- [Reddit web interface](https://reddit.com/)

Tools that convert Markdown to HTML
are unaffected as far as I can tell
(HTML viewed with Chrome and Lynx):

- [Pandoc](https://pandoc.org/)
- [Markdown](https://daringfireball.net/projects/markdown/)
- [Python-Markdown](https://github.com/Python-Markdown/markdown)

Most paragraphs in this file are wrapped
with `fmt -40`.  Such paragraphs should
still be wrapped to the width chosen
by the viewer software.

The bug is is particularly annoying when the input text is wrapped at, say,
80 columns and the output is 60 columns.  The bug can cause the paragraph
to be rendered as alternating 60- and 20-column lines.  (It's not quite that
simple, since output typically uses a variable-width font.)  This paragraph
is formatted with `fmt -80`.

A block of plain text, should be filled
and rendered as a single paragraph.
In the following examples, such a
paragraph should be shown as a single
line "Line one Line two Line three",
assuming a sufficiently wide display.
Some Markdown viewers incorrectly pass
the line breaks through to the output.

The same applies to a block of quoted
text.

Line breaks can be inserted by adding
two spaces to the end of a line.
A bulleted list also shows one item per
line.  (Long lines should be wrapped;
I don't test that here.)

---

## The following should be a single line

Line one
Line two
Line three

---

## The following should be a single line of quoted text

> Line one
> Line two
> Line three

---

## The following should be three lines (explicit line breaks)

Line one  
Line two  
Line three  

---

## The following should be three bulleted lines

- Line one
- Line two
- Line three

---
