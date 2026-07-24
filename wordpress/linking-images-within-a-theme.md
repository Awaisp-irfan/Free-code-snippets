# Two Ways to Reference Theme Images in Templates

_From: [mnestorov/wp-snippets](https://github.com/mnestorov/wp-snippets) (Unlicense — public domain)_

Two equivalent ways to build the path to an image sitting inside your theme folder, for use directly in template markup.

```php
<img src="<?php bloginfo( 'stylesheet_directory' ); ?>/img/image.png" />
```

or

```php
<img src="<?php echo get_stylesheet_directory_uri(); ?>/images/image.jpg" />
```
