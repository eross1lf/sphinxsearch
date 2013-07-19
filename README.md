sphinxsearch
============

This magento extension provides integration for Magento CE with a sphinx search server.

Versions
--------
sphinxsearch was tested on Magento CE version 1.7.X.X.
It probably works with 1.6.X.X too, but i haven't tested it yet.
Earlier versions of Magento won't work without changes in the extension code. 

Installation
------------
* Use modman (https://github.com/colinmollenhour/modman) for easy installation of this extension.
Integration with magento connect will be provided in the near future.
* Logout from magento backend to execute extension setup files.
* Login to backend to configure sphinxsearch under Configuration/Catalog/Sphinx Search Engine.
* Recreate index catalog_search

Installing sphinx server
------------------------
Please refer to the sphinx installation guide for your server OS.

Just a quick guide for Debian GNU/Linux or Ubuntu:

* `# apt-get install sphinxsearch`
* Then copy sphinx.conf.example to /etc/sphinxsearch/sphinx.conf and edit according to your database configuration.
This config file provides sphinx search server all information to create an its index for all products in your magento shop.
* Edit /etc/default/sphinxsearch (change NO to YES)
* re-create sphinx' index: `# indexer --rotate --all`
* start sphinx search with `# /etc/init.d/sphinxsearch start`

Done!