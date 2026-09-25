# Natas8 Writeup

Here we are faced with yet another page with a `View sourcecode` link.

When inspecting the source code we can see an interesting variable.
```php
$encodedSecret = "3d3d516343746d4d6d6c315669563362";
```
This hints that the secret will be encoded.

## Decoding the secret

There is a function below which can help us understand how the secret is encoded.
```php
function encodeSecret($secret) {
    return bin2hex(strrev(base64_encode($secret)));
}
```

It does the following functions to create the secret.
1. bin2hex - Converts a binary to hexadecimal.
2. strrev - Reverses the string.
3. base64 - encodes an input into base64 format

To crack the secret we can use [Cyberchef](https://cyberchef.org)

We will use this recipe.
`From_Hex('Auto')
Reverse('Character')
From_Base64('A-Za-z0-9+/=',true,false)`

Inputing the $encodedSecret$ returns the decoded secret.

Inputing this on the site will return the key.
