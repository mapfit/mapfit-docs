# Get API KEY  (*Discontinued*)
To use certain API's and features, you must register for our service and get an API key which you can add to your app.

## Quick guide to getting a key

### Step 1: Get an API key from Mapfit
Click on the button below, which guides you through the process of signing up for your Mapfit API key. This key can be used throughout any of Mapfit's services. We recommend using one API key per project. 

### Step 2: Add the API key to your application
Add this line of code to the top of your JavaScript file where all your functions for the map are being called.  Substitute `API_KEY` in the code below with the API key you received from step 1. 
###### Javascript
```javascript
mapfit.apikey = \"API_KEY\"
```
###### Swift
``` swift
import Mapfit

@UIApplicationMain
class AppDelegate: UIResponder, UIApplicationDelegate {
    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplicationLaunchOptionsKey: Any]?) -> Bool {
      MFTManager.sharedManager.apiKey = "API_KEY"
      return true
    }
}
```
###### Kotlin
```kotlin
Mapfit.getInstance(this, API_KEY)
```
###### Java
```java
Mapfit.getInstance(this, API_KEY)
```