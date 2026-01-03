---
date: "2024-03-17T16:29:25+00:00"
title: "How to Change Admin URI of Bludit"
---

It is possible to change the admin URI of your _Bludit_ installation.

Open the **bl-kernel/boot/variables.php** file in your preferred text editor with appropriate privileges and edit the following value:

```php
define('ADMIN_URI_FILTER', 'admin');
```

### Example

```php
define('ADMIN_URI_FILTER', 'secret_passage');
```

or:

```php
define('ADMIN_URI_FILTER', 'R3z5cCSpmZTuGB4DjhndM6y9HAPNkgQv');
```

Your new admin URI will be:

- _<https://domain/secret_passage/>_
- _<https://domain/R3z5cCSpmZTuGB4DjhndM6y9HAPNkgQv/>_

---

Say goodbye to bots!
