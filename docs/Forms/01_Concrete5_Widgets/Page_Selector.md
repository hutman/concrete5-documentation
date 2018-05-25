## Loading The Helper

Provides an easy way to select a page from a combination sitemap/search form. Saves a numeric page ID to a hidden form element.

```
$app = \Concrete\Core\Support\Facade\Application::getFacadeApplication();
$pageSelector = $app->make('helper/form/page_selector');
```

## Usage

### $pageSelector->selectPage($fieldName, $cID = false);

@param string $fieldName The field name  
@param bool|int $cID The ID of the already selected page 

Creates form fields and JavaScript page chooser for choosing a page. For use with inclusion in blocks.

### $pageSelector->selectMultipleFromSitemap($field, $pages = array(), $startingPoint = 'HOME_CID', $filters = array());

@param string $field The field name  
@param array $pages An array of IDs of the already selected pages  
@param int $startingPoint Page ID of the parent page for displaying the sitemap  
@param array $filters - ??? Not sure what can go in here  