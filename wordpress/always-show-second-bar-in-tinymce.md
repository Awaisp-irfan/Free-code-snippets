# Keep the Second Toolbar Row Open in the Classic Editor

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
