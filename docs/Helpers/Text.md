## Loading the Helper

```
$app = \Concrete\Core\Support\Facade\Application::getFacadeApplication();
$th = $app->make('helper/text');
```

## Methods

### $th->encodePath(string $path);

URL-encodes collection path.

### $th->match(string $pattern, string $value);

Determine if a given string matches a given pattern.

### $th->slugSafeString(string $handle, int $maxlength = 128);

Remove unsafe characters for URL slug.

### $th->sanitize(string $string, int $max_length, string $allowed = '');

Strips tags and optionally reduces string to specified length.

### $th->email(string $email);

Leaves only characters that are valid in email addresses (RFC).

### $th->alphanum(string $string);

Leaves only characters that are alpha-numeric.

### $th->entities(string $v);

Always use in place of htmlentites(), so it works with different languages.

### $th->decodeEntities(string $v);

Decodes html-encoded entities (for instance: from '>' to '>').

### $th->specialchars($v)

A concrete5 specific version of htmlspecialchars(). Double encoding is OFF, and the character set is set to your site's.

### $th->shorten(string $textStr, int $numChars = 255, string $tail = '…')

An alias for shorten().

### $th->shortText(string $textStr, int $numChars = 255, string $tail = '…')

Like sanitize, but requiring a certain number characters, and assuming a tail.

### $th->camelcase(string $string)

Takes a string and turns it into the CamelCase or StudlyCaps version.

### $th->twitterAutolink(string $input, int $newWindow, int $withSearch)

Automatically add hyperlinks to any twitter style @usernames in a string.

### $th->makenice(string $input)

Runs a number of text functions, including autolink, nl2br, strip_tags. Assumes that you want simple text comments but with a few niceties.

### $th->prettyStripTags($input, $allowedTags = null)

Runs strip_tags but ensures that spaces are kept between the stripped tags.

### $th->autolink(string $input, bool $newWindow = false, string $defaultProtocol = 'http://')

Scans passed text and automatically hyperlinks any URL inside it.

### $th->fnmatch(string $pattern, string $string)

A wrapper for PHP's fnmatch() function, which some installations don't have.

### $th->uncamelcase(string $string)

Takes a CamelCase string and turns it into camel_case.

### $th->unhandle(string $string)

Takes a handle-based string like "blah_blah" or "blah-blah" or "blah/blah" and turns it into "Blah Blah".

### $th->handle($handle, bool $leaveSlashes = false)

Takes a string and turns it into a handle.

### $th->sanitizeFileSystem(string $handle)

Takes text and returns it in the "lowercase_and_underscored_with_no_punctuation" format. Tries to be sensible about internationalized characters, converting umlauts, etc…

### $th->urlify(string $handle, int $max_length = null, string $locale = '', bool $removeExcludedWords = true)

Takes text and returns it in the "lowercase-and-dashed-with-no-punctuation" format.

### $th->asciify(string $text, string $locale = '')

Takes text and converts it to an ASCII-only string (characters with code between 32 and 127, plus \t, \n and \r).

### $th->wordSafeShortText(string $textStr, int $numChars = 255, string $tail = '…')

alias of shortenTextWord().

### $th->shortenTextWord($textStr, int $numChars = 255, string $tail = '…')

Shortens and sanitizes a string but only cuts at word boundaries.

### $th->filterNonAlphaNum(string $val)

Strips out non-alpha-numeric characters.

### $th->highlightSearch(string $value, string $searchString)

Highlights a string within a string with the class ccm-highlight-search.

### $th->formatXML($xml)

Formats a passed XML string nicely.