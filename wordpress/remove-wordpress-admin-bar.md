# Remove the Admin Bar's Front-End Spacing Fix

_From: [mnestorov/wp-snippets](https://github.com/mnestorov/wp-snippets) (Unlicense — public domain)_

Removes the small script WordPress adds to push page content down to make room for the admin bar — useful if you're hiding the bar another way and don't need the offset.

```php
/**
 * Remove WordPress admin bar
 */
function remove_admin_bar() {
    remove_action( 'wp_head', '_admin_bar_bump_cb' );
}

add_action( 'get_header', 'remove_admin_bar' );
```
