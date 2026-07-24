# Add a Preconnect Hint for Google Fonts

Tells the browser to open an early connection to Google's font CDN before it's actually needed, shaving a bit of load time off font requests.

```php
/**
 * Implement preconnect to Google Fonts in themes
 */
function twentyfifteen_resource_hints( $urls, $relation_type ) {
    // Checks whether the subject is carrying the source of fonts google and the `$relation_type` equals preconnect.
    // Replace `enqueue_font_id` the `ID` used in loading the source.
    if ( wp_style_is( 'enqueue_font_id', 'queue' ) && 'preconnect' === $relation_type ) {
        // Checks whether the version of WordPress is greater than or equal to 4.7
        // to ensure compatibility with older versions
        // because the 4.7 has become necessary to return an array instead of string
        
	if ( version_compare( $GLOBALS['wp_version'], '4.7-alpha', '>=' ) ) {
            // Array with url google fonts and crossorigin
            $urls[] = array(
                'href' => 'https://fonts.gstatic.com',
                'crossorigin',
            );
        } else {
            // String with url google fonts
            $urls[] = 'https://fonts.gstatic.com';
        }
    }
    
    return $urls;
}

add_filter( 'wp_resource_hints', 'twentyfifteen_resource_hints', 10, 2 ); 
```
