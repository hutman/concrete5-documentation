## Loading The Helper

```
$app = \Concrete\Core\Support\Facade\Application::getFacadeApplication();
$af = $app->make('helper/form/color');
```

## Usage

$af->output($inputName, $value = null, $options = array());

@param string $name - Form field name.  
@param string $value - Selected hex color.  
@param array $options - ??? Not sure what can go in here  