# Bulk-Convert Posts From One Post Type to Another

_From: [mnestorov/wp-snippets](https://github.com/mnestorov/wp-snippets) (Unlicense — public domain)_

Runs a direct database update to change every post of one post type into another — useful when migrating content into a new custom post type.

```php
/**
 * Switch post type
 */
function switch_post_type ( $old_post_type, $new_post_type ) {
    global $wpdb;

    // Run the update query
    $wpdb->update(
        $wpdb->posts,
        // Set
        array( 'post_type' => $new_post_type),
        // Where
        array( 'post_type' => $old_post_type )
    );
}
```
