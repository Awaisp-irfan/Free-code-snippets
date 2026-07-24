# Load a Google Font the Proper WordPress Way

Registers and enqueues a Google Font stylesheet through `wp_enqueue_style`, instead of hardcoding a `<link>` tag in your theme's header.

```php
/**
 * Enqueue Google Fonts
 */
function google_fonts() {
    wp_register_style( 'OpenSans', '//fonts.googleapis.com/css?family=Open+Sans:400,600,700,800' );
    wp_enqueue_style( 'OpenSans' );
}

add_action( 'wp_print_styles', 'google_fonts' );
```
