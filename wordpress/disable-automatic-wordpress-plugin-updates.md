# Turn Off Automatic Plugin Updates

Disables WordPress's background auto-updates specifically for plugins, without touching core or theme updates.

```php
add_filter( 'auto_update_plugin', '__return_false' );
```
