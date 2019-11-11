### **1. Download & install Lektor**

Run the command: `$ curl -sf https://www.getlektor.com/install.sh | sh`

**Troubleshoots**
*  If you get the error `curl command not found`, then you need to install curl first. You can do this by using the command: `sudo apt install curl`
* You may get `Error: None of the items in $PATH are writable. Run with sudo or add a $PATH item`. You can fix this by instead running `curl -sf https://www.getlektor.com/install.sh | sudo sh`

### **2. Clone the repo from torgit** (this is a read only repository)
Run the command `git clone https://git.torproject.org/project/web/tpo.git`

### **3. Install the [dependencies for the lektor-i18n-plugin](https://github.com/numericube/lektor-i18n-plugin#prerequisites)**
You can do this by running the following commands:
```
$ sudo apt-get install gettext python3-babel
$ pip install babel
```
### **4. Clone the translations repository**
Translations for the website are imported by Jenkins when building the page, but if you want to test them, download the [correct branch](https://gitweb.torproject.org/translation.git/log/?h=tpo-web) of the translations repo to the ./i18n/ folder:

```
$ git clone https://git.torproject.org/translation.git i18n
$ cd i18n
$ git checkout tpo-web
```

### **5. Initialize the building blocks submodule**
`$ cd tpo/lego && git submodule update --init`


### **6. Install and use Lektor i18n plugin**
`$ lektor plugins add lektor-i18n`

The translation mechanism is hooked into the build system. So translating a website just means building the website.

`$ lektor build`

> **Tip**: To save some time while you build in local, you can edit the [configs/i18n.ini](https://gitweb.torproject.org/project/web/tpo.git/tree/configs/i18n.ini) file and take some languages out of the 'translations' option. 

You can make changes to the pages. Most of [the content is on the `content/` folder](https://dip.torproject.org/torproject/web/tpo/wikis/Writing-the-content).

**Troubleshoots**
* If you encounter the error: `from urllib import requestImportError: cannot import name request`, you can fix it by going to `~tpo/lego/packages/xml-to-html/lektor_xml_to_html.py` and changing the line `from urllib import request` to `from urllib3 import request`. You may also have to do the same change for the `~tpo/lego/packages/txt-to-html/lektor_txt_to_html.py` file.

* A possible error is `UnicodeEncodeError: 'ascii' codec can't encode character u'\xae'` stemming from `~tpo/lego/packages/i18n/lektor_i18n.py`. This can be fixed by adding the following code snippet to the top of the page after the `import sys` phrase:
```
reload(sys)
sys.setdefaultencoding('utf8')
```


### **7. Finally,** 
enter `$ lektor server` to run a local continuous builder.
You should be able to access your local lektor instance at [http://127.0.0.1:5000/](http://127.0.0.1:5000/) from your computer.

# Most common lektor errors

#### FileNotFoundError:
    file = builtins.open(filename, mode, buffering) 
    FileNotFoundError: [Errno 2] No such file or directory: '/content/**some filename**/contents.lr'

This happens when a source file `contents.lr` has been deleted in the repository, but their associated language files are still there. So, when trying to update the language files, lektor fails because the source file is not there. Delete the folder with the translations and build again. 

##### Update lego
/training/code-of-conduct/index.html (jinja2.exceptions.UndefinedError: 'render_text' is undefined)

fixed with `git submodule update --init --recursive`


