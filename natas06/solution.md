# Natas6 writeup

Upon entering the site there is a button saying 'View sourcecode'.

Click the button and inspect the code.

```js
include "includes/secret.inc";

    if(array_key_exists("submit", $_POST)) {
        if($secret == $_POST['secret']) {
        print "Access granted. The password for natas7 is <censored>";
    } else {
        print "Wrong secret";
    }
    }  
```
We can see that it includes a file secret.inc and compares the users input to the secret.
Navigating to `http://natas6.natas.labs.overthewire.org/includes/secret.inc`

`<?
$secret = "FOEIUWGHFEEUHOFUOIU";
?>`

By copying the seceret and entering it in the box on the main page it returns the key.
