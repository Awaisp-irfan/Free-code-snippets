# Turn Off Automatic Theme Updates

Same idea, scoped to themes only — handy when you're actively customizing a theme and don't want it silently overwritten.

```php
add_filter( 'auto_update_theme', '__return_false' );
```
