# SitemapBundle

A simple eZ Publish 5 bundle providing a controller to generate an XML sitemap on the fly.
It provides a human-readable stylesheet.

## How to install

Install into vendors using composer:

	composer --update-no-dev require "eab/tutei-sitemap-bundle":">=0.9"

Or download into src using git:

    git clone https://github.com/eab-dev/TuteiSitemapBundle.git src/Tutei/SitemapBundle

Edit `ezpublish/EzPublishKernel.php` and add the following to the registerBundles() function:

    new Tutei\SitemapBundle\TuteiSitemapBundle()

Add the following to `ezpublish/config/routing.yml`:

    tutei_sitemap:
        resource: "@TuteiSitemapBundle/Resources/config/routing.yml"

Run the following to install the bundle assets:

    php ezpublish/console assets:install --symlink web

## How to configure

### Minimal configuration

Example parameters are in `/src/Tutei/SitemapBundle/Resources/config/services.yml`
Copy and modify these to your own `services.yml`

### How to target a specific siteaccess content tree?

By default, the sitemap takes the whole tree. If you want to restrict this to your siteaccess content tree, add `content.tree_root.location_id` parameter to your `default_settings.yml`. Example:

    parameters:
        ezsettings.mysiteaccess.content.tree_root.location_id: 92

## How to use

To view your sitemap access: `/sitemap.xml`
