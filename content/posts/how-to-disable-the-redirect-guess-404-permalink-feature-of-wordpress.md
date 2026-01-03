---
date: "2024-10-12T11:19:07+00:00"
title: "How to Disable the “Redirect Guess 404 Permalink” Feature of WordPress"
---

Add the following custom PHP code snippet to your WordPress installation:

```php
<?php
add_filter('do_redirect_guess_404_permalink', '__return_false');
?>
```
