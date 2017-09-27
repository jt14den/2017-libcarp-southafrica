---
title: "Files and Conventions"
teaching: 30
exercises: 0
questions:
- "Key question"
objectives:
- "First objective."
keypoints:
- "First key point."
---

# Working with data is made easier by structuring your stuff in a consistent and predictable manner.

Why?


# URL structure
`ROOT/YYYY/MM/DD/words-of-title-separated-by-hyphens`
- <http://cradledincaricature.com/2015/07/24/code-control-and-making-the-argument-in-the-humanities/>

`ROOT/SUB_ROOT/YYYY/MMM/DD/words-describing-content-separated-by-hyphens`
- <https://www.theguardian.com/us-news/2016/oct/08/john-mccain-donald-trump-sex-boast-tape>

`ROOT/record-type/REF`
- <https://calisphere.org/collections/25503/>

`ROOT/browse.jsp?ref=REF`
- <http://www.oldbaileyonline.org/browse.jsp?ref=OA16780417>

* Without structured information, our lives would be much poorer.
* As library, data & archive people we know this.
* But I'll linger on this a little longer because for working with data it is especially important.

* Examining URLs is a good way of thinking about why structuring research data in a consistent and predictable manner might be useful in your work.
* Good URLs represent with clarity the content of the page they identify, either by containing semantic elements or by using a single data element found across a set or majority of pages.

1. A typical example of the former are the URLs used by news websites or blogging services. WordPress URLs follow the format:
`ROOT/YYYY/MM/DD/words-of-title-separated-by-hyphens`

2. A similar style is used by news agencies such as a *The Guardian* newspaper:
`ROOT/SUB_ROOT/YYYY/MMM/DD/words-describing-content-separated-by-hyphens`

3. In archival catalogues, URLs structured by a single data element are often used. The NLA's TROVE structures its online archive using the format:
`ROOT/record-type/REF`

4. And the Old Bailey Online uses the format:
ROOT/browse.jsp?ref=REF`

* What we learn from these examples is that a combination of semantic description and data elements make for consistent and predictable data structures that are readable both by humans and machines.
* Transferring this to your stuff makes it easier to browse, to search, and to query using both the standard tools provided by operating systems and by the more advanced tools Library Carpentry will cover.

---

# In practice, the structure of a good archive might look something like this:

TODO: good enough scicomp
- A base or root directory, perhaps called 'work'.

- A series of sub-directories such as 'events', 'data', ' projects' et cetera

- Within these directories are series of directories for each event, dataset or project. Introducing a naming convention here that includes a date element keeps the information organised without the need for subdirectories by, say, year or month
* All this should help you remember something you were working on when you come back to it later (call it real world preservation).

* The crucial part for us is the file naming convention you choose.
* The name of a file is important to ensuring it and its contents are easy to identify.
* 'Data.xslx' doesn't fulfil this purpose. A title that describes the data does.
* And adding dating convention to the file name, associating derived data with base data through file names, and using directory structures to aid comprehension strengthens those connection.
