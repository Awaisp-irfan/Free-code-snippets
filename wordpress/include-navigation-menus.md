# Register and Output a Custom Nav Menu

_From: [mnestorov/wp-snippets](https://github.com/mnestorov/wp-snippets) (Unlicense — public domain)_

Adds a new menu location you can assign in Appearance → Menus, shows how to output it in a template, and includes the multi-menu version too.

```php
/** 
 * Include navigation menus
 */
function register_my_menu() {
    register_nav_menu( 'nav-menu', __( 'Navigation Menu' ) );
}

add_action( 'init', 'register_my_menu' );
```

Insert this where you want it to appear, and save the menu in **Appearance -> Menus**.

```php
wp_nav_menu( array( 'theme_location' => 'nav-menu' ) );
```

Here's the code for multiple menus:

```php
function register_my_menus() {
    register_nav_menus(
        array(
            'new-menu'      => __( 'New Menu' ),
            'another-menu'  => __( 'Another Menu' ),
            'an-extra-menu' => __( 'An Extra Menu' ),
        )
    );
}

add_action( 'init', 'register_my_menus' );
```
