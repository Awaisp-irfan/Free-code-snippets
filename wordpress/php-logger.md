# Log PHP Values to the Browser Console

A quick debugging helper that prints a PHP value straight into the browser's JavaScript console — handy for spotting what a variable actually contains without a full debug setup.

```php
/**
 * PHP Logger
 */
function php_logger( $data ) {
    $output = $data;
    if ( is_array( $output ) )
        $output = implode( ',', $output );
        
    // print the result into the JavaScript console
    echo "<script>console.log( 'PHP LOG: " . $output . "' );</script>";
}
```
