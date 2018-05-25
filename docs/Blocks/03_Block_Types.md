From time to time you may find yourself access a BlockType object. Here are the various methods available from that object.

## Load a Block Type Object

### $blockType = \Concrete\Core\Block\BlockType::getByID($id)

### $blockType = \Concrete\Core\Block\BlockType::getByHandle($blockTypeHandle)

Returns a BlockType object given a passed block type ID or handle.

## Methods

### \Concrete\Core\Block\BlockType::installBlockType($btHandle, $pkg)

Installs a block type from a particular package. Useful in a package's install() method.

### $blockType->isCoreBlockType()

Returns true if the block type ships with concrete5.

### $blockType->getPackageID()

Returns the package ID of the block type, or zero if the block type ships with concrete5 or is custom.

### $blockType->getPackageHandle()

Returns the package handle of the block type, or null if the block type ships with concrete5 or is custom.

### $blockType->getCount()

Returns the number of unique instances of this block type.

### $blockType->getBlockTypeDescription()

Returns the description of the block type.

### $blockType->getBlockTypeInterfaceWidth()

Returns the width that the block thinks it needs to be, when adding or editing.

### $blockType-> getBlockTypeInterfaceHeight()

Returns the height that the block thinks it needs to be, when adding or editing.

### $blockType->getBlockTypeCustomTemplates()

Returns an array of custom templates. Checks the core block type directory, the local overrides directory, and any packages to see if they specify custom templates for this block type.

### $controller = $blockType->getController()

Returns the extended BlockController for the particular BlockType object.

### $blockType->getBlockTypePath()

Returns a path to where the block type's files are located.

### $blockType->inc($file, $args = array())

Extracts all items passed through $args, and then includes the file from either the local directory or the core directory.

### $blockType->delete()

Deletes the block type. Only removes the block type from the BlockTypes table, not any of the information in the other tables.

### $blockType->refresh()

Refreshes the block type's database schema (stored in db.xml).

### $blockType->render($view)

Renders a particular view of a block type, using the public $controller variable as the block type's controller

## Embedding Blocks in a Page Template

There are times when you might want to use a block's functionality within a page without having that block editable through the CMS. You can render a block with parameters as though it were added through the CMS by coding it directly into a page template.

### Example 1: Hard-Coding Tags Block

```
$bt = \Concrete\Core\Block\BlockType::getByHandle('tags');
$c = \Concrete\Core\Page\Page::getByID('/path/to/target/page');
$bt->controller->set('title', t('Tags'));
$bt->controller->set('target', $c);
$bt->render();
```

### Example 2: Hard-Coding Auto-Nav Block with Custom Template

Render a breadcrumb navigation using the Auto-Nav block with certain options, and the built-in Breadcrumb Auto-Nav custom tempate.

```
$bt = \Concrete\Core\Block\BlockType::getByHandle('autonav');
$bt->controller->orderBy = 'display_asc';
$bt->controller->displayPages = 'top';
$bt->controller->displaySubPages = 'relevant_breadcrumb';
$bt->controller->displaySubPageLevels = 'all';
$bt->render('templates/breadcrumb');
```