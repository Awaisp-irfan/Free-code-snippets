# Customize the Excerpt “More” Text

_From: [mnestorov/wp-snippets](https://github.com/mnestorov/wp-snippets) (Unlicense — public domain)_

Replaces the default ‘[...]’ that WordPress appends to trimmed excerpts with your own text.

```php
/**
 * Change More excerpt
 */
function custom_more_excerpt( $more ) {
    return '...';
}

add_filter( 'excerpt_more', 'custom_more_excerpt' );
```
