
# temp-mail.ru
Node.js wrapper for temp-mail.ru api.

## Install

```sh
$ npm install temp-mail.ru --save
```

## How to

TypeScript:
```ts
import TempMail from "temp-mail.ru";
TempMail.randomFreeEmail().subscribe((mailName) => {
    console.log(mailName);
});
```

JavaScript:
```js
var TempMail = require("temp-mail.ru").default;
TempMail.randomFreeEmail().subscribe(function(mailName) {
    console.log(mailName);
});
```

# API Reference
    
* [pichuser](#module_pichuser)
    * [~TempMail](#module_pichuser..TempMail)
        * [.domains()](#module_pichuser..TempMail.domains) ⇒ <code>Observable.&lt;Array.&lt;string&gt;&gt;</code>
        * [.mails(mailName)](#module_pichuser..TempMail.mails) ⇒ <code>Observable.&lt;Array.&lt;module:pichuser~MailObject&gt;&gt;</code>
        * [.mailsCount(mailName)](#module_pichuser..TempMail.mailsCount) ⇒ <code>Observable.&lt;number&gt;</code>
        * [.randomFreeEmail()](#module_pichuser..TempMail.randomFreeEmail) ⇒ <code>Observable.&lt;string&gt;</code>
        * [.deleteMail(id)](#module_pichuser..TempMail.deleteMail) ⇒ <code>Observable.&lt;boolean&gt;</code>
        * [.waitForMail(mailName, timeout)](#module_pichuser..TempMail.waitForMail) ⇒ <code>Observable.&lt;module:pichuser~MailObject&gt;</code>

<a name="module_pichuser..TempMail"></a>

### pichuser~TempMail
**Kind**: inner class of <code>[pichuser](#module_pichuser)</code>  

* [~TempMail](#module_pichuser..TempMail)
    * [.domains()](#module_pichuser..TempMail.domains) ⇒ <code>Observable.&lt;Array.&lt;string&gt;&gt;</code>
    * [.mails(mailName)](#module_pichuser..TempMail.mails) ⇒ <code>Observable.&lt;Array.&lt;module:pichuser~MailObject&gt;&gt;</code>
    * [.mailsCount(mailName)](#module_pichuser..TempMail.mailsCount) ⇒ <code>Observable.&lt;number&gt;</code>
    * [.randomFreeEmail()](#module_pichuser..TempMail.randomFreeEmail) ⇒ <code>Observable.&lt;string&gt;</code>
    * [.deleteMail(id)](#module_pichuser..TempMail.deleteMail) ⇒ <code>Observable.&lt;boolean&gt;</code>
    * [.waitForMail(mailName, timeout)](#module_pichuser..TempMail.waitForMail) ⇒ <code>Observable.&lt;module:pichuser~MailObject&gt;</code>

<a name="module_pichuser..TempMail.domains"></a>

#### TempMail.domains() ⇒ <code>Observable.&lt;Array.&lt;string&gt;&gt;</code>
Get all available domains

**Kind**: static method of <code>[TempMail](#module_pichuser..TempMail)</code>  
**Example**  
```js
     TempMail.domains().subscribe((domains) => {
            console.log(domains);
        });
```
<a name="module_pichuser..TempMail.mails"></a>

#### TempMail.mails(mailName) ⇒ <code>Observable.&lt;Array.&lt;module:pichuser~MailObject&gt;&gt;</code>
Get all emails by mail name

**Kind**: static method of <code>[TempMail](#module_pichuser..TempMail)</code>  

| Param | Type | Description |
| --- | --- | --- |
| mailName | <code>string</code> | email on temp-mail.ru |

**Example**  
```js
     TempMail.mails('test@tempmail.domain')
        .subscribe((mails) => {
            console.log(mails);
        });
```
<a name="module_pichuser..TempMail.mailsCount"></a>

#### TempMail.mailsCount(mailName) ⇒ <code>Observable.&lt;number&gt;</code>
Return count of mails in box

**Kind**: static method of <code>[TempMail](#module_pichuser..TempMail)</code>  

| Param | Type | Description |
| --- | --- | --- |
| mailName | <code>string</code> | email on temp-mail.ru |

**Example**  
```js
     TempMail.mails('test@tempmail.domain')
     .subscribe((count) => {
        console.log(count);
    });
```
<a name="module_pichuser..TempMail.randomFreeEmail"></a>

#### TempMail.randomFreeEmail() ⇒ <code>Observable.&lt;string&gt;</code>
Return first random email without inbox letters

**Kind**: static method of <code>[TempMail](#module_pichuser..TempMail)</code>  
**Example**  
```js
     TempMail.randomFreeEmail().subscribe((mailName) => {
        console.log(mailName);
    });
```
<a name="module_pichuser..TempMail.deleteMail"></a>

#### TempMail.deleteMail(id) ⇒ <code>Observable.&lt;boolean&gt;</code>
Delete email by id

**Kind**: static method of <code>[TempMail](#module_pichuser..TempMail)</code>  

| Param | Type | Description |
| --- | --- | --- |
| id | <code>string</code> | system hash of mail. |

**Example**  
```js
     TempMail.deleteMail('hashid').subscribe((success) => {
        console.log(success ? "deleted" : "can\'t delete");
    });
```
<a name="module_pichuser..TempMail.waitForMail"></a>

#### TempMail.waitForMail(mailName, timeout) ⇒ <code>Observable.&lt;module:pichuser~MailObject&gt;</code>
Return first available letter

**Kind**: static method of <code>[TempMail](#module_pichuser..TempMail)</code>  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| mailName | <code>string</code> |  | email on temp-mail.ru |
| timeout | <code>number</code> | <code></code> | timeout in seconds |

**Example**  
```js
     TempMail.waitForMail('test@tempmail.domain', 10)
     .subscribe((mail) => {
        console.log(mail);
    }, (error) => {
        alert("Mailbox still empty")
    });
```

* * *

## License

MIT