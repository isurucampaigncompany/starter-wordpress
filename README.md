# Craft WordPress Import Starter
A pre-configured Craft CMS starter project designed to streamline the migration process from WordPress. This project provides a foundation that closely mirrors a default WordPress installation, making it easier to import and work with your WordPress content.

## Features
- Ready-to-use templates for common WordPress content types
- Live Preview configured out of the box
- Sensible defaults that match WordPress content structure
- Included plugins to import your data:
  - The official [WordPress Import plugin](https://github.com/craftcms/wp-import)
  - The official [CKEditor plugin](https://plugins.craftcms.com/ckeditor)
  - [Verbb Comments](https://plugins.craftcms.com/comments)

## Requirements
- DDEV installed locally
- PHP 8.0.2+
- Composer 2.0+
- MySQL 5.7.8+ or PostgreSQL 10+
- A publicly accessible WordPress site to migrate from

## Craft setup

1. Clone this repository and navigate into it:
```bash
git clone https://github.com/craftcms/starter-wordpress.git
cd starter-wordpress
```

2. Start DDEV:
```bash
# Optional: Update project domain in .ddev/config.yaml first
ddev start
```

3. Install Composer dependencies:
```bash
ddev composer install
```

4. Run Craft setup wizard:
```bash
ddev craft install
```

5. Install plugins and launch site:
```bash
ddev craft up
ddev launch
```

Your site should now open in the browser. Access the control panel at `https://project-name.ddev.site/admin`.

## Preparing Your WordPress Site

Before migration, you'll need to prepare your WordPress site. See the [wp-import repository](https://github.com/craftcms/wp-import) for complete documentation.

1. Install the WP Import Helper plugin:
   - Save `plugins/wp-import-helper.php` to your WordPress site's `wp-content/plugins/` folder
   - Log into WP Admin Dashboard
   - Navigate to Plugins and activate "wp-import helper"

2. Create an application password:
   - In WP Admin Dashboard, go to Users
   - Edit an administrator's account
   - Scroll to "Application Passwords"
   - Enter "Craft CMS" as the name
   - Click "Add New Application Password"
   - Save the username and generated password for later use (you'll need it on the import step)

3. Configure custom post types (if applicable):
   - Ensure `'show_in_rest' => true` is set in `register_post_type()`

4. Configure ACF fields (if applicable):
   - Enable "Show in REST API" for each field group

## Importing WordPress Content

1. Run the import script:
```bash
ddev craft wp-import
```

2. Enter your WordPress site details when prompted:
   - WordPress site URL
   - Admin username
   - Application password (created earlier)

The importer will create:
- A "Posts" section for your posts
- A "Pages" section for your pages
- An "Uploads" filesystem and volume for your media
- A "Post Content" CKEditor field with nested entry types for non-HTML block data

See the [wp-import repository](https://github.com/craftcms/wp-import) for full documentation, command options, and compatible 
fields.

## Using Your New Craft Site

### Control Panel Access
Navigate to Entries to see your Posts and Pages, where you can add and edit content and see Craft's Live Preview in action. You can also find your assets, categories, and comments in the sidebar.

### Review the content modeling
Navigate to Settings to see the sections, entry types, fields, and other elements the import generated.

### Start templating

We built some bare bones Twig templates to get you started in the project's templates folder. See how our templates work, or use it as a starting point for your own theme.

## Getting Help
If you have any questions or suggestions, you can reach us at support@craftcms.com or [post a GitHub issue](https://github.com/craftcms/starter-wordpress/issues).

We’ll do what we can to get you up and running with Craft!