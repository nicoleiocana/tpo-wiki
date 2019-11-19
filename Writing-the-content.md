When writing the content, there are some things to take into account:

**Markdown syntax**

We work with a text format called MarkDown. You can learn about it from the link https://dip.torproject.org/help/user/markdown 

**Short Sentences**

Please add linebreaks to the long sentences.

If you add only one linebreak, the paragraph will stay together, but the translation framework will generate two sentences.
Long sentences are hard to translate and unlikely to be reused.
Please dont change the line in the middle of a sentence, as that creates bad translation files.

**Links**

* Links are better done as \[linked words\](https://link), as it is easier to review them and simpler to read (instead of `<a href="https://link">`)
- External links:
  * **Always prefer https links when available**, to protect the privacy of our readers.
  * Make sure that the link is the shortest version possible, without suffixes like: `?ftag=COS-05-10aaa0b` or other random stuff. Take everything possible out of the link and leave it to its minimal (as long as functional) expression.

**HTML**

HTML is supported but not totally, and should be avoided. It is better to stick to MarkDown.

**TABLES**

You can do tables with | characters. Example:

```
| Project  | Methodology | Locations | Dates | Reporting |
| -------- | ----------- | --------- | ----- | --------- |
|  |  |  |  | test      |
```

Will create:

| Project  | Methodology | Locations | Dates | Reporting |
| -------- | ----------- | --------- | ----- | --------- |
|  |  |  |  | test      |


