# Exclude a Category From the Main WordPress Loop

Hides posts from a specific category ID across the site's default queries — handy for keeping an internal or catch-all category out of public listings.

```php
/**
 * Exclude a category from all WordPress loops
 */
add_action( 'pre_get_posts', function( $query ) { // anonymous callback
    
    global $wp_query; 

    // Hard coded category ID, but can be dynamic: esc_attr(get_option('your-cat-id')); 
    $excluded_cat_id = 25;

    // add category ID to existing, avoid overwriting it 
    $cat[] = $query->get( 'cat' );
    $cat[] = "-" . $excluded_cat_id;

    $query->set( 'cat', $cat );
    }
});
```
