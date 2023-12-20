
# CPH ZOO Consumer App tracking requirement document

[**3. Table of content**](#members-&-user-permissions)<br/>
[3.1 Log in (complete)](#log-in)<br/>

## Introduction
The following guide provide documentation for automatically collected events and will outline custom tracking specifications for the CPH ZOO App

Google documentation on automatically collected events
https://support.google.com/analytics/answer/9234069?hl=en



### Log in

Whenever a user logs in:

```swift
Analytics.logEvent("login", parameters: [
 "method" : "{{INSERT METHOD}}" // if relevant - e.g. email, Google
 "procedure": "{{INSERT PROCEDURE }}" // i.e. refresh/auto log-in or prompt via screen
 "successfulLogin": "{{INSERT LOGIN RESULT}}" //true or false
 "user_id": "{{INSERT USER ID}}"
])
```



