# Let WordPress Manage Your `<title>` Tag

_From: [mnestorov/wp-snippets](https://github.com/mnestorov/wp-snippets) (Unlicense — public domain)_

Hands `<title>` tag generation over to WordPress core instead of hardcoding it in header.php — required for accurate SEO titles and compatibility with SEO plugins.

Important: delete any hardcoded `<title>` tag already in your header.php first, or you'll end up with two.

```php
/**
 * Utilize proper WordPress titles
 */
add_theme_support( 'title-tag' );
```
