---
title: "Regular Expression 2"
teaching: 15
exercises: 40
questions:
- "Key question"
objectives:
- "First objective."
keypoints:
- "First key point."
---

## Regular Expressions

* one reason we place emphasis on consistent, well strutured naming conventions with files is because these patterns become actionable
* we can use the computer to match the patterns we've created and do things with the files that meet that pattern
  - e.g. you have a file neame with years in it `2014`, we can then match those files
  - or if you have the term `journal` in the file somewhere, we can use the computer to select just those  files and operate on them
* additionally, when we use plain text formats (non-binary or complex) we can select files or lines in files based on characteristics of the text inside the file

**regular expressions** are the way will do this, shorted to **regex**

* a regex is a sequence of characters thatdefine a search pattern - used in pattern matching with strings - like 'find and place' operations
* Who knows what a string is?
* string is a continguous sequence of characters, for exmple a word, a sentence, a set of numbers, such as a phone number, a doi, a url
* **Regular expression** when written in many tools are surrounded by some character tell the tool "this is a regex" - many use `/your-regex/`

Regexes will let you:

* match on character type (e.g. 'upper case characters', 'digits', 'spaces')
* match patterns that repeat any number of times
* define groups of matched characters so we can do something with the sub-string

**most computational** software implement regexes b/c many programming tasks require complex matching

* A simple use of a regular Expression would be to locate the same word spelled two different ways -- for example `organi[sz]e` matches both **organize** and **organise**.
* It would also match **reorganize**, **reorganise**, **organises**, **organizes**, `organised`, `organized`, et cetera.
* WHY do you think???
* B/c we haven't specified the beginning or end of where our should matchin on the string
* We use regex syntax to help us specify this.

**Let's cover some of the special syntax**

* `[ABC]` matches A or B or C
* `[A-Z]` matches any upper case letter
- `[A-Za-z]` matches any upper or lower case letter (note: this is case-sensitive)
- `[A-Za-z0-9]` matches any upper or lower case letter or any digit (note: this is case-sensitive)

Then there are:

