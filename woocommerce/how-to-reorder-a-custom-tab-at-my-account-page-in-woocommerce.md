# Reorder (and Rename) the My Account Menu Tabs

Controls the exact order the tabs appear in on the WooCommerce My Account page, and lets you rename any of them at the same time — including slotting in a custom tab you've added elsewhere.

```php
/**
 * Rename or re-order my account menu items
 */
function woo_reorder_my_account_menu() {
    $neworder = array(
        'dashboard'          => __( 'Dashboard', 'woocommerce' ),
        'orders'             => __( 'Previous Orders', 'woocommerce' ),
        'custom-tab'         => __( 'Custom Tab', 'woocommerce' ),
        'edit-address'       => __( 'Addresses', 'woocommerce' ),
        'edit-account'       => __( 'Account Details', 'woocommerce' ),
        'customer-logout'    => __( 'Logout', 'woocommerce' ),
    );
    
    return $neworder;
}

add_filter ( 'woocommerce_account_menu_items', 'woo_reorder_my_account_menu' );
```
