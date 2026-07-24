# Silence the jQuery Migrate Console Warning

_From: [mnestorov/wp-snippets](https://github.com/mnestorov/wp-snippets) (Unlicense — public domain)_

Removes the “JQMIGRATE: Migrate is installed...” message that shows up in the browser console on sites still using jQuery Migrate.

```php
/**
 * Disable the message "JQMIGRATE: Migrate is installed version 1.4.1"
 */
add_action('wp_default_scripts', function ($scripts) {
    if (!empty($scripts->registered['jquery'])) {
        $scripts->registered['jquery']->deps = array_diff($scripts->registered['jquery']->deps, ['jquery-migrate']);
    }
});
```
