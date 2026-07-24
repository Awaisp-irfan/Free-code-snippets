# Add a “Lead” Class to a Post's Opening Paragraph

_From: [mnestorov/wp-snippets](https://github.com/mnestorov/wp-snippets) (Unlicense — public domain)_

Wraps the first paragraph of post content in a `lead` class, handy for styling an intro paragraph larger or bolder than the rest.

```php
/**
 * Add lead class to first paragraph
 */
function first_paragraph( $content ) {
    return preg_replace( '/<p([^>]+)?>/', '<p$1 class="lead">', $content, 1 );
}

add_filter( 'the_content', 'first_paragraph' );
```

Only targets [the_content](https://developer.wordpress.org/reference/functions/the_content/), so it won't affect excerpts or widget text.
