# Replace the WordPress Logo on the Login Page

Swaps the default WordPress logo above the login form for your own, via a bit of inline CSS.

```php
/**
 * Insert custom login logo
 */
function custom_login_logo() {
    echo '
        <style>
            .login h1 a { 
                background-image: url(image.jpg) !important; 
                background-size: 234px 67px; 
                width:234px; 
                height:67px; 
                display:block; 
            }
        </style>
    ';
}

add_action( 'login_head', 'custom_login_logo' );
```
