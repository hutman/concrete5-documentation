## Loading The Helper

```
$app = \Concrete\Core\Support\Facade\Application::getFacadeApplication();
$dtt = $app->make('helper/form/date_time');
```

The $dtt Object is now an instance of DateTimeHelper.

This helper provides a calendar and an optional time dropdown selector. Useful for selecting dates and date/time combinations.

## Usage

### $dtt->date($field, $value = null, $calendarAutoStart = true, array $datePickerOptions = array());

@param string $field The field name (will be used as $field parameter in the translate method)  
@param \DateTime|string $value The initial value  
@param bool $calendarAutoStart Set to false to avoid initializing the Javascript calendar  
@param array $datePickerOptions datepicker properties, see jquery-ui datepicker docs  

Creates form fields and JavaScript calendar includes for a particular item but includes only calendar controls (no time, so no time-zone conversions will be applied).

### $dtt->datetime($field, $value = null, $includeActivation = false, $calendarAutoStart = true, $classes = null, $timeResolution = 60, array $datePickerOptions = array());

@param string $field The field prefix (will be used as $field parameter in the translate method)  
@param \DateTime|string $value The initial value  
@param bool $includeActivation Set to true to include a checkbox to enable/disable the date/time fields  
@param bool $calendarAutoStart Set to false to avoid initializing the Javascript calendar  
@param string $classes A list of space-separated classes to add to the ui-datepicker-div container  
@param int $timeResolution The time resolution in seconds (60 means we won't ask seconds)  
@param array $datePickerOptions datepicker properties, see jquery-ui datepicker docs  

Creates form fields and JavaScript calendar includes for a particular item (date/time string representations will be converted from the user system-zone to the time-zone).

### $dtt->translate($field, $arr = null, $asDateTime = false);

@param string $field The name of the field to translate  
@param array $arr The array containing the value. If null (default) we'll use $_POST  
@param bool $asDateTime Set to true to get a DateTime object, false (default) for a string representation  

Takes a "field" and grabs all the corresponding disparate fields from $_POST and translates into a timestamp.

If $field has both date and time, the resulting value will be converted from the user timezone to the system timezone.

If $field has only date and not time, no timezone conversion will occur.