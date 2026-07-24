# Build a Simple Custom Settings Page

Adds a new page under Appearance with the WordPress Settings API wired up — a starting point for a theme options panel with your own fields.

```php
/**
 * Create custom global settings
 */
function custom_settings_page() { ?>
    <div class="wrap">
    <h1>Custom Settings</h1>
    <form method="post" action="options.php">
        <?php
            settings_fields( 'section' );
            do_settings_sections( 'theme-options' );
            submit_button();
        ?>
    </form>
    </div><?php 
}

function custom_settings_add_menu() {
    add_theme_page( 'Custom Settings', 'Custom Settings', 'manage_options', 'custom-settings', 'custom_settings_page', null, 99 );
}

add_action( 'admin_menu', 'custom_settings_add_menu' );

// Example setting
function setting_twitter() { ?>
    <input type="text" name="twitter" id="twitter" value="<?php echo get_option('twitter'); ?>" /><?php 
}

function custom_settings_page_setup() {
    add_settings_section( 'section', 'All Settings', null, 'theme-options' );
    add_settings_field( 'twitter', 'Twitter Username', 'setting_twitter', 'theme-options', 'section' );
    register_setting( 'section', 'twitter' );
}

add_action( 'admin_init', 'custom_settings_page_setup' );
```

**Reading the saved value**

```php
echo get_option( 'twitter' );
```

Adapted from [Create a WordPress Theme Settings Page with the Settings API](http://www.sitepoint.com/create-a-wordpress-theme-settings-page-with-the-settings-api/).
