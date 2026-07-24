# Turn Off Automatic Plugin Updates

_From: [mnestorov/wp-snippets](https://github.com/mnestorov/wp-snippets) (Unlicense — public domain)_

Disables WordPress's background auto-updates specifically for plugins, without touching core or theme updates.

```php
add_filter( 'auto_update_plugin', '__return_false' );
```
