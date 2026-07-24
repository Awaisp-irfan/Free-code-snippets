# Strip Version Query Strings From CSS/JS URLs

_From: [mnestorov/wp-snippets](https://github.com/mnestorov/wp-snippets) (Unlicense — public domain)_

Removes the `?ver=x.x` WordPress appends to enqueued stylesheets and scripts — some CDNs and caching setups don't cache query-string URLs well, so this helps them cache properly.

```php
/**
 * Remove query string from static resources 
 */
function remove_cssjs_ver( $src ) {
    if ( strpos( $src, '?ver=' ) ) {
        $src = remove_query_arg( 'ver', $src );
    }
	
    return $src;
}

add_filter( 'style_loader_src', 'remove_cssjs_ver', 10, 2 );
add_filter( 'script_loader_src', 'remove_cssjs_ver', 10, 2 );
```
