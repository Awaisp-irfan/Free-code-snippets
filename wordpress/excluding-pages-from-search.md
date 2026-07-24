# Exclude Pages From Site Search

_From: [mnestorov/wp-snippets](https://github.com/mnestorov/wp-snippets) (Unlicense — public domain)_

Marks the built-in Page post type as excluded from search — similar to the custom-post-type version, but targeting Pages specifically.

```php
/**
 * Excluding pages from search
 */
function exclude_pages_from_search() {
    global $wp_post_types;
    $wp_post_types['page']->exclude_from_search = true;
}

add_action( 'init', 'exclude_pages_from_search' );
```
