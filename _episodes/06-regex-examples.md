---
title: "Regular Expression"
teaching: 45
exercises: 25
questions:
- "Key question"
objectives:
- "First objective."
keypoints:
- "First key point."
---

## Exercises

### Exercise

Pair up with the person next to you to work through the following problems.

> ## Using square brackets
> Can you guess what the regular expression `Fr[ea]nc[eh]` will match?
>
> > ## Solution
> > ~~~
> > French
> > France
> > Frence
> > Franch
> > ~~~
> > This will also find words where there are characters either side of the solutions above, such as `Francer`, `foobarFrench`, and `Franch911`.
> {: .solution}
{: .challenge}

> ## Using dollar signs
> Can you guess what the regular expression `Fr[ea]nc[eh]$` will match?
>
> > ## Solution
> > ~~~
> > French
> > France
> > Frence
> > Franch
> > ~~~
> > This will also find strings at the end of a line. It will find words where there were characters before these, for example `foobarFrench`.
> {: .solution}
{: .challenge}

> ## Introducing options
> What would match the strings `French` and `France` only that appear at the beginning of a line?
>
> > ## Solution
> > ~~~
> > ^France|^French
> > ~~~
> > This will also find words where there were characters after `French` such as `Frenchness`.
> {: .solution}
{: .challenge}

> ## Case insensitivity
> How do you match the whole words `colour` and `color` (case insensitive)?
>
> > ## Solutions
> > ~~~
> > \b[Cc]olou?r\b|\bCOLOU?R\b
> > /colou?r/i
> > ~~~
> > In real life, you *should* only come across the case insensitive variations `colour`, `color`, `Colour`, `Color`, `COLOUR`, and `COLOR` (rather than, say, `coLour`). So based on what we know, the logical regular expression is `\b[Cc]olou?r\b|\bCOLOU?R\b`. An alternative more elegant option we've not discussed is to take advantage of the `/` delimiters and add an 'ignore case' flag: so `/colou?r/i` will match all case insensitive variants of `colour` and `color`.
> {: .solution}
{: .challenge}

> ## Word boundaries
> How would you find the whole word `headrest` and or `head rest` but not `head  rest` (that is, with two spaces between `head` and `rest`?
>
> > ## Solution
> > ~~~
> > \bhead ?rest\b
> > ~~~
> > Note that although `\bhead\s?rest\b` does work, it will also match zero or one tabs or newline characters between `head` and `rest`. So again, although in most real world cases it will be fine, it isn't strictly correct.
> {: .solution}
{: .challenge}

> ## Matching non-linguistic patterns
> How would you find a string that ends with 4 letters preceded by at least one zero?
>
> > ## Solution
> > ~~~
> > 0+[a-z]{4}\b
> > ~~~
> {: .solution}
{: .challenge}

> ## Matching digits
> How do you match any 4-digit string anywhere?
>
> > ## Solution
> > ~~~
> > \d{4}
> > ~~~
> > Note: this will also match 4 digit strings within longer strings of numbers and letters.
> {: .solution}
{: .challenge}

> ## Matching dates
> How would you match the date format `dd-MM-yyyy`?
>
> > ## Solution
> > ~~~
> > \b\d{2}-\d{2}-\d{4}\b
> > ~~~
> > Depending on your data, you may chose to remove the word bounding.
> {: .solution}
{: .challenge}

> ## Matching multiple date formats
> How would you match the date format `dd-MM-yyyy` or `dd-MM-yy` at the end of a line only?
>
> > ## Solution
> > ~~~
> > \d{2}-\d{2}-\d{2,4}$
> > ~~~
> > Note this will also find strings such as `31-01-198` at the end of a line, so you may wish to check your data and revise the expression to exclude false positives. Depending on your data, you may chose to add word bounding at the start of the expression.
> {: .solution}
{: .challenge}

> ## Matching publication formats
> How would you match publication formats such as `British Library : London, 2015` and `Manchester University Press: Manchester, 1999`?
>
> > ## Solution
> > ~~~
> > `.* ?: .*, \d{4}`
> > ~~~
> >{: .source}
> > Without word boundaries you will find that this matches any text you put before `British` or `Manchester`. Nevertheless, the regular expression does a good job on the first look up and may be need to be refined on a second, depending on your data.
> {: .solution}
{: .challenge}

## Some applications

1. Google spreadsheet - search and replace
2. Google spreadsheet - regexmatch function
3. Text editors
4. Shell and Openrefine
5. Programming languages

> ## Regex for Google Sheets
> Using the [2014 Public Library Survey](https://data.imls.gov/Public-Libraries-Survey/Main-Libraries-Branches-and-Bookmobiles-FY-2014-Pu/ucdn-7aur/data), extract as a CSV and upload to Google Sheets. In the location column notice that the values contain the latitude and longitude in parenthesis. Construct a regular expression to match and extract the latitude and longitude into a new column named 'latlong'. Look up the function `REGEXEXTRACT` in Google Sheets. 
