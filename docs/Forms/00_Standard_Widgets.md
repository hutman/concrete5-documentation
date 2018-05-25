concrete5's form helper makes it easy to add form widgets to your single pages and custom blocks, and several advantages to writing full HTML tags.

1. **Data persistence on POST:** when submitting the core form helpers, their data will remain as originally entered, without having to worry about checking $_REQUEST variables. This is even the case for more complex form elements like radio buttons and checkbox lists.
2. **Attractive styling.** Form elements in the block add and edit dialogs will better adhere to concrete5 design guidelines when they are output using the core form helpers.
3. **Do more with less.** Once you learn the syntax, writing forms using these helpers can save you a lot of time and code.

## Loading the Helper

You can load the concrete5 form helper using the following simple code

```
$app = \Concrete\Core\Support\Facade\Application::getFacadeApplication();
$form = $app->make('helper/form');
```

The $form variable now contains an instance of the FormHelper class.

## Arguments

While each form helper function ultimately displays a different HTML tag, most take common arguments. Here is their explanation:

### $name

Name of the field. Oftentimes will set the ID of the field to the same valueOrMiscFields.

### $valueOrMiscFields

Initial field valueOrMiscFields. Typically optional.

### $miscFields

An associative array of additional attributes to be added to the input element. (e.g. array('style' => 'width: 100%')).

### $additionalClasses

A string of additional classes to be added to the class attribute on the tag.

**Note:** In most cases, only the $name of the field is a required function argument. Other items are optional. Additionally, if the $valueOrMiscFields is left blank, the $miscFields field can usually be specified as the second argument to the helper.

## Methods

### $form->hidden($name, $valueOrMiscFields)

Creates a hidden form element.

### $form->label($name, $valueOrMiscFields)

Creates a label for a form element. The $name parameter must match the $name of another form element.

### $form->text($name, $valueOrMiscFields, $miscFields)

Creates a text input element.

### $form->number($name, $valueOrMiscFields, $miscFields)

Creates a number input element.

### $form->email($name, $valueOrMiscFields, $miscFields)

Creates an email input element.

### $form->telephone($name, $valueOrMiscFields, $miscFields)

Creates a telephone input element.

### $form->url($name, $valueOrMiscFields, $miscFields)

Creates a url input element.

### $form->password($name, $valueOrMiscFields, $tagAttribute)

Outputs a password field.

### $form->textarea($name, $valueOrMiscFields, $miscFields)

Outputs a textarea form element.

### $form->select($name, $optionValues, $valueOrMiscFields, $miscFields)

Outputs a select menu. The $options argument is a PHP array. The keys of the array will be used as the select option valueOrMiscFieldss, while the array valueOrMiscFieldss will be displayed in the menu. The $valueOrMiscFields parameter controls the initially checked select element.

### $form->selectCountry($key, $selectedCountryCode, $configuration = [], $miscFields = [])

Renders a select menu to choose a Country.

@param string $key The name of the element. If $key denotes an array, the ID will start with $key but will have a progressive unique number added; if $key does not denotes an array, the ID attribute will be $key.  
@param string $selectedCountryCode the code of the Country to be initially selected  
@param array $configuration Configuration options. Supported keys are:  
- 'required': users must choose a Country?
- 'allowedCountries': an array containing a list of acceptable Country codes. If not set, all the countries will be selectable.
- 'linkStateProvinceField': set to true to look for text fields that have a "data-countryfield" attribute with the same valueOrMiscFields as this Country field name (updating the Country select will automatically update the State/Province list).

@param array $miscFields Additional fields appended to the element (a hash array of attributes name => valueOrMiscFields), possibly including 'class'

### $form->checkbox($name, $value, $isChecked, $miscFields)

Outputs a checkbox. The $isChecked boolean controls whether the checkbox is initially checked or not.

### $form->radio($name, $value, $checkedValueOrMiscFields, $miscFields)

Outputs a radio button. The $buttonValue argument controls the valueOrMiscFields of this particular radio button. The second $valueOrMiscFields argument contains the initial valueOrMiscFields we wish to check, in a series of radio buttons.

### $form->file($name, $tagAttribute)

Outputs a file upload field.

### $form->submit($name, $valueOrMiscFields, $miscFields, $additionalClasses)

Outputs an input type="submit".

### $form->button($name, $valueOrMiscFields, $miscFields, $additionalClasses)

Outputs an input type="button".