## Lego

Lego contains the building blocks shared by all torproject.org websites. Theser are templates, plugins, databags, assets.

Each website repository has a submodule called lego. This is how the lego common elements are imported. Lego is imported in the main repository and the single files are sym-linked to their relative folders. Ex: [header template](https://dip.torproject.org/torproject/web/tpo/blob/master/templates/header.html) in torproject.orgg main website.

## Assets

Here is where you can find shared assets for all the websites

- [assets](https://dip.torproject.org/torproject/web/lego/tree/master/assets) 

## Databags

Some databags are shared for all the websites so that when something needs to be changed we don't have to edit the same file serveral times

- [databags](https://dip.torproject.org/torproject/web/lego/tree/master/databags)

## Models

At the moment lego holds only one model. This is the model for a page that redirects to a different resource

- [models](https://dip.torproject.org/torproject/web/lego/tree/master/models)

## Packages

Here is where all the used plugins are stored. If a new plugin is added to one of the websites needs to go in here.

- [plugins](https://dip.torproject.org/torproject/web/lego/tree/master/packages)

## Templates

Shared templates and macro are stored in this folder.

- [templates](https://dip.torproject.org/torproject/web/lego/tree/master/templates)