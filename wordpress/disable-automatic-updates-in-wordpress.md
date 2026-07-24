# Turn Off WordPress Core Auto-Updates

Stops WordPress from silently updating itself in the background — useful when you want to control exactly when updates happen.

```php
define( 'WP_AUTO_UPDATE_CORE', false );
```

**Where it goes**

Add the line above to your **_wp-config.php_**.
