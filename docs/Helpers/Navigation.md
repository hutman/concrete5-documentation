## Loading the Helper

```
$app = \Concrete\Core\Support\Facade\Application::getFacadeApplication();
$nh = $app->make('helper/navigation');
```

## Methods

### $nh->getCollectionURL($cObj);

@param Page $cObj The page object

Returns the URL of a collection so that it can be clicked on.

### $nh->getLinkToCollection($cObj);

@param Page $cObj The page object

Returns a link to a page. Note: this always returns a string.

### $nh->getTrailToCollection($cObj)

@param Page $cObj The page object

Returns an array of collections as a breadcrumb to the current page

```
$breadcrumb = $nh->getTrailToCollection($c); 
krsort($breadcrumb); 
foreach ($breadcrumb as $bcpage) { 
    echo '' . $bcpage->getCollectionName() . ' > ';
} 
echo $c->getCollectionName();

Returns breadcrumb links: Home > Previous Page > Current Page
```

### $nh->getLogInOutLink()

Returns a string containing an HTML link to either the Login page (if the user is not currently logged in) or the Logout page