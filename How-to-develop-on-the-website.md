To follow this documentation you need to set up a [local copy of the website](Compiling-a-local-version-of-the-website)
Content for the website is organized in the folder [content](https://dip.torproject.org/web/tpo/tree/master/content). The file responsible for content is always callend `contents.lr`.

Also the `contents.lr` implements the filed specified in the model. Model are defined in the folder [models](https://dip.torproject.org/web/tpo/tree/master/models) and are used to specified fields used within the page.

Some of these `contents.lr` files do not have a body because the styling of the page required us to add some content to the template itself.

All the templates are located in the folder [templates}(https://dip.torproject.org/web/tpo/tree/master/templates).

All the templates are built starting from [layout.html](https://dip.torproject.org/web/tpo/tree/master/templates/layout.html). 

Within the templates folder there is a folder called [macros](https://dip.torproject.org/web/tpo/tree/master/templates/macros). Macros are block of code that can be called from within a template:
```
<div class="row">
    <h2 class="text-primary">Windows Expert Bundle</h2>
    {% set t = bag('versions', 'torbrowser-stable') %}
    <table class="table">
      <tbody>
        <tr>
          <td>Windows 10, 8, 7, Vista, XP, 2000, 2003 Server, ME, and Windows 98SE</td>
          <td>Contains just Tor and nothing else.</td>
          <td class="text-right">
            {% from "macros/downloads.html" import render_windows_expert %}
            {{ render_windows_expert(t.version, t.win32) }}
          </td>
        </tr>
      </tbody>
    </table>
  </div>
```

Finally recursive type of data are defined with databags.
These live in the folder [databags](https://dip.torproject.org/web/tpo/tree/master/databags).

This table summarises how each databag file is used

| file | function |
| ------ | ------ |
| about+en.ini | About page nav menu |
| menu+en.ini | Navbar top menu |
| alternatives.ini | Locales and styling information for each language |
| download-alternatives-alpha.ini | Locales for the alpha version of Tor Browser |
| download-alternatives.ini | Locales for Tor Browser |
| versions.ini | Latest versions for all the downloads |
| platforms.ini | Supported platforms for the desktop versions |
| tags.ini | Content tags and styling information |


## How to add a new sponsor

1. Create a new directory for the sponsor under `content/about/sponsors/` e.g `content/about/sponsors/<SPONSOR_SHORT_NAME>`
2. Add a new `content.lr` file to the newly created directory, use the following template:
```
_model: sponsor
---
active: True
---
time: <YYYY>
---
name: <SPONSOR_LONG_NAME>
---
key: <ORDER_NUMBER>
---
logo: /static/images/sponsors/<SPONSOR_SHORT_NAME>.png
---
_hidden: yes
---
link: <SPONSOR_URL>
---
description:

<SPONSOR_DESCRIPTION>
```

Where <ORDER_NUMBER> is the next available key, i.e look at the key value for the last sponsor added and increment that by one. 

3. Add a logo image for the sponsor under `assets/static/images/sponsors/<SPONSOR_SHORT_NAME>.png`

### How to remove a Current Sponsor

Once a sponsor is no longer funding us, they need to be moved to the "Past Sponsors" list

1. Open up the sponsor contents file e.g `content/about/sponsors/<SPONSOR_SHORT_NAME>`
2. Edit the value for the `active` field from `True` to `False`

## How to add a new Tor person

1. Create a new directory for the person under `content/about/people/` e.g `content/about/people/<NICKNAME>`

2. Add a new `content.lr` file to the newly created directory, use the following template:

```
_model: person
---
_hidden: yes
---
role: core (use "board" for a board person - board people also have a "title" field)
---
name: <PERSON FULL NAME>
---
pronoun: https://pronoun.is/<PRONOUN> (optional)
---
twitter_handle: <TWITTER USERNAME> (optional)
---
nickname: <NICKNAME>
---
gpg: <LINK TO KEY> (This could either be a textfile under /assets/static/keys or a link)
---
image: <LINK TO IMG> (Optional. If a link to an image under /static/images/people/ is not provided the onion image is displayed instead)
---
description:

<DESCRIPTION>

```
3. Add a person image (if the person want to use an image) under `assets/static/images/people/<NICKNAME>.png`
4. Add a person gpg/pgp key (if the person want to use a txt key instead of a link) under `assets/static/keys/<NICKNAME>.txt`

## How to add a new release

### Tor Browser

For the canonical source of this document, please see: https://gitweb.torproject.org/tor-browser-spec.git/tree/processes/ReleaseProcess#n142

1. Update `content/projects/torbrowser/RecommendedTBBVersions/contents.lr`. This is file is responsible for the following page: https://www.torproject.org/projects/torbrowser/RecommendedTBBVersions/ used by Tor Browser
2. Update `databags/versions.ini`

If you want to add a new locale for Tor Browser:

- For stable edit: `databags/download-alternatives.ini` 
- For alpha edit: `databags/download-alternatives.ini`

### Tor 
1. Update `databags/versions.ini`