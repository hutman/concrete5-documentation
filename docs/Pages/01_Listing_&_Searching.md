The PageList class provides an object-oriented way to search pages.

```
use Concrete\Core\Page\PageList;

$list = new PageList;
```

## Basic Example Getting All Results
```
$list = new \Concrete\Core\Page\PageList();
$pages = $list->getResults();
```

## Basic Example with Pagination
```
$list = new \Concrete\Core\Page\PageList();
$pagination = $list->getPagination();
$pagination->setMaxPerPage(10)->setCurrentPage(2);
$results = $pagination->getCurrentPageResults();
```

## Debug Methods

### $list->debug()

### $list->debugStart()

### $list->debugStop()

## Filtering Methods

### $list->filterByParentID(array $cParentID)

Filters pages by the parent ID of a given page.

### $list->filterByPageTypeHandle(mixed $ptHandle)

Filters by page type handles. $ctHandle can also be an array of page type handles.

### $list->filterByPageTemplate(Template $template)

### $list->filterByAttribute($handle, $value, $comparison = '=')

Filters by attribute.

### $list->filterByPublicDate($date, $comparison = '=')

### $list->filterByDateAdded($date, $comparison = '=')

### $list->filterByDateLastModified($date, string $comparison = '=')

### $list->filterByNumberOfChildren($number, string $comparison = '>')

### $list->filterByKeywords($keywords)

Filtering by keywords performs a simple LIKE query against the name, description or text content of a page, as well as the textual representation of any page attributes that have been marked as "included in search index".

### $list->filterByFulltextKeywords($keywords)

Filters files by keywords, which searches:

Name, Description, Indexed Content against MySQL fulltext functions

Any collection attributes marked as being included in the search index

### $list->filterByPackage(Package $package)

### $list->filterBySite(Site $site)

### $list->includeSystemPages()

Instructs the page list to include system pages (e.g. the dashboard).

### $list->ignorePermissions()

When called, this will instruct the PageList query that you don't want to check the permissions of the logged-in user. This may result in the page list including pages that user cannot view.

### $list->includeAliases()

Instructs the page list to ignore aliased pages.

## Sorting Methods

### $list->sortByDisplayOrder()

Sorts this list by display order.

### $list->sortByDisplayOrderDescending()

Sorts this list by display order descending.

### $list->sortByDateModified()

Sorts this list by date modified ascending.

### $list->sortByDateModifiedDescending()

Sorts this list by date modified descending.

### $list->sortByCollectionIDAscending()

Sorts by ID in ascending order.

### $list->sortByPublicDate()

Sorts this list by public date ascending order.

### $list->sortByName()

Sorts by name in ascending order.

### $list->sortByNameDescending()

Sorts by name in descending order.

### $list->sortByPublicDateDescending()

Sorts this list by public date descending order.

### $list->sortByRelevance()

Sorts by fulltext relevance (requires that the query be fulltext-based.

### $list->sortBy($field, $direction = 'asc')

### $list->executeSortBy($column, $direction = 'asc')

### $list->sortBySearchColumn(Column $column, $direction = null)

## Getting Results

### $list->setItemsPerPage($itemsPerPage)

### $list->getTotalResults()

### $list->getResults()

Once you have filtered your PageList object, getResults() will return all matching pages.

### $list->getResult($queryRow)

## Pagination

### $pagination = $list->getPagination();

### $pagination->setMaxPerPage($itemsPerPage);

### $pagination->setCurrentPage($pageNumber);

### $pagination->getTotalResults();

To get the total number of results

### $pagination->getTotalPages();

To get the total number of pages

### $pagination->hasNextPage();
### $pagination->hasPreviousPage();

To determine whether paging is necessary

### $pagination->renderDefaultView();

Several common pagination styles are built-in, including Bootstrap 2, Bootstrap 3, Basic Pagination, and Concrete5's default styling (which is heavily Bootstrap 3 inspired).

### $results = $pagination->getCurrentPageResults();