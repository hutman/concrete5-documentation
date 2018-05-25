## Loading The Helper

```
$app = \Concrete\Core\Support\Facade\Application::getFacadeApplication();
$captcha = $app->make('helper/form/captcha');
```

The captcha helper lets you integrate an image-based captcha into your forms, to help prevent spam. Uses the third party SecureImage library.

## Usage

### $captcha->display()

Displays a dynamically generated image, for use with the captcha input text field.

### $captcha->showInput()

Creates the text field for that instance of the captcha. This text input element automatically has the name "ccmCaptchaCode"

### $captcha->check($field = 'ccmCaptchaCode')

Automatically checks the request array for the passed $field. Returns true if the field contains the same text as the current instance of the captcha, false if the captcha has been failed.