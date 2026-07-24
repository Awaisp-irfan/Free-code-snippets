# WordPress Pretty Permalinks .htaccess Rules

The standard rewrite block WordPress relies on for "pretty" permalinks — it routes any request that isn't a real file or folder through `index.php` so WordPress can handle the URL itself.

```txt
# BEGIN WordPress
<IfModule mod_rewrite.c>
RewriteEngine On
RewriteBase /
RewriteRule ^index\.php$ - [L]
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule . /index.php [L]
</IfModule>
# END WordPress
```

**Setup:**

1. Make a backup copy of your current `.htaccess` file before touching anything.
2. Clear out the existing contents of `.htaccess`.
3. Paste the rules above in its place.
4. Save the file.
