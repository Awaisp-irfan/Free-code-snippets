# Change the Default Excerpt Word Count

_From: [mnestorov/wp-snippets](https://github.com/mnestorov/wp-snippets) (Unlicense — public domain)_

WordPress trims excerpts to 55 words by default — this sets your own limit.

```php
/**
 * Modify excerpt length
 */
function custom_excerpt_length( $length ) {
    return 25;
}

add_filter( 'excerpt_length', 'custom_excerpt_length', 999 );
```
