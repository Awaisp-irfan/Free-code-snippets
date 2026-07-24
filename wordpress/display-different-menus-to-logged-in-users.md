# Show a Different Nav Menu to Logged-In Users

Swaps which menu location renders depending on whether the visitor is logged in — useful for member-only sites or a different nav for admins.

```php
function nav_menu_args( $args = '' ) {
    if ( is_user_logged_in() ) {
        $args['menu'] = 'Logged-In'; // we need to create this menu
    } else {
        $args['menu'] = 'Primary Menu'; // we need to create this menu
    }

    return $args;
}

add_filter( 'wp_nav_menu_args', 'nav_menu_args' );
```
