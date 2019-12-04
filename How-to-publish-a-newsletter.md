Each newsletter has a html and a text version. To add a new newsletter follow these steps.

1. Create a new folder under `content/archive/`. The folder name represent the slug for the newsletter. 
Ex: `content/archive/advocating-for-anonymity-bandwidth-scanners-tor-metrics-events` results in the following url: [https://newsletter.torproject.org/archive/2019-04-30-advocating-for-anonymity-bandwidth-scanners-tor-metrics-events/text/](https://newsletter.torproject.org/archive/2019-04-30-advocating-for-anonymity-bandwidth-scanners-tor-metrics-events/text/)

2. Create a `contents.lr` file inside the folder with the following template:

```
_model: post
---
_template: newsletter.html
---
author: <AUTHOR EMAIL>
---
pub_date: <YYYY-MM-DD>
---
title: <TITLE>
---
html_body:

<HTML_CONTENT>

```

3. Create a `text` folder and add a `contents.lr` file with the following template:

```
_model: post
---
_template: post.html
---
author: <AUTHOR EMAIL>
---
pub_date: <YYYY-MM-DD>
---
title: <TITLE>
---
body:

<MARKDOWN_CONTENT>

```