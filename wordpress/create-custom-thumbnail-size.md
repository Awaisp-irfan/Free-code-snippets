# Register and Output a Custom Image Size

_From: [mnestorov/wp-snippets](https://github.com/mnestorov/wp-snippets) (Unlicense — public domain)_

Defines a new named thumbnail size, plus two different ways to pull that image back out in a template.

```php
/**
 * Create custom thumbnail size
 */
add_image_size( 'custom-thumbnail', 250, 250, true );
```

**Option A — get the image array**

 ```php
 $thumb = wp_get_attachment_image_src( get_post_thumbnail_id($post->ID), 'custom-thumbnail' );

 echo $thumb[0]; 
 ```
 
**Option B — simpler, WordPress 4.4+**

```php
the_post_thumbnail_url( $size );
```