- `.` matches any character
- `\d` matches any single digit
- `\w` matches any part of word character (equivalent to `[A-Za-z0-9]`)
- `\s` matches any space, tab, or newline
- `\` NB: this is also used to escape the following character when that character is a special character. So, for example, a regular expression that found `.com` would be `\.com` because `.` is a special character that matches any character.
- `^` asserts the position at the start of the line. So what you put after the caret will only match if they are the first characters of a line. The caret is also known as a circumflex.
- `$` asserts the position at the end of the line. So what you put before it will only match if they are the last characters of a line.
- `\b` adds a word boundary. Putting this either side of a word stops the regular expression matching longer variants of words. So:
	- the regular expression `foobar` will match `foobar` and find `666foobar`, `foobar777`, `8thfoobar8th` et cetera
	- the regular expression `\bfoobar` will match `foobar` and find `foobar777`
	- the regular expression `foobar\b` will match `foobar` and find `666foobar`
	- the regular expression `\bfoobar\b` will find `foobar`

  So, what is `^[Oo]rgani.e\b` going to match?

  > ## Using special characters in regular expression matches
  > Can you guess what the regular expression `^[Oo]rgani.e\b` will match?
  >
  > > ## Solution
  > > ~~~
  > > organise
  > > organize
  > > Organise
  > > Organize
  > > organife
  > > Organike
  > > ~~~
  > > Or, any other string that starts a line, begins with a letter `o` in lower or capital case, proceeds with `rgani`, has any character in the 7th position, and ends with the letter `e`.
  > {: .solution}
  {: .challenge}

  Other useful special characters are:

  - `*` matches the preceding element zero or more times. For example, ab*c matches "ac", "abc", "abbbc", etc.
  - `+` matches the preceding element one or more times. For example, ab+c matches "abc", "abbbc" but not "ac".
  - `?` matches when the preceding character appears zero or one time.
  - `{VALUE}` matches the preceding character the number of times defined by VALUE; ranges, say, 1-6, can be specified with the syntax `{VALUE,VALUE}`, e.g. `\d{1,9}` will match any number between one and nine digits in length.
  - `|` means or.
  - `/i` renders an expression case-insensitive (equivalent to `[A-Za-z]`)

  So, what are these going to match?

  > ## ^[Oo]rgani.e\w*
  > Can you guess what the regular expression `^[Oo]rgani.e\w*` will match?
  >
  > > ## Solution
  > > ~~~
  > > organise
  > > Organize
  > > organifer
  > > Organi2ed111
  > > ~~~
  > > Or, any other string that starts a line, begins with a letter `o` in lower or capital case, proceeds with `rgani`, has any character in the 7th position, follows with letter `e` and zero or more characters from the range `[A-Za-z0-9]`.
  > {: .solution}
  {: .challenge}

  > ## [Oo]rgani.e\w+$
  > Can you guess what the regular expression `[Oo]rgani.e\w+$` will match?
  >
  > > ## Solution
  > > ~~~
  > > organiser
  > > Organized
  > > organifer
  > > Organi2ed111
  > > ~~~
  > > Or, any other string that ends a line, begins with a letter `o` in lower or capital case, proceeds with `rgani`, has any character in the 7th position, follows with letter `e` and **at least one or more** characters from the range `[A-Za-z0-9]`.
  > {: .solution}
  {: .challenge}

  > ## ^[Oo]rgani.e\w?\b
  > Can you guess what the regular expression `^[Oo]rgani.e\w?\b` will match?
  >
  > > ## Solution
  > > ~~~
  > > organise
  > > Organized
  > > organifer
  > > Organi2ek
  > > ~~~
  > > Or, any other string that starts a line, begins with a letter `o` in lower or capital case, proceeds with `rgani`, has any character in the 7th position, follows with letter `e`, and ends with **zero or one** characters from the range `[A-Za-z0-9]`.
  > {: .solution}
  {: .challenge}

  > ## ^[Oo]rgani.e\w?$
  > Can you guess what the regular expression `^[Oo]rgani.e\w?$` will match?
  >
  > > ## Solution
  > > ~~~
  > > organise
  > > Organized
  > > organifer
  > > Organi2ek
  > > ~~~
  > > Or, any other string that starts and ends a line, begins with a letter `o` in lower or capital case, proceeds with `rgani`, has any character in the 7th position, follows with letter `e` and **zero or one characters** from the range `[A-Za-z0-9]`.
  > {: .solution}
  {: .challenge}

  > ## \b[Oo]rgani.e\w{2}\b
  > Can you guess what the regular expression `\b[Oo]rgani.e\w{2}\b` will match?
  >
  > > ## Solution
  > > ~~~
  > > organisers
  > > Organizers
  > > organifers
  > > Organi2ek1
  > > ~~~
  > > Or, any other string that begins with a letter `o` in lower or capital case after a word boundary, proceeds with `rgani`, has any character in the 7th position, follows with letter `e`, and ends with **two** characters from the range `[A-Za-z0-9]`.
  > {: .solution}
  {: .challenge}

  > ## \b[Oo]rgani.e\b|\b[Oo]rgani.e\w{1}\b
  > Can you guess what the regular expression `\b[Oo]rgani.e\b|\b[Oo]rgani.e\w{1}\b` will match?
  >
  > > ## Solution
  > > ~~~
  > > organise
  > > Organi1e
  > > Organizer
  > > organifed
  > > ~~~
  > > Or, any other string that begins with a letter `o` in lower or capital case after a word boundary, proceeds with `rgani`, has any character in the 7th position, and end with letter `e`, or any other string that begins with a letter `o` in lower or capital case after a word boundary, proceeds with `rgani`, has any character in the 7th position, follows with letter `e`, and ends with a single character from the range `[A-Za-z0-9]`.
  > {: .solution}
  {: .challenge}

  ### How could this be helpful?  Can you think of some ways? Take 5 minuges and pair up.
