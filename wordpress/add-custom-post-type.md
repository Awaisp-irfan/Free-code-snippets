# Register a Basic Custom Post Type

A minimal starting template for registering your own custom post type, with title/editor/excerpt/thumbnail support and archive pages enabled.

```php
/**
 * Add custom post type
 */
function create_custom_post() {
    register_post_type( 'custom-post', // slug for custom post type
        array(
        'labels' => array(
            'name' => __( 'Custom Post' ),
        ),
        'public'       => true,
        'hierarchical' => true, 
        'has_archive'  => true,
        'supports'     => array(
            'title',
            'editor',
            'excerpt',
            'thumbnail',
        ), 
        'can_export' => true,
        'taxonomies' => array(
             'post_tag',
              category',
        )
    ));
}

add_action( 'init', 'create_custom_post' );
```

**Official reference**

[Function Reference/register post type](https://codex.wordpress.org/Function_Reference/register_post_type)

**Also useful**

[Dashicons](https://developer.wordpress.org/resource/dashicons/#menu)
