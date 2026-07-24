# "Add $X More for Free Shipping" Cart Notice

Checks the customer's cart against your lowest configured free-shipping threshold across all shipping zones, and shows a notice on the cart page telling them exactly how much more they need to spend to unlock it. Tested against WooCommerce 3.0.5.

_From: [mnestorov/wp-snippets](https://github.com/mnestorov/wp-snippets) (Unlicense — public domain)_

```php
/**
 * Notice with $$$ remaining to Free Shipping @ WooCommerce Cart 
 * Tested with WooCommerce version 3.0.5
 */ 
function wc_free_shipping_cart_notice() { 
  global $woocommerce; 
  // Get Free Shipping Methods for Rest of the World Zone & populate array $min_amounts
  $default_zone = new WC_Shipping_Zone(0); 
  $default_methods = $default_zone->get_shipping_methods();
    foreach( $default_methods as $key => $value ) {
      if ( $value->id === "free_shipping" ) {
        if ( $value->min_amount > 0 ) $min_amounts[] = $value->min_amount;
      }
    }
    
    // Get Free Shipping Methods for all other ZONES & populate array $min_amounts
    $delivery_zones = WC_Shipping_Zones::get_zones();
    foreach ( $delivery_zones as $key => $delivery_zone ) {
      foreach ( $delivery_zone['shipping_methods'] as $key => $value ) {
        if ( $value->id === "free_shipping" ) {
          if ( $value->min_amount > 0 ) $min_amounts[] = $value->min_amount;
        }
      }
    }
    
    // Find lowest min_amount
    if ( is_array($min_amounts) ) {
       $min_amount = min($min_amounts);
       // Get Cart Subtotal inc. Tax excl. Shipping
       $current = WC()->cart->subtotal;
       // If Subtotal < Min Amount, еcho Notice and add "Continue Shopping" button
       if ( $current < $min_amount ) {
          $added_text = esc_html__('You need to add ', 'woocommerce' ) . wc_price( $min_amount - $current ) . esc_html__(' for free delivery!', 'woocommerce' );
    $return_to = apply_filters( 'woocommerce_continue_shopping_redirect', wc_get_raw_referer() ? wp_validate_redirect( wc_get_raw_referer(), false ) : wc_get_page_permalink( '/' ) );
    $notice = sprintf( '%s %s', esc_url( $return_to ), esc_html__( 'Continue shopping', 'woocommerce' ), $added_text );
    wc_print_notice( $notice, 'notice' );
       }
    }
}

add_action( 'woocommerce_before_cart', 'wc_free_shipping_cart_notice' );
```
