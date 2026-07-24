# Custom Notice on the WooCommerce Login/Registration Form

Drops a custom message above the login and registration form on the My Account page — handy for a promo note, a heads-up about registration requirements, or just a friendlier welcome.

_From: [mnestorov/wp-snippets](https://github.com/mnestorov/wp-snippets) (Unlicense — public domain)_

```php
function wc_custom_login_message() {
   if ( get_option( 'woocommerce_enable_myaccount_registration' ) == 'yes' ) {
       $html  = '<div class="woocommerce-info">';
       $html .= '<p>' . _e( 'Your custom message goes here.' ) . '</p>';
       $html .= '</div>';
       echo $html;
   }
}

add_action( 'woocommerce_before_customer_login_form', 'wc_custom_login_message' );
```
