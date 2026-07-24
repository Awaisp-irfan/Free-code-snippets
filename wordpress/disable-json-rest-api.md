# Disable the WordPress REST API

_From: [mnestorov/wp-snippets](https://github.com/mnestorov/wp-snippets) (Unlicense — public domain)_

Turns off the built-in JSON REST endpoints — worth doing only if you're certain nothing on your site (plugins, blocks, headless setups) depends on it.

```php
/** 
 * Disable JSON REST API  
 */
add_filter( 'json_enabled', '__return_false' );
add_filter( 'json_jsonp_enabled', '__return_false' );
```
