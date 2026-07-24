# Keep the Second Toolbar Row Open in the Classic Editor

_From: [mnestorov/wp-snippets](https://github.com/mnestorov/wp-snippets) (Unlicense — public domain)_

Skips the extra click to expand TinyMCE's second formatting row — it's just always visible.

```php
/**
 * Always show second bar in TinyMCE
 */
function show_tinymce_toolbar( $in ) {
    $in['wordpress_adv_hidden'] = false;
    return $in;
}

add_filter( 'tiny_mce_before_init', 'show_tinymce_toolbar' );
```
