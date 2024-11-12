# Craft wordpress import starter
A pre-configured Craft CMS starter project designed to streamline the migration process from WordPress. This project provides a foundation that closely mirrors a default WordPress installation, making it easier to import and work with your WordPress content.

## Features

- Ready-to-use templates for common WordPress content types
- Live Preview configured out of the box
- Sensible defaults that match WordPress content structure
- Inclued plugins to import your data:
  - The official [WordPress Import plugin](https://github.com/craftcms/wp-import)
  - The official [CKEditor plugin](https://plugins.craftcms.com/ckeditor)
  - [Verbb Comments](https://plugins.craftcms.com/comments)

## Requirements

- PHP 8.0.2+
- Composer 2.0+
- MySQL 5.7.8+ or PostgreSQL 10+
- A WordPress site to migrate from
- 
While we strongly recommend DDEV for new Craft projects, alternate installation methods are available for anyone with a preexisting environment or preferred workflow that meets its requirements.

Install or update DDEV(opens new window), then follow these steps:

Create a project directory and move into it:

mkdir craft-wp
cd craft-wp/

Bootstrap the project using the craftcms/starter-wordpress package:

ddev composer create -y "craftcms/starter-wordpress"
