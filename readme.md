Custom Admin Branding
=====================

A class to allow theme/plugin developers to easily brand the WordPress login and admin screens

## Features

* Change the login page logo
* Change the login page logo link URL and title attribute
* Add a designer credit to the login page and admin footer
* Remove the built in WordPress menu item from the admin menu bar
* Add a favicon to the login, admin and front end of the site

## Who This is For

This is for developers producing custom WordPress themes, plugins, or managed solutions for clients.

This class is not meant to be used in plugins or themes making their way into the WordPress repo.  Unless, of course, you want to make a plugin to allow users to change their own login and admin branding.

Clients like seeing their names and logos on things. The above features seems to have made some of my own clients happy, so I thought I'd share them!

## Usage

First, grab the code.  You can do this with git:

    $ cd /your/theme/directory
    $ git clone git://github.com/chrisguitarguy/WP-Custom-Admin-Branding.git branding

Or you can download the [zipball](https://github.com/chrisguitarguy/WP-Custom-Admin-Branding/zipball/master).

Next up, drop a few lines of code in your `functions.php`.

    <?php
    // somewhere in `functions.php`
    require_once( trailingslashit( dirname( __FILE__ ) ) . 'branding/branding.php' );

    // Create a new instance of the `Custom_Admin_Branding` class
    // Pass in whatever values you want (see the "Arguments" section below)
    new Custom_Admin_Branding( array( 
        'login_url'       => 'http://example.com', 
        'login_image'     => 'http://placebear.com/273/63',
        'login_title'     => 'This is a title',
        'designer_url'    => 'http://christopherdavis.me',
        'designer_anchor' => 'Christopher Davis',
        'favicon_url'     => 'http://placebear.com/16/16',
        'remove_wp'       => true
    ) );

### Arguments

* `login_url` - Where would you like the logo above the login form to link? Defaults to wordpress.org
* `login_image` - What will replace the WordPress logo on the login page.
* `login_title` - The title attribute on the logo link on the login page.
* `login_height` - Height of the login logo image.
* `login_width` - Width of the login login logo image. ~320px is recommended. Defaults to 326px.
* `designer_url` - Used in the credit link on the login and admin pages. Your website!
* `designer_anchor` - Anchor text for the credit link.
* `favicon_url` - The favicon to be added on the login and admin pages and on the front end.
* `remove_wp` - Remove the WordPress drop down from the admin menu bar if set to true. The Default is false.

### Example

Check out the [theme branch](https://github.com/chrisguitarguy/WP-Custom-Admin-Branding/tree/theme) for an example.

## License

GPLv2, just like WordPress.
