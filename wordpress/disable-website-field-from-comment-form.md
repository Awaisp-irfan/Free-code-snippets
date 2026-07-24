# Remove the Website Field From the Comment Form

_From: [mnestorov/wp-snippets](https://github.com/mnestorov/wp-snippets) (Unlicense — public domain)_

Drops the optional URL field from the default comment form — a common ask since it mostly attracts spam links.

```php
/** 
 * Disable website field from comment form
 */
function disable_website_field( $field ) { 
    if( isset($field['url']) ) {
        unset( $field['url'] );
    }
    
    return $field;
}

add_filter('comment_form_default_fields', 'disable_website_field');
```
