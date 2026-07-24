# Override How a Currency Symbol Displays in WooCommerce

Some currencies don't have a widely-recognized symbol, so WooCommerce falls back to something unclear. This swaps in a custom symbol for a specific currency code instead — the example below covers Bulgarian Lev (BGN).

```php
function wc_change_bgn_currency_symbol( $currency_symbol, $currency ) {
  switch ( $currency ) {
    case 'BGN':
      $currency_symbol = 'BGN';
    break;
  }
  
  return $currency_symbol;
}

add_filter( 'woocommerce_currency_symbol', 'wc_change_bgn_currency_symbol', 10, 2 );
```
