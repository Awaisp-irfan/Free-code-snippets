# Load jQuery From Google's CDN Instead of Locally

Swaps WordPress's bundled jQuery for a specific version served from Google's CDN, on the front end only.

```php
/**
 * Modify jQuery
 */
function modify_jquery() {
    wp_deregister_script( 'jquery' );
    wp_register_script( 'jquery', 'https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js', false, '3.2.1' );
    wp_enqueue_script( 'jquery' );
}

if ( ! is_admin() ) add_action( 'wp_enqueue_scripts', 'modify_jquery' );
```
