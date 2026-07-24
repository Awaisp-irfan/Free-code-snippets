# Serve Media Library Files From a Different Domain or CDN

Points uploaded media at a separate host (like a CDN or assets subdomain) instead of your main site URL. Two approaches shown — a direct option update, and a filter-based version that avoids writing to the database.

```php
/**
 * Change Media Gallery URL
 */
if ( empty( get_option( 'upload_url_path' ) ) ) {
    update_option( 'upload_url_path', 'http://assets.website.com/wp-content/uploads' );
}
```

A cleaner alternative — filters the value on the fly instead of saving it to the options table:

```php
/**
 * Change Media Gallery URL
 */
add_filter( 'pre_option_upload_url_path', function() {
    return 'http://assets.website.com/wp-content/uploads';
});
```
