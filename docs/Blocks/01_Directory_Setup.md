A block's directory can contain the following items.

## A Database Definition

### db.xml

This is a file named db.xml, in the [Doctrine XML Format](https://documentation.concrete5.org/developers/packages/custom-database-tables-in-packages/db-xml-doctrine-xml-format).

This file describes the schema of the block in a way that can be easily read and understood.

The schema can also be altered later and refreshed through the dashboard or a package update if the block is installed using a package.

Multiple tables can contained within this file. The only requirement for the table is that the core block type table must contain a column named bID, which is an unsigned integer.

## An Icon

### icon.png

A block's icon is displayed in the Add Block window. This is a 50x50 PNG named "icon.png".

## Controller

### controller.php

This file extends the BlockController object. You can learn more about this file in the [Controller](01_Blocks/01_Controller) section of the Blocks Documentation

## Core Templates

### add.php

This file is rendered when the block is added.

### edit.php

This file is rendered when the block is edited.

### view.php

This file is rendered when the block is viewed in a page.

### composer.php (optional)

An optional file that is rendered when the block is displayed within the composer view.

## Stylesheet

### view.css

Block specific styles, will be included on every page that this block is added to.