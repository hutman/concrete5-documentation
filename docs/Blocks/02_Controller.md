A block's controller can contain the following properties and methods.

## Properties

### $btTable (required)

This is the core block type table that you are saving data into.

### $btExportTables

If your block uses more than one table. This is an array of tables that are connected to this block, this is used for the duplicate function.

### $btInterfaceWidth (default 400)
### $btInterfaceHeight (default 400)

These variables define, in pixels, the width and height of your block's window when added or edited.

### $btSupportsInlineAdd (default false)
### $btSupportsInlineEdit (default false)

These variables can be set to true if this block supports inline add/edit functionality (like the Content block).

### $btDefaultSet

This variable can be set to defind the Block Set this Block Type should display in.  If none is defined it will display in the "Other" Set.

### $btCacheBlockRecord (default true)

Allow the block record to be cached.

### $btCacheBlockOutput (default false)

Allow the block output to be cached.

### $btCacheBlockOutputLifetime (default 0)

Time, in minutes, to cache the block's output.

### $btCacheBlockOutputOnPost (default false)

Allow the block output to be cached after post.

### $btCacheBlockOutputForRegisteredUsers

Allow the block output to be cached for Registered Users.

### $btIgnorePageThemeGridFrameworkContainer (default false)

Define if this block should always ignore the area's grid framework container.

### $helpers (default ['form'])

If your block needs helpers, this is an array of helpers to be included.

### $supportSavingNullValues (default false)

Set this to true if the data sent to the save/performSave methods can contain NULL values that should be persisted.

## Methods

### getBlockTypeName()

Returns the name of the block's type.

### getBlockTypeDescription()

Returns the description of the block type.

### on_start()

Fires automatically when a block is interacted with. If you're thinking of putting something in the block's "__construct()" method, use this instead. It is run only when necessary and is less likely to be a performance drain.

### on_page_view()

This function is automatically run when the block is viewed from within a page.

### add()

This function is automatically run when the block is placed in add mode.

### edit()

This function is automatically run when the block is edited.

### validate()

This function is automatically run when the block is submitted to be saved and can return validation errors if needed.

### save($args)

$args is an associated array, and is usually filled with the contents of the $_POST array (when either added or saved.) The BlockController save() method will actually rarely need to be overridden, as it inspects the columns of the block's core database table and looks through the $_POST to find matching columns, and saves data automatically.

### registerViewAssets($outputContent = '')

This function is automatically run when the block is viewed and can be used to include assets for the view.

### view()

This function is automatically run when the block is viewed.

### set($key, $value)

Takes a string $key and a mixed $value, and makes a variable of that name available from within a block's view, add or edit template. This is typically used within the add(), edit() or view() function.

### render($view)

Renders a view that's in the block's folder. Does not require .php on the end of the filename.

### duplicate($newBlockID)

Run automatically when a block is duplicated. This most likely happens when a block that is in an approved version is updated. A block controller may override this function to provide specific duplicate-only functionality.

### delete()

Automatically run when a block is deleted. This removes the special data from the block's specific database table. If a block needs to do more than this this method should be overridden.