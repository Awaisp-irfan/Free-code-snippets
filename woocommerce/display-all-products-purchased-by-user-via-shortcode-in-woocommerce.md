# Shortcode: Show a Customer's Purchase History as a Product Grid

Registers a `[my_products]` shortcode that looks up everything the logged-in customer has ever bought (completed or processing orders) and renders it as a normal WooCommerce product loop — useful for a "buy again" section on the My Account page.

```php 
add_shortcode( 'my_products', 'wc_user_products_bought' );
  
function wc_user_products_bought() {
  
    global $product, $woocommerce, $woocommerce_loop;
    $columns = 3;
  
    // Get user
    $current_user = wp_get_current_user();
  
    // Get user orders (COMPLETED + PROCESSING)
    $customer_orders = get_posts( array(
        'numberposts' => -1,
        'meta_key'    => '_customer_user',
        'meta_value'  => $current_user->ID,
        'post_type'   => wc_get_order_types(),
        'post_status' => array_keys( wc_get_is_paid_statuses() ),
    ) );
  
    // Loop Through orders and get product IDs
    if ( ! $customer_orders ) return;
    
    $product_ids = array();
    
    foreach ( $customer_orders as $customer_order ) {
        $order = wc_get_order( $customer_order->ID );
        $items = $order->get_items();
        foreach ( $items as $item ) {
            $product_id = $item->get_product_id();
            $product_ids[] = $product_id;
        }
    }
    $product_ids = array_unique( $product_ids );
  
    // Query products
    $args = array(
       'post_type' => 'product',
       'post__in' => $product_ids,
    );
    
    $loop = new WP_Query( $args );
  
    // Generate WC loop
    ob_start();
    woocommerce_product_loop_start();
    while ( $loop->have_posts() ) : $loop->the_post();
    wc_get_template_part( 'content', 'product' ); 
    endwhile; 
    woocommerce_product_loop_end();
    woocommerce_reset_loop();
    wp_reset_postdata();
  
    // Return content
    return '<div class="woocommerce columns-' . $columns . '">' . ob_get_clean() . '</div>';
}
```
