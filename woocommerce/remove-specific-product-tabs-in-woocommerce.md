# Hide Specific Tabs on the WooCommerce Product Page

Removes the Description, Reviews, and Additional Information tabs from a product page — common when a product's details are already covered elsewhere on the page and the default tabs just add clutter.

_From: [mnestorov/wp-snippets](https://github.com/mnestorov/wp-snippets) (Unlicense — public domain)_

```php
function wc_remove_product_tabs( $tabs ) {
   // remove the description tab
   unset( $tabs['description'] );
   
   // remove the reviews tab
   unset( $tabs['reviews'] );
   
   // remove the additional information tab
   unset( $tabs['additional_information'] );
   
   return $tabs;
}

add_filter( 'woocommerce_product_tabs', 'wc_remove_product_tabs', 99 );
```
