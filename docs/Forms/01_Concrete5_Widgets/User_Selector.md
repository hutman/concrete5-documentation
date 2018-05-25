## Loading The Helper

Provides an interface for selecting a single or multiple users. Saves to a hidden form element.

```
$app = \Concrete\Core\Support\Facade\Application::getFacadeApplication();
$uh = $app->make('helper/form/user_selector');
```

## Usage

### $uh->selectUser($fieldName, $uID = false);

@param string $fieldName - the field name  
@param bool|int $uID -  the ID of the user to be initially selected  

Build the HTML to be placed in a page to choose a user using a popup dialog.

### $uh->quickSelect($fieldName, $uID = false, $miscFields = []);

@param string $fieldName - the name of the field  
@param int|false $uID - the ID of the user to be initially selected  
@param array $miscFields - additional fields appended to the hidden input element (a hash array of attributes name => value), possibly including 'class'  

Build the HTML to be placed in a page to choose a user using a select with users pupulated dynamically with ajax requests.

### $uh->selectMultipleUsers($field, $pages = array(), $startingPoint = 'HOME_CID', $filters = array());

@param string $field - the field name  
@param array $pages - an array of IDs of the already selected pages  
@param int $startingPoint - page ID of the parent page for displaying the sitemap  
@param array $filters - ??? Not sure what can go in here

Build the HTML to be placed in a page to choose multiple users using a popup dialog.