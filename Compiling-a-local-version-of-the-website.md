* Download Lektor: [​https://www.getlektor.com/downloads/](​https://www.getlektor.com/downloads/)
* Clone the repo from torgit (this is a read only repository): ​[https://git.torproject.org/project/web/tpo.git](https://git.torproject.org/project/web/tpo.git)
* Init the building blocks submodule: `$ cd tpo/lego && git submodule update --init`

Translations for the website are imported by Jenkins when bulding the page, but if you want to test them, download the [correct branch](https://gitweb.torproject.org/translation.git/log/?h=tpo-web) of the translations repo to the ./i18n/ folder.

Finally run:
`$ lektor server` to run a local continuous builder
`$ lektor build -O <folder>` to just build the website once.