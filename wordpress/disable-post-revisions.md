# Turn Off Post Revisions Entirely

_From: [mnestorov/wp-snippets](https://github.com/mnestorov/wp-snippets) (Unlicense — public domain)_

Stops WordPress from saving a new revision every time you update a post or page.

```php
define( 'WP_POST_REVISIONS', false );
```

WordPress normally keeps a copy of a post or page every time you save it, so you can roll back to an earlier version later. You can turn that off completely, or cap it at a fixed number instead (see the related snippet for that version).

**Where it goes**

Add the line above to your **_wp-config.php_**.
