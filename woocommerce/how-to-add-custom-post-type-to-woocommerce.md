# Sell a Custom Post Type Through WooCommerce

Lets a non-`product` post type behave like a purchasable WooCommerce item — pulling its price from a custom field and giving it a working "Add to Cart" button, without converting it into an actual Product post type.

**Part 1 — hook your price field into WooCommerce**

```php
/**
 * Your post type should have a custom field called 'price'. 
 * We just have to make sure that its meta key is '_price'. 
 * How to check that? You can try to inspect the element:  
 * 1) Visit your post type admin page. 
 * 2) Try to add or edit a post in your post type admin page. 
 * 3) Look for the text box that has the price label and right click on the text box. 
 * 4) You should find it's name attribute to be '_price'. 
 * Usually the name is the meta key for a custom field.
 *
 * Add the code below if your meta key is not '_price'
 */
add_filter('woocommerce_get_price','wc_get_price', 20, 2);

function wc_get_price($price, $post) {
  if ($post->post->post_type === 'post') {
    $price = get_post_meta($post->id, 'price', true);
  }
  
  return $price;
}
```

**Part 2 — add the "Add to Cart" button**

```php
/**
 * You're now able to add a custom post type to the cart.
 * Now we have to create our own "Add to Cart" button.
 */
add_filter('the_content', 'wc_add_to_cart_button', 20, 1);

function wc_add_to_cart_button($content) {
  global $post;
 
  if ($post->post_type !== 'post') {
    return $content;
  }

  ob_start(); ?>
 
  <form action="" method="post">
    <input name="add-to-cart" type="hidden" value="<?php echo $post->ID ?>">
    <input name="quantity" type="number" value="1" min="1">
    <input name="submit" type="submit" value="Add to cart>
  </form><?php
	
  return $content . ob_get_clean();
}
```

**Heads up:** for the "added to cart" confirmation message to actually appear, you'll need to call `wc_print_notices()` somewhere in your `single-{post_type}.php` template.
