# Allow ZIP, MOBI, PDF & EPUB Uploads

_From: [mnestorov/wp-snippets](https://github.com/mnestorov/wp-snippets) (Unlicense — public domain)_

WordPress blocks a handful of file types from the Media Library by default — this whitelists a few common document and ebook formats.

```php
/**
 * This code allows you to upload the file formats ZIP, MOBI, PDF, and EPUB
 */
function add_custom_mime_types( $mimes ) {
    $new_file_types = array (
        'zip'  => 'application/zip',
        'mobi' => 'application/x-mobipocket-ebook',
        'pdf'  => 'application/pdf',
        'epub' => 'application/epub+zip'
    );
    
    return array_merge( $mimes, $new_file_types );
}

add_filter( 'upload_mimes', 'add_custom_mime_types' );
```
