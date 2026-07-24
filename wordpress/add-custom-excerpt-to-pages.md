# Enable the Excerpt Field on Pages

Pages don't show an Excerpt box by default — this turns it on, the same way it already works for posts.

```php
/**
 * Add custom excerpt to pages
 */
function add_page_excerpt() {
    add_post_type_support( 'page', array( 'excerpt' ) );
}

add_action( 'init', 'add_page_excerpt' );
```
