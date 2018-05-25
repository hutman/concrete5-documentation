## Loading The Helper

```
$app = \Concrete\Core\Support\Facade\Application::getFacadeApplication();
$af = $app->make('helper/form/calendar_event_selector');
```

## Usage

$af->selectEvent($calendar, $fieldName, $eventID = false);

@param object $calendar - Calendar object.  
@param string $fieldName - Form field name.  
@param int $eventID - Selected eventID  