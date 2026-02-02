# Hydra [ LEGACY TEMPLATE NO LONGER MAINTAINED ]

Marketing site template for Jekyll. Browse through a [live demo](https://proud-alligator.cloudvent.net/).
Increase the web presence of your brand with this configurable theme.

![Hydra template screenshot](images/_screenshot.png)

Hydra was made by [CloudCannon](http://cloudcannon.com/), the Cloud CMS for Jekyll.

Find more templates, themes and step-by-step Jekyll tutorials at [CloudCannon Academy](https://learn.cloudcannon.com/).

[![Deploy to CloudCannon](https://buttons.cloudcannon.com/deploy.svg)](https://app.cloudcannon.com/register#sites/connect/github/CloudCannon/hydra-jekyll-template)

## Features

* Contact form
* Pre-built pages
* Pre-styled components
* Blog with pagination
* Post category pages
* Disqus comments for posts
* Staff and author system
* Configurable footer
* Optimised for editing in [CloudCannon](http://cloudcannon.com/)
* RSS/Atom feed
* SEO tags
* Google Analytics

## Setup

1. Add your site and author details in `_config.yml`.
2. Add your Google Analytics and Disqus keys to `_config.yml`.
3. Get a workflow going to see your site's output (with [CloudCannon](https://app.cloudcannon.com/) or Jekyll locally).

## Develop

Hydra was built with [Jekyll](http://jekyllrb.com/) version 3.3.1, but should support newer versions as well.

Install the dependencies with [Bundler](http://bundler.io/):

~~~bash
$ bundle install
~~~

Run `jekyll` commands through Bundler to ensure you're using the right versions:

~~~bash
$ bundle exec jekyll serve
~~~

## Editing

Hydra is already optimised for adding, updating and removing pages, staff, advice, company details and footer elements in CloudCannon.

### Posts

* Add, update or remove a post in the *Posts* collection.
* The **Staff Author** field links to members in the **Staff** collection.
* Documentation pages are organised in the navigation by category, with URLs based on the path inside the `_docs` folder.
* Change the defaults when new posts are created in `_posts/_defaults.md`.

### Contact Form

* Preconfigured to work with CloudCannon, but easily changed to another provider (e.g. [FormSpree](https://formspree.io/)).
* Sends email to the address listed in company details.

### Staff

* Reused around the site to save multiple editing locations.
* Add `excluded_in_search: true` to any documentation page's front matter to exclude that page in the search results.

### Navigation

* Exposed as a data file to give clients better access.
* Set in the *Data* / *Navigation* section.

### Footer

* Exposed as a data file to give clients better access.
* Set in the *Data* / *Footer* section.


---

## Development Notes (Windows / Ruby 3.4)
**Added:** 2026-02-01 by Earl Lamier

While setting up Jekyll locally on Windows with Ruby 3.4, a few compatibility
adjustments were required due to changes in Ruby’s standard library and
dependency handling.

### Added
The following gems were added to the `Gemfile` to ensure Jekyll runs correctly
on Ruby 3.4 (Windows):

- `csv`
- `base64`
- `bigdecimal`
- `tzinfo`
- `tzinfo-data` (Windows only)
- `webrick`

### Removed
To prevent build conflicts caused by duplicate output paths:

- Removed `index.markdown` (kept `index.html`)
- Removed `about.html` (kept `about.markdown`)

### Result
- Jekyll builds and serves locally without errors
- Configuration is explicit and stable on Windows
- No impact on GitHub Pages deployment
