# Lock Down the Theme & Plugin File Editor

Turns off the built-in code editor under Appearance/Plugins in wp-admin, so nobody can edit theme or plugin files straight from the dashboard — a common target once an account gets compromised.

_From: [mnestorov/wp-snippets](https://github.com/mnestorov/wp-snippets) (Unlicense — public domain)_

```php 
define( 'DISALLOW_FILE_EDIT', true ); 
```

**Setup**

1. Open `wp-config.php` in the root of your WordPress install.
2. Add the line above anywhere before the `/* That's all, stop editing! */` comment.
3. Save the file — no need to touch anything else.
