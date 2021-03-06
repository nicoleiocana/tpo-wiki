Tor Project website is hosted at several computers for redundancy, and these computers are together called "the www rotation". Please check the ​[​static sites help page](https://help.torproject.org/tsa/doc/static-sites/) for more info.

> Please use this wiki documentation as a basis for other lektor sites, as community, support, tb-manual, styleguide, template, etc. 

The current git repository for the website can be found on ​[gitweb.tpo/project/web/tpo.git](https://gitweb.torproject.org/project/web/tpo.git/).

The repository is built via the following ​[Jenkins build process](https://jenkins.torproject.org/job/lektor-website-tpo-translation/).

The current git repository for the 2019 archive can be found on ​[gitweb.tpo/project/web/webwml.git](https://gitweb.torproject.org/project/web/webwml.git/).

The archive repository is built via the following ​[Jenkins build process](https://jenkins.torproject.org/job/website-build-webwml/).

The website is built via [Lektor](https://getlektor.com). Lektor is static file generator like Jekyll, Pelican, Hugo, Middleman and many more. 
This means that unlike WordPress or similar solutions it does not run on a server, but your local computer (or a build server), and generates static HTML that can be uploaded to any web server or content distribution platform like S3 with CloudFront.

The following excerpt was taken from [Lektor Documentation](https://www.getlektor.com/docs/what/).

Why go static? Because the vast, vast majority of websites will be read many more times than they will be updated. This is crucial because dynamic content does not come for free. It needs server resources and because program code is running there it needs to be kept up to date for to ensure there are no security problems that are left unpatched. Also when a website gets a sudden spike of traffic a static website will stay up for longer on the same server than a dynamic one that needs to execute code.

Sure, there are some things you cannot do on a static website, but those are not things you would use Lektor for. For small dynamic sections, JavaScript paired up with other services is a good solution.


