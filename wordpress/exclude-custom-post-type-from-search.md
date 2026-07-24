# Limit Search Results to Regular Posts Only

_From: [mnestorov/wp-snippets](https://github.com/mnestorov/wp-snippets) (Unlicense — public domain)_

Forces the default search to only return standard posts, keeping custom post types (and pages) out of search results.

```php
/**
 * Exclude custom post type from search
 */
function excludePages( $query ) {
   if ( $query->is_search ) {
      $query->set( 'post_type', 'post' );
   }
   return $query;
}

add_filter( 'pre_get_posts','excludePages' );
```
