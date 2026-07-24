# Revert to the Classic Editor Without a Plugin

Turns off the block editor site-wide with a single filter — no Classic Editor plugin required.

```php
add_filter( 'use_block_editor_for_post', '__return_false' );
```
