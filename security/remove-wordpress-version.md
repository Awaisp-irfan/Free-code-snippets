# Hide the WordPress Version Number

Strips the WordPress version string out of your site's `<head>`, so it's not sitting in plain sight for anyone scanning your site for a known vulnerability tied to a specific version.

```php 
/**
 * Remove WordPress version.
 * Better to hide it and keep hackers in the dark.
 */
function remove_wp_version() {
    return '';
}
add_filter( 'the_generator', 'remove_wp_version' );
```
