# [Day 1] `Web Exploitation` A Christmas Crisis

Deploy the box and open the IP Address of it in the browser

We are presented with a register/ login form.

![web_form](img/01.png)

Register a new user:
I am gonna create one with the username: `Elfo7` and password: `foobar`

![register](img/register.png)

Afterwards we can login with our username and password

![loggedin](img/loggedin.png)

All controls are inactive... Let's do something about that.


Open up the Developer Tools, press `F12` or `Ctrl+Shift+I` and navigate to the
`storage` tab (Application tab in Chrome/Edge).
We can see a cookie with the name of `auth` and a base16 aka hex encoded value.

![cookie](img/cookie.png)

Copy the value of the auth cookie and paste it into the input field on [CyberChef FromHex](https://gchq.github.io/CyberChef/#recipe=From_Hex('Auto'))
The output will be json object.

![decrypted_cookie](img/decrypted.png)

We can now copy the json object and copy it into the input field on [CyberChef ToHex](https://gchq.github.io/CyberChef/#recipe=To_Hex('None',0))
and change the username to 'santa'. CyberChef will encode the json into hex for us.

![encode_cookie](img/encode.png)

Copy the hex string and replace the value of the auth cookie with it and reload the page.
Finally we are able to active all the controls and capture the THM-flag

![flag](img/flag.png)