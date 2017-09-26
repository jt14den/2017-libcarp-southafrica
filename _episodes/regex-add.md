# Plain text formats are your friend

	aka Get The Heck Out of Office!

- Agnostic Formats
   - `.txt`, `.csv`, `.tsv`

- The computer doesn't like pretty

- Formatting elements can't be easily found

- If it can't be found with Ctrl-F, it's not machine readable

---

* If you want computers to be able to process your stuff, try to get in the habit where possible of using platform-agnostic formats such as .txt for notes and .csv or .tsv for tabulated data (the latter pair are spreadsheet formats, separated by commas and tabs respectively).
* These plain text formats are preferable to the proprietary formats used as defaults by Microsoft Office because they can be opened by many software packages and have a strong chance of remaining viewable and editable in the future.
* Most standard office suites include the option to save files in .txt, .csv and .tsv formats, meaning you can continue to work with familiar software and still  make your work accessible.
* Compared to .doc or .xls, these formats have the additional benefit of containing only machine-readable elements.
* Using bold, italics, and colouring to signify headings or to make a visual connection between data elements is common practice, these **display-orientated annotations** are not (easily) machine-readable and hence can neither be queried and searched nor are appropriate for large quantities of information (the rule of thumb is if you can't find it by CTRL+F it isn't machine readable).
* Preferable are simple notation schemes such as using a double-asterisk or three hashes to represent a data feature: in my own notes, for example, three question marks indicate something I need to follow up on, chosen because `???` can easily be found with a CTRL+F search.
* `???` was also chosen by me because it doesn't clash with existing schemes.

---
## Use plain text formatting syntax

* Markdown - a lightweight markup language
- Markdown files are machine & human readable and  used in many different contexts (GitHub)

---

* Though it is likely that notation schemes will emerge from existing individual practice, existing schema are available to represent headers, breaks, et al.
* One such scheme is Markdown, a lightweight markup language. Markdown files are as .md, are machine readable, human readable, and used in many contexts - GitHub for example, renders text via Markdown.

---

# Useful links!

  - Markdown cheat sheet:  https://github.com/adam-p/markdown-here

  - Notepad++: http://notepad-plus-plus.org/

  - Pandoc:  http://pandoc.org/

---

* An excellent [Markdown cheat sheet is available on GitHub](https://github.com/adam-p/markdown-here) for those who wish to follow – or adapt – this existing schema.
* Notepad++ http://notepad-plus-plus.org/ is recommended for Windows users as a tool to write Markdown text in, though it is by no means essential for working with .md files.
* Mac or Unix users may find Komodo Edit, Text Wrangler, Kate, or Atom helpful.
* Combined with [pandoc](http://pandoc.org/), a markdown file can be exported to PDF, LaTeX or other formats, so it is a great way to create machine-readable, easily searchable documents that can be repurposed in many ways. It is a universal document converter.
* The slides and lessons we are using today were written in markdown and converted to HTML using pandoc.
