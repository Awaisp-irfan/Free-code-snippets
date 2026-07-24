# Enable Categories for Media Attachments

_From: [mnestorov/wp-snippets](https://github.com/mnestorov/wp-snippets) (Unlicense — public domain)_

Lets you assign regular post categories to media library attachments, so images and files can be organized and filtered the same way posts are.

```php
/**
 * Add categories for attachments
 */
function add_categories_for_attachments() {
    register_taxonomy_for_object_type( 'category', 'attachment' );
}

add_action( 'init' , 'add_categories_for_attachments' );
```
