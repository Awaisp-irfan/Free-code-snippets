# Enable Tags for Media Attachments

_From: [mnestorov/wp-snippets](https://github.com/mnestorov/wp-snippets) (Unlicense — public domain)_

Same idea as attachment categories, but for tags — lets you tag individual media library items.

```php
/**
 * Add tags for attachments
 */
function add_tags_for_attachments() {
    register_taxonomy_for_object_type( 'post_tag', 'attachment' );
}

add_action( 'init' , 'add_tags_for_attachments' );
```
