# Add a Custom Widget to the wp-admin Dashboard

Registers your own box on the main Dashboard screen — useful for surfacing client instructions, support links, or site-specific notes.

```php
/**
 * Create custom WordPress dashboard widget
 */
function dashboard_widget_function() {
    echo '
        <h2>Custom Dashboard Widget</h2>
        <p>Custom content here</p>
    ';
}

function add_dashboard_widgets() {
    wp_add_dashboard_widget( 'custom_dashboard_widget', 'Custom Dashoard Widget', 'dashboard_widget_function' );
}

add_action( 'wp_dashboard_setup', 'add_dashboard_widgets' );
```
