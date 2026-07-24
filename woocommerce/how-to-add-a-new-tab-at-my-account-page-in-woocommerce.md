# Add a Custom Tab to the WooCommerce My Account Page

Registers a brand new endpoint (in this example, "Premium Support") and adds it as its own tab in the My Account menu, complete with its own content area — the standard pattern for extending My Account with anything WooCommerce doesn't ship by default.

_From: [mnestorov/wp-snippets](https://github.com/mnestorov/wp-snippets) (Unlicense — public domain)_

```php
/**
 * Register new endpoint slug to use for My Account page
 */

/**
 * @important-note	Resave permalinks or it will give 404 error
 */
function woo_custom_add_premium_support_endpoint() {
   add_rewrite_endpoint( 'premium-support', EP_ROOT | EP_PAGES );
}
  
add_action( 'init', 'woo_custom_add_premium_support_endpoint' );
  
/**
 * Add new query var
 */
  
function woo_custom_premium_support_query_vars( $vars ) {
   $vars[] = 'premium-support';
   return $vars;
}
  
add_filter( 'woocommerce_get_query_vars', 'woo_custom_premium_support_query_vars', 0 );
  
/**
 * Insert the new endpoint into the My Account menu
 */
function woo_custom_add_premium_support_link_my_account( $items ) {
   $items['premium-support'] = 'Premium Support';
   return $items;
}
  
add_filter( 'woocommerce_account_menu_items', 'woo_custom_add_premium_support_link_my_account' );
  
/**
 * Add content to the new endpoint
 */
function woo_custom_premium_support_content() {
   echo '<h3>Premium WooCommerce Support</h3><p>Welcome to the WooCommerce support area.</p>';
   echo do_shortcode( ' /* your shortcode here */ ' );
}

/**
 * @important-note	"add_action" must follow 'woocommerce_account_{your-endpoint-slug}_endpoint' format
 */
add_action( 'woocommerce_account_premium-support_endpoint', 'woo_custom_premium_support_content' );
```
