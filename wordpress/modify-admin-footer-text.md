# Customize the wp-admin Footer Text

_From: [mnestorov/wp-snippets](https://github.com/mnestorov/wp-snippets) (Unlicense — public domain)_

Replaces the default “Thank you for creating with WordPress” line at the bottom of every admin screen.

```php
/**
 * Modify admin footer text
 */
function modify_footer() {
    echo 'Created by <a href="mailto:you@example.com">you</a>.';
}

add_filter( 'admin_footer_text', 'modify_footer' );
```
