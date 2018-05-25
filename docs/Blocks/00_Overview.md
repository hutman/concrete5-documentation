## Concepts

### Blocks

Blocks are the smallest presentational unit in concrete5. They are meant to be added to a page, and to consist primarily of visible content.

Each time a block is added to a page, a new Block object is created. This same block object may be aliased to different pages and versions of pages.

### Block Types

Each block has a BlockType object associated with it, which tells the system what type of data it stores. Each block must be of a certain type (e.g. “slideshow,” “content,” “page list,” etc…)

### Block Instance-Specific Data

A combination of these two types of data gives us the block’s instance-specific data. This is information about the particular instance of the block that is only relevant to the block’s type. For example, if you’re dealing with the Youtube video block, it’s instance-specific data is the address of the video you want to display, and its name. Basically, any information displayed a block’s add or edit interface is its instance-specific data.

## Code Locations

All of the necessary block files are contained within one directory, located in one of several places

concrete/blocks/  
packages/some_package/blocks/  
application/blocks/  

The name of the directory that stores the code files in these locations must match that of the block type handle.

### Overrides

Any file in the first two locations above can be overridden by the same file in the third location. This lets sites override presentational and controller logic for custom applications and display, without forking core code bases or packages acquired from the marketplace.