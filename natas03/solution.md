# Natas3 writeup

This comment was found in the source code.
```html
<!-- No more information leaks!! Not even Google will find it this time... -->
```

## Robots.txt

When the comment said 'Not even Google will find it' it made me instantly think about robots.txt .
Robots.txt is used to tell web crawlers which URLs they can access.

Upon visiting robots.txt 
```
http://natas3.natas.labs.overthewire.org/robots.txt
```
we can see some text that says `Disallow: /s3cr3t/`.
This rule tells the crawlers not to visist this directory. For this solution that is where we will be heading.

When we follow the link to
```
http://natas3.natas.labs.overthewire.org/s3cr3t/
```
we can see another user.txt file with the password for natas4

