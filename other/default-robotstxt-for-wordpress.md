# A Baseline robots.txt Setup for WordPress

A starting-point `robots.txt` for a typical WordPress site — it keeps your uploads crawlable, keeps search engines out of the folders and pages that don't need indexing, and points crawlers to your sitemaps.

```txt
User-Agent: *
Allow: /wp-content/uploads/
Disallow: /wp-content/plugins/
Disallow: /wp-content/themes/
Disallow: /readme.html
Disallow: /?s=
Disallow: /search/

Sitemap: http://www.sitename.com/post-sitemap.xml
Sitemap: http://www.sitename.com/page-sitemap.xml
```

**Setup:**

1. Create a plain text file named `robots.txt`.
2. Paste the rules above into it.
3. Replace the placeholder sitemap URLs with your actual site's address.
4. Upload the file to your site's root directory (the same folder as `wp-config.php`).
