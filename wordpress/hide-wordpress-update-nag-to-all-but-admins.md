# Only Show the Update Nag to Admins

Hides the “WordPress X.X is available” banner from everyone except users who can actually run the update — cleans up the dashboard for clients and editors.

```php
/**
 * Hide WordPress update nag to all but admins
 */
function hide_update_notice_to_all_but_admin() {
    if ( !current_user_can( 'update_core' ) ) {
        remove_action( 'admin_notices', 'update_nag', 3 );
    }
}

add_action( 'admin_head', 'hide_update_notice_to_all_but_admin', 1 );
```
