# Notify the Admin When a User Updates Their Profile

_From: [mnestorov/wp-snippets](https://github.com/mnestorov/wp-snippets) (Unlicense — public domain)_

Sends an email to the site admin any time a user saves changes to their profile — useful on multi-author or membership sites.

```php
function user_profile_update( $user_id ) {
    $user_info = get_userdata( $user_id );

    $to       = get_option( 'admin_email' );
    $subject  = 'User Profile Updated';
    $message  = "Hello Administrator,\n\nThe " . $user_info->user_nicename . " (" . $user_info->user_email . ") profile has been updated! \n\n";
    $message .= "Site URL: " . get_bloginfo( 'wpurl' ) . "\n\n";
    $message .= "Regards, \n" . get_option( 'blogname' );

    wp_mail( $to, $subject, $message );
}

add_action( 'profile_update', 'user_profile_update', 10, 2 );
```
