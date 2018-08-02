The JSON helper is useful when working with data that needs to be decoded from or encoded to the JSON format.

concrete5 uses JSON to communicate between the dashboard sitemap and the backend, and to/from the concrete5 marketplace.

## Loading the Helper

```
$app = \Concrete\Core\Support\Facade\Application::getFacadeApplication();
$json = $app->make('helper/json');
```

## Methods

### $json->decode($string, $as_array = false);

@param string $string The string to be json decoded
@param boolean $as_array Whether to return the restuls as an array

Decodes a string of JSON data into a PHP object or array. By default, the JSON data is decoded into an object. Setting the optional second parameter true will return an associative array.

### $json->encode($item);

@param mixed $item The item to be json encoded

Encodes a PHP object or array $item into a JSON string and returns it.