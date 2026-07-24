# Customize the “Read More” Link Text

Overrides WordPress's default more-link markup with your own label and formatting.

```php
/**
 * Change Read More link
 */
function custom_read_more_link() {
    return '<a href="' . get_permalink() . '">Read More</a>';
}

add_filter( 'the_content_more_link', 'custom_read_more_link' );
```
