## Getting the current page

Throughout your code, if you wish to grab the object for the currently rendered page, simply execute this code:

```
$page = \Concrete\Core\Page\Page::getCurrentPage();
```
This will return the currently rendered page's object.

## Getting a Page Object by ID

```
$page = \Concrete\Core\Page\Page::getByID($pageID);
```

Returns the current page based on its id.

## Getting a Page Object by Path

```
$page = \Concrete\Core\Page\Page::getByPath('/path/to/page');
```

Returns the current page based on its path.

## Methods

### $page->getCollectionID()

Returns the id for the current page.

### $page->getCollectionHandle()

Returns the page's handle.

### $page->getCollectionName()

Returns the page's name.

### $page->getCollectionDatePublic()

Gets the date a the current version was made public, date formated like: 2009-01-01 00:00:00

### $page->getCollectionDatePublicObject()

Returns the \DateTime instance (or null if the current version doesn't have public date)

### $page->getAttribute(string|CollectionKey $akHandle, string|false $displayMode = false)

Return the value of the attribute with the handle $akHandle of the currently loaded version (if it's loaded).

### $page->getAttributeValueObject($akHandle, $createIfNotExists = false)

Return the attribute value object with the handle $akHandle of the currently loaded version (if it's loaded).

### $page->getCollectionPath()

Returns the path for the current page.

### $page->getCollectionLink($appendBaseURL = false)

Returns full url for the current page.

### $page->getCollectionDescription()

Get the description of a page.

### $page->getPageTypeID()

Returns the Collection Type ID.

### $page->getPageTypeHandle()

Returns the Collection Type handle.

### $page->getPageTemplateID()

Returns the Page Template ID.

### $page->getPageTemplateHandle()

Returns the Page Template handle.

### $page->getCollectionThemeID()

Returns theme id for the collection.

### $page->getJSONObject()

Return a representation of the Page object as something easily serializable.

### $page->isEditMode()

Is the page in edit mode.

### $page->isExternalLink()

Checks if a page is an external link.

### $page->getCollectionParentID()

Get the Parent cID from a page by using a cID.

### $page->getNumChildren()

### $page->getNumChildrenDirect()

### $page->getFirstChild(string $sortColumn = 'cDisplayOrder asc')

Returns the first child of the current page, or null if there is no child.

### $page->getCollectionChildrenArray($oneLevelOnly)

### $page->getCollectionChildren()

Returns the immediate children of the current page.

### $page->addBlock(BlockType $bt, Area $a, array $data)

Adds a block to the page.

### $page->getBlocks(string|false $arHandle = false)

List the blocks in the currently loaded collection version (or in a specific area within it).

### $page->add($pt, $data, $template = false)

Adds a new page of a certain type, using a passed associate array to setup value. $data may contain any or all of the following: "uID": User ID of the page's owner "pkgID": Package ID the page belongs to "cName": The name of the page "cHandle": The handle of the page as used in the path "cDatePublic": The date assigned to the page.

### $page->delete()

### $page->moveToTrash()