For the canonical source, please see: https://gitweb.torproject.org/tor-browser-spec.git/tree/processes/ReleaseProcess#n155

1.  Edit [https://dip.torproject.org/web/tpo/blob/master/configs/i18n.ini#L2](https://dip.torproject.org/web/tpo/blob/master/configs/i18n.ini#L2). Please keep alphabetic order
```
content = en
translations = de,es,fr,is,it,ka,pt-BR,ru,tr,<new locale>
i18npath = i18n
translate_paragraphwise = False
url_prefix = https://www.torproject.org/
```
2.  Add it to [https://dip.torproject.org/web/tpo/blob/master/tpo.lektorproject#L13](https://dip.torproject.org/web/tpo/blob/master/tpo.lektorproject#L13). Please keep alphabetic order
```
[alternatives.de]
name = Deutsch (de)
url_prefix = /de/
locale = de
```
3.  Specify styling information for the new locale in [https://dip.torproject.org/web/tpo/blob/master/databags/alternatives.ini#L7](https://dip.torproject.org/web/tpo/blob/master/databags/alternatives.ini#L7). Please keep alphabetic order
```
[de]
direction = text-left
order = order-last
url = /de/
language = Deutsch (de)
```

You can then run `lektor build` to see if there are any errors, and see the language file generated on the '/i18n' folder