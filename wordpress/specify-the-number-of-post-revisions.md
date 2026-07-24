# Cap the Number of Saved Revisions Per Post

Instead of disabling revisions entirely, this keeps only a set number of the most recent ones.

```php
define('WP_POST_REVISIONS', 3);
```

Change the number below to whatever cap you want — 3 and 5 are common choices.

**Where it goes**

Add the line above to your **_wp-config.php_**.
