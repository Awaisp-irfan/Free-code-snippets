# Track Post Views Without a Plugin

A lightweight view counter that stores a hit count in post meta each time a single post loads — enough to sort by “most viewed” without installing a dedicated plugin.

```php
/**
 * Show Popular Posts Without Plugins
 */
function count_post_visits() {
    if( is_single() ) {
        global $post;
        $views = get_post_meta( $post->ID, 'my_post_viewed', true );
        if( $views == '' ) {
            update_post_meta( $post->ID, 'my_post_viewed', '1' );   
        } else {
            $views_no = intval( $views );
            update_post_meta( $post->ID, 'my_post_viewed', ++$views_no );
        }
    }
}

add_action( 'wp_head', 'count_post_visits' );
```
