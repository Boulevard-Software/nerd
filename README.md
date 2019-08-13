# ![Logo](https://github.com/Boulevard-Software/n.e.r.d/blob/master/logo.png) Named Entity Recognition Dashboard
[![MIT Licensed](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE.md)

The `NERD` dashboard is used for training [Apache OpenNLP](https://opennlp.apache.org/) models, crawling and processing results. Turning web pages into data that can be exported to database or [Apache Solr](http://lucene.apache.org/solr/).

- Create a job, sets online sources of data.
- Train on sample documents, teach the system the data your interested in.
- Crawl and process results to database table.
- Filter and export to Apache Solr for easy searching.

![Screenshot](https://raw.githubusercontent.com/Boulevard-Software/n.e.r.d/master/screenshot.jpg)


## Support 

A beta version of the project will be available for download in September. Work is needed on documentation and testing. If your interested in getting started before that and you need some help, just reach out and I'll do what I can. Demo coming soon. 

[Github Issues Tracking](https://github.com/Boulevard-Software/nerd/issues) | [Trello](https://trello.com/b/UgDofsbl/nerd) | [Email](http://webanet.com.au)


## Requirements
    
    - Apache (with mod_rewrite + mod_ssl)
    - Apache OpenNLP
    - Apache Solr
    - Oracle Java 8
    - PHP 7+ (php-curl php-xml php-mbstring php-pgsql php-tidy php-intl)
    - PostgreSQL
    - PHP Composer

## Installation

1. Download or clone the repo.
2. Update dependancies using composer
3. Set write access to `data` + `cache` directories.
4. Setup configutation `/bootstrap/parameters.yml.dist` + `settings.php.dist` 
5. Configure Apache web server virtual host
6. Create [reCAPTCHA](https://www.google.com/recaptcha/)
6. Add admin user (invite others within the dashboard)

``` bash
git clone https://github.com/Boulevard-Software/n.e.r.d.git 
composer update
cd console
composer update
chown -R {you}:www-data ../{dir}
chmod -R 755 ../{dir}
chmod -R 775 cache
chmod -R 775 data
chmod -R +x console/bin/*
chmod -R 775 http/Resources/views/Emails
composer update
cd ../bootstrap
cp parameters.yml.dist parameters.yml
cp settings.php.dist settings.php
nano parameters.yml
nana settings.php
cp wiki/files/conf.txt /etc/apache2/sites-available/nerd.conf
a2ensite /etc/apache2/sites-available/nerd.conf
apache service reload
console/nerd users add "admin"
```

## Internationalization

The project uses [illuminate/translation](https://github.com/illuminate/translation) for language. To add your language simply copy the http/Resources/lang/en_US directory to suit and translate. English only so far.

## Contributing

Please! Contributions are welcome and will be fully credited. Submit a pull request here at Github.
Code formatting as per [PHP Unit](https://github.com/sebastianbergmann/phpunit/blob/master/.github/CONTRIBUTING.md).

![Apache OpenNLP](https://cwiki.apache.org/confluence/download/thumbnails/74691846/opennlp-poweredby.png?version=1&modificationDate=1514406818000&api=v2)
