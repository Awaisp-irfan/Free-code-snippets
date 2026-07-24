# Disable XML-RPC

Turns off WordPress's legacy XML-RPC interface and its related discovery links in the page `<head>` — a common security hardening step, since XML-RPC is a frequent brute-force target.

```php
/**
 * Disable xmlrpc.php
 */
 
add_filter( 'xmlrpc_enabled', '__return_false' );
remove_action( 'wp_head', 'rsd_link' );
remove_action( 'wp_head', 'wlwmanifest_link' );
```
