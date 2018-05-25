## Loading The Helper

```
$app = \Concrete\Core\Support\Facade\Application::getFacadeApplication();
$rt = $app->make('helper/form/rating');
```

## Usage

### $rt->rating($name, $value = null, $includeJS = true);

@param string $name - The field name  
@param string $value - The selected value  
@param boolean $includeJS - Should this include javascript  