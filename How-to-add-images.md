Lektor use markdown.

Add images to: https://dip.torproject.org/web/community/tree/master/assets/static/images

Then reference them in Markdown from: https://community.torproject.org/static/images/

Ex:
```
Inline-style: 
![alt text](https://community.torproject.org/static/images/home/png/onion-services.png "Onion Service 1")

Reference-style: 
![alt text][onion]

[onion]: https://community.torproject.org/static/images/home/png/onion-services.png "Onion Service 2"

```