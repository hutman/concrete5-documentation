## Loading the Helper

```
$app = \Concrete\Core\Support\Facade\Application::getFacadeApplication();
$mh = $app->make('helper/mail');
```

## Plain Text Example

```
$mh->setSubject('Plain Text Message');
$mh->from('noreply@domain.com');
$mh->replyto('noreply@domain.com');
$mh->to('email@domain.com', 'To Name');
$mh->cc('email@domain.com', 'To Name');
$mh->bcc('email@domain.com', 'To Name');
$mh->setBody('This is my simple message body.');
$mh->sendMail();
```

## HTML Example

```
$mh->setSubject('Plain Text Message');
$mh->from('noreply@domain.com');
$mh->replyto('noreply@domain.com');
$mh->to('email@domain.com', 'To Name');
$mh->cc('email@domain.com', 'To Name');
$mh->bcc('email@domain.com', 'To Name');
$mh->setBodyHTML('<p>This is my simple message body.</p>');
$mh->sendMail();
```

## Loading email content from an external template.

You may load email content from a template, which will need to be located in the local mail/ directory. These templates are simply a collection of PHP variables like $body, $subject, and $from. Additional PHP variables can be specified within these variables and then passed through the MailHelper::addParameter method.

### Template

```
$subject = t("Template Message");
$body = t("

Dear %s,

Your email is: %s

Thanks!

", $uName, $uEmail);

$mh->from('noreply@domain.com');
$mh->replyto('noreply@domain.com');
$mh->to('email@domain.com', 'To Name');
$mh->cc('email@domain.com', 'To Name');
$mh->bcc('email@domain.com', 'To Name');
$mh->addParameter('uName', 'username');
$mh->addParameter('uEmail', 'email@domain.com');
$mh->load('template_name');
$mh->sendMail();
```

## Methods

### $mh->reset()

Clean up the instance of this object (reset the class scope variables).

### $mh->addParameter(string $key, mixed $val)

Adds a parameter for the mail template.

### $mh->addAttachment(Concrete\Core\Entity\File\File $file)

Add a File entity as an attachment of the message.

### $mh->addAttachmentWithHeaders(Concrete\Core\Entity\File\File $file, array $headers)

@param array $headers Additional headers fo the MIME part. Valid values are: - filename: The name to give to the attachment (it will be used as the filename part of the Content-Disposition header) [default: the filename of the File instance] - mimetype: the main value of the Content-Type header [default: the content type of the file] - disposition: the main value of the Content-Disposition header [default: attachment] - encoding: the value of the Content-Transfer-Encoding header [default: base64] - charset: the charset value of the Content-Type header - boundary: the boundary value of the Content-Type header - id: the value of the Content-ID header (without angular brackets) - description: the value of the Content-Description header - location: the value of the Content-Location header - language: the value of the Content-Language header

Add a File entity as an attachment of the message, specifying the headers of the mail MIME part.

### $mh->addRawAttachment(string $content, string $filename, string $mimetype = 'application/octet-stream')

Add a mail attachment by specifying its raw binary data.

### $mh->addRawAttachmentWithHeaders(string $content, string $filename, array $headers = [])

Add a mail attachment by specifying its raw binary data, specifying the headers of the mail MIME part.

### $mh->load(string $template, string|null $pkgHandle = null)

Load an email template from the /mail/ directory.

### $mh->setBody(string|false $body)

Manually set the plain text body of a mail message (typically the body is set in the template + load method).

### $mh->setSubject(string $subject)

Manually set the message's subject (typically the body is set in the template + load method).

### $mh->setBodyHTML(string|false $html)

Manually set the HTML body of a mail message (typically the body is set in the template + load method).

### $mh->from(string $email, string|null $name = null)

Set the from address on the message.

### $mh->to(string $email, string|null $name = null)

Add one or more "To" recipients to the message.

### $mh->cc(string $email, string|null $name = null)

Add one or more "CC" recipients to the message.

### $mh->bcc(string $email, string|null $name = null)

Add one or more "BCC" recipients to the message.

### $mh->replyto(string $email, string|null $name = null)

Sets the Reply-To addresses of the message.

### $mh->setTesting(bool $testing)

Set the testing state (if true the email logging never occurs and sending errors will throw an exception).

### $mh->setAdditionalHeaders(array $headers)

Set additional message headers.

### $mh->sendMail(bool $resetData = true)

Sends the email.