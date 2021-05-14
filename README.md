# CookieManager
A simple JS class to manage cookies\
CookieManager provides a way to simply manage cookies.

## Installation
Using npm, run the following command :
```
npm i @mercierkevin35/cookiemanager
```
Then use it in your file
```javascript
import CookieManager from 'cookiemanager';
```

## Create a cookie
To create a cookie whose name is "myCookie" and value is "my cookie value",\
proceed as follows :

```javascript
//Create
const manager = new CookieManager(),
    key = "myCookie",
    value = "my cookie value";
manager.setCookie(key, value);
```
If not specified, the cookie expires at the end of the session.
To explicitly specify the expiration delay, proceed like so :

```javascript
//Create
const manager = new CookieManager(),
    key = "myCookie",
    value = "my cookie value",
    expireDays = 7;
manager.setCookie(key, value, expireDays); // this cookie expires in 7 days
```

## Get a cookie value
The getCookies method returns a JS object containing each cookie as attributes\
You can get a specific value like this :

```javascript
//Create
const manager = new CookieManager(),
    key = "myCookie",
    value = "my cookie value",
    expireDays = 7;
manager.setCookie(key, value, expireDays); // this cookie expires in 7 days

//Read
let myValue = manager.getCookies().myCookie // myValue == "my cookie value"
```
You can also specify a key dynamically into brackets like this :

```javascript
const manager = new CookieManager(),
    key = "myCookie",
    value = "my cookie value",
    expireDays = 7;
manager.setCookie(key, value, expireDays); // this cookie expires in 7 days

//Read
let myValue = manager.getCookies().myCookie; // myValue == "my cookie value"

let dynamicKey = "myCookie";
let theValue = manager.getCookies()[dynamicKey]; // theValue == "my cookie value"
```

## Update a cookie value
To update a cookie value, just set a cookie with the same key

```javascript
//Create
const manager = new CookieManager(),
    key = "myCookie",
    value = "my cookie value",
    expireDays = 7;
manager.setCookie(key, value, expireDays); // this cookie expires in 7 days

//Read
let myValue = manager.getCookies().myCookie; // myValue == "my cookie value"
let dynamicKey = "myCookie";

let theValue = manager.getCookies()[dynamicKey]; // theValue == "my cookie value"

//Update
manager.setCookie("myCookie", "my new cookie value");
```

## Delete a cookie
To delete a cookie, use the deleteCookie method with the key as argument

```javascript
//Create
const manager = new CookieManager(),
    key = "myCookie",
    value = "my cookie value",
    expireDays = 7;
manager.setCookie(key, value, expireDays); // this cookie expires in 7 days

//Read
let myValue = manager.getCookies().myCookie; // myValue == "my cookie value"
let dynamicKey = "myCookie";

let theValue = manager.getCookies()[dynamicKey]; // theValue == "my cookie value"

//Update
manager.setCookie("myCookie", "my new cookie value");

//Delete
manager.deleteCookie("myCookie");
//myCookie no more exists
```
