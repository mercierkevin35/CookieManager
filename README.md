# CookieManager
A simple JS object to manage cookies
CookieManager provides a way to simply manage cookies.

## Create a cookie
To create a cookie whose name is "myCookie" and value is "my cookie value". Process as follows :

```javascript
var manager = new CookieManager(),
    key = "myCookie",
    value = "my cookie value";
manager.setCookie(key, value);
```
If not specified, the cookie expires at the end of the session.
To explicitly specify the expiration delay, process like so :

```javascript
var manager = new CookieManager(),
    key = "myCookie",
    value = "my cookie value",
    expireDays = 7;
manager.setCookie(key, value, expireDays); // this cookie expires in 7 days
```

## Get a cookie value
You can get the value of a particular cookie :\
The getCookies method returns a JS object containing each cookie as attributes\
You can get a specific value like this :

```javascript
var manager = new CookieManager(),
    key = "myCookie",
    value = "my cookie value",
    expireDays = 7;
manager.setCookie(key, value, expireDays); // this cookie expires in 7 days

var myValue = manager.getCookies().myCookie //myValue == "my cookie value"
```
Yo can also specify a key dynamically into brackets like this :

```javascript
var manager = new CookieManager(),
    key = "myCookie",
    value = "my cookie value",
    expireDays = 7;
manager.setCookie(key, value, expireDays); // this cookie expires in 7 days

var myValue = manager.getCookies().myCookie; //myValue == "my cookie value"
var dynamicKey = "myCookie";

var theValue = manager.getCookies()[dynamicKey]; //theValue == "my cookie value"
```

## Update a cookie value
To update a cookie value, just set a cookie with the same key

```javascript
//Create
var manager = new CookieManager(),
    key = "myCookie",
    value = "my cookie value",
    expireDays = 7;
manager.setCookie(key, value, expireDays); // this cookie expires in 7 days

//Read
var myValue = manager.getCookies().myCookie; //myValue == "my cookie value"
var dynamicKey = "myCookie";

var theValue = manager.getCookies()[dynamicKey]; //theValue == "my cookie value"

//Update
manager.setCookie("myCookie", "my new cookie value");
```

## Delete a cookie
To delete a cookie, use the deleteCookie method with the key as argument

```javascript
//Create
var manager = new CookieManager(),
    key = "myCookie",
    value = "my cookie value",
    expireDays = 7;
manager.setCookie(key, value, expireDays); // this cookie expires in 7 days

//Read
var myValue = manager.getCookies().myCookie; //myValue == "my cookie value"
var dynamicKey = "myCookie";

var theValue = manager.getCookies()[dynamicKey]; //theValue == "my cookie value"

//Update
manager.setCookie("myCookie", "my new cookie value");

//Delete
manager.deleteCookie("myCookie");
//myCookie no more exists
```
