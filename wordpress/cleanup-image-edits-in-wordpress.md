# Stop WordPress From Piling Up Image Edit Backups

By default, every time you crop or rotate an image, WordPress keeps the previous version around on the server. This makes it keep only the latest edit instead.

```php
define( 'IMAGE_EDIT_OVERWRITE', true );
```

Normally, each edit generates a brand new set of image files, and the older ones stick around even after you restore the original. Setting **_IMAGE_EDIT_OVERWRITE_** to **_true_** changes that — only the most recent edit is kept, and restoring the original clears the edited files out entirely.

**Where it goes**

Add the line above anywhere in your **_wp-config.php_**.
