
# CPH ZOO Consumer App tracking requirement document

[**1. Table of content**](#members-&-user-permissions)<br/>
[2 Introduction](#introduction)<br/>
[2 Screen naming](#screen-naming)<br/>
[3 Log in](#log-in)<br/>

## Introduction
The following guide provide documentation for automatically collected events and will outline custom tracking specifications for the CPH ZOO App

Google documentation on automatically collected events
https://support.google.com/analytics/answer/9234069?hl=en

## Screen naming
Add a unique screen name for each app screen. 

![image](https://github.com/RasmusEge/ZOO-APP-Tracking-Implementation/assets/93127486/6d831703-7663-43b7-a42e-78b48018d5e6)


## Web view

When a user opens webview from app:

![image](https://github.com/RasmusEge/ZOO-APP-Tracking-Implementation/assets/93127486/200f5942-e931-480b-a99e-96c6a815c4fa)

````javascript
window.datalayer.push({
  "event": "webViewInApp",
  "App":"true" 
});
````


### Log in
Whenever a user logs in:

![image](https://github.com/RasmusEge/ZOO-APP-Tracking-Implementation/assets/93127486/4a8a4119-f226-4ac1-b908-912665ece561)

```swift
Analytics.logEvent("login", parameters: [
 "method" : "{{INSERT METHOD}}" // if relevant - e.g. email, Google
 "procedure": "{{INSERT PROCEDURE }}" // i.e. refresh/auto log-in or prompt via screen
 "successfulLogin": "{{INSERT LOGIN RESULT}}" //true or false
 "user_id": "{{INSERT USER ID}}"
])
```

### Add zoo card
Whenever a user clicks on "Tilføj zookort" (Add zoo card):

![image](https://github.com/RasmusEge/ZOO-APP-Tracking-Implementation/assets/93127486/8650f248-6c60-456e-ae2e-b96c34874b86)

```swift
Analytics.logEvent("add_zoo_card")
```

### Remove zoo card
Whenever a user clicks on ""Ja, fjern" (Yes, remove):

![image](https://github.com/RasmusEge/ZOO-APP-Tracking-Implementation/assets/93127486/fe585856-3790-4e44-a0e3-daad3bc1675e)

```swift
Analytics.logEvent("remove_zoo_card")
```



### Create account
Whenever a user clicks on ""Bekræft" (Confirm), when they are creating a new password:

![image](https://github.com/RasmusEge/ZOO-APP-Tracking-Implementation/assets/93127486/774d7dff-ebd6-4738-9f03-eeb23dc2f746)

```swift
Analytics.logEvent("create_account")
```

### Navigation click

Whenever user clicks on one of the navigation points:

![image](https://github.com/RasmusEge/ZOO-APP-Tracking-Implementation/assets/93127486/6a3cc27d-0ee8-4d35-971c-0f90f9b2fc64)

```swift
Analytics.logEvent("navigation", parameters: [
 "category" : "{{INSERT CATEGORY}" // "Oplev", "Kort", "Mit ZOO", "Køb" and "Indstillinger". 
])
```
