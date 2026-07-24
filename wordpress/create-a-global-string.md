# Define a Reusable Global String

_From: [mnestorov/wp-snippets](https://github.com/mnestorov/wp-snippets) (Unlicense — public domain)_

A simple pattern for storing a value — like a phone number or address — in one place and reusing it anywhere in your theme.

```php
/**
 * Create a global string
 */
function global_string() {
    return 'String';
}
```

**Usage**

```php
echo global_string();
```
