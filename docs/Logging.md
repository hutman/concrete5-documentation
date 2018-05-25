In concrete5, logging something so that it appears in the Dashboard can be as simple as a single line.

```
\Log::addInfo('This is an informative message');
\Log::addWarning('Uh oh.');
\Log::addAlert('Red alert!');
Log::addDebug('This is a debug level.');
```

This is using the Log facade, which is a static class in the root namespace that automatically instantiates the Concrete\Core\Logging\Logger class with its dependencies. If you import the Log class at the top of your file, you don't have to use the backslash:

## Severity

concrete5's logger implements PSR-3, and is built on the Monolog library. That means it supports the following severities (which are listed here in escalating order.)

- Debug
- Info
- Notice
- Warning
- Error
- Critical
- Alert
- Emergency

To log a message with a particular severity, simply call Log::addSeverity, concrete5 makes it easy to search by severity in the Dashboard.

## Logging Objects

Need to log an object using the logger? You'll need to change it into a string first. Here's an example of logging the data about Concrete\Core\User\UserInfo object:

```
$ui = \UserInfo::getByID(1);
\Log::addInfo('Information about the admin user: ' . var_dump_safe($ui, $false));
```

Why var_dump_safe? Some objects in concrete5 are built from Doctrine ORM, which is a library that makes it easy to work with database data. These objects are extremely large; if you attempt to run a normal var_dump or print_r on them, they will die and possibly crash your PHP session. Instead, use the concrete5-specific var_dump_safe method, with the $echo argument (the second argument) set to false.