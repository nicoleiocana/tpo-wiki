* Download Lektor: [​https://www.getlektor.com/downloads/](​https://www.getlektor.com/downloads/)
* Clone the repo from torgit (this is a read only repository): ​[https://git.torproject.org/project/web/tpo.git](https://git.torproject.org/project/web/tpo.git)
* Init the building blocks submodule: `$ cd tpo/lego && git submodule update --init`

Translations for the website are imported by Jenkins when bulding the page, but if you want to test them, download the [correct branch](https://gitweb.torproject.org/translation.git/log/?h=tpo-web) of the translations repo to the ./i18n/ folder.

Tip: To save some time while you build in local, you can edit the [configs/i18n.ini](https://gitweb.torproject.org/project/web/tpo.git/tree/configs/i18n.ini) file and take some languages out of the 'translations' option.

Finally run:
`$ lektor server` to run a local continuous builder
`$ lektor build -O <folder>` to just build the website once.

# Most common lektor errors

#### FileNotFoundError:
    file = builtins.open(filename, mode, buffering) 
    FileNotFoundError: [Errno 2] No such file or directory: '/content/**some filename**/contents.lr'

This happens when a source file `contents.lr` has been deleted in the repository, but their associated language files are still there. So, when trying to update the language files, lektor fails because the source file is not there. Delete the folder with the translations and build again. 