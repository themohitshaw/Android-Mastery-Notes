# Project: 06 WebView(Mohitverse)

## Project Repository

**GitHub Project:**

```text
https://github.com/themohitshaw/Android-Mastery/tree/main/06%20MohitVerse
```



---

# Project Information

- **Project Number:** 06
- **Project Name:** WebView
- **Technology:** Kotlin, XML
- **IDE:** Android Studio

---

# Objective

This project demonstrates how to use **WebView** in Android.

A **WebView** is a UI component that allows an Android application to display web pages directly inside the app without opening an external browser.

In this project:

- A WebView is added to the layout.
- JavaScript is enabled.
- DOM Storage is enabled.
- Images are loaded automatically.
- Safe Browsing is enabled.
- The website **https://mohitkumarshaw.netlify.app** opens inside the application.
- The Back button navigates to the previous webpage if available.

---

# Complete Code

## MainActivity.kt

```kotlin
package com.example.webview

import android.os.Build
import android.os.Bundle
import android.webkit.WebView
import android.webkit.WebViewClient
import androidx.activity.addCallback
import androidx.annotation.RequiresApi
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {

    private lateinit var webViewVariable: WebView

    @RequiresApi(Build.VERSION_CODES.O)
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        setContentView(R.layout.activity_main)

        webViewVariable = findViewById(R.id.webview)

        webViewSetup(webViewVariable)

        onBackPressedDispatcher.addCallback(this) {

            if (webViewVariable.canGoBack()) {
                webViewVariable.goBack()
            } else {
                finish()
            }
        }
    }

    @RequiresApi(Build.VERSION_CODES.O)
    private fun webViewSetup(a: WebView) {

        a.webViewClient = WebViewClient()

        a.settings.javaScriptEnabled = true
        a.settings.domStorageEnabled = true
        a.settings.loadsImagesAutomatically = true
        a.settings.useWideViewPort = true
        a.settings.loadWithOverviewMode = true
        a.settings.safeBrowsingEnabled = true

        a.loadUrl("https://mohitkumarshaw.netlify.app")
    }
}
```

---

## activity_main.xml

```xml
<?xml version="1.0" encoding="utf-8"?>

<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <WebView
        android:id="@+id/webview"
        android:layout_width="match_parent"
        android:layout_height="match_parent"/>

</LinearLayout>
```

---

# Line by Line Explanation (MainActivity.kt)

## Line 1

```kotlin
package com.example.webview
```

### Meaning

Defines the package where MainActivity belongs.

### Simple English

The file is stored inside the **webview** package.

---

## Line 2

```kotlin
import android.os.Build
```

### Meaning

Imports the `Build` class.

### Simple English

Used to check the Android version.

---

## Line 3

```kotlin
import android.os.Bundle
```

### Meaning

Imports the `Bundle` class.

### Simple English

Stores Activity state information.

---

## Line 4

```kotlin
import android.webkit.WebView
```

### Meaning

Imports the `WebView` class.

### Simple English

Allows the app to display web pages inside the application.

---

## Line 5

```kotlin
import android.webkit.WebViewClient
```

### Meaning

Imports the `WebViewClient` class.

### Simple English

Keeps web pages opening inside the WebView instead of an external browser.

---

## Line 6

```kotlin
import androidx.activity.addCallback
```

### Meaning

Imports the Back Press callback.

### Simple English

Allows custom behavior when the Back button is pressed.

---

## Line 7

```kotlin
import androidx.annotation.RequiresApi
```

### Meaning

Imports the `RequiresApi` annotation.

### Simple English

Ensures a method runs only on supported Android versions.

---

## Line 8

```kotlin
import androidx.appcompat.app.AppCompatActivity
```

### Meaning

Imports `AppCompatActivity`.

### Simple English

Makes MainActivity an Android Activity.

---

## Class

```kotlin
class MainActivity : AppCompatActivity()
```

### Meaning

Creates the MainActivity class.

### Simple English

This is the first screen of the application.

---

## Variable

```kotlin
private lateinit var webViewVariable: WebView
```

### Meaning

Declares a WebView variable that will be initialized later.

### Simple English

Creates a WebView reference before assigning it.

---

## RequiresApi

```kotlin
@RequiresApi(Build.VERSION_CODES.O)
```

### Meaning

Specifies that the following method requires Android Oreo (API 26) or higher.

### Simple English

The method works only on Android 8.0 and above.

---

## onCreate()

```kotlin
override fun onCreate(savedInstanceState: Bundle?)
```

### Meaning

Called when the Activity starts.

### Simple English

Android begins running the app from here.

---

## super.onCreate()

```kotlin
super.onCreate(savedInstanceState)
```

### Meaning

Calls the parent Activity's initialization.

### Simple English

Lets Android perform its default setup.

---

## setContentView()

```kotlin
setContentView(R.layout.activity_main)
```

### Meaning

Loads the XML layout.

### Simple English

Displays `activity_main.xml` on the screen.

---

## findViewById()

```kotlin
webViewVariable = findViewById(R.id.webview)
```

### Meaning

Finds the WebView from XML.

### Simple English

Connects the WebView with Kotlin.

---

## Call Function

```kotlin
webViewSetup(webViewVariable)
```

### Meaning

Calls the function that configures the WebView.

### Simple English

Initializes all WebView settings.

---

## Back Press Dispatcher

```kotlin
onBackPressedDispatcher.addCallback(this)
```

### Meaning

Registers a custom Back button action.

### Simple English

Controls what happens when the user presses the Back button.

---

## Check Previous Page

```kotlin
if (webViewVariable.canGoBack())
```

### Meaning

Checks whether the WebView has a previous page.

### Simple English

Determines if there is browsing history.

---

## Go Back

```kotlin
webViewVariable.goBack()
```

### Meaning

Loads the previous webpage.

### Simple English

Returns to the last visited page.

---

## Else

```kotlin
else
```

### Meaning

Runs when there is no previous page.

### Simple English

Executes the alternative action.

---

## finish()

```kotlin
finish()
```

### Meaning

Closes the Activity.

### Simple English

Exits the application screen.

---

## Function

```kotlin
private fun webViewSetup(a: WebView)
```

### Meaning

Creates a function to configure the WebView.

### Simple English

All WebView settings are written here.

---

## WebViewClient

```kotlin
a.webViewClient = WebViewClient()
```

### Meaning

Assigns a WebViewClient.

### Simple English

Keeps web pages opening inside the app instead of the browser.

---

## Enable JavaScript

```kotlin
a.settings.javaScriptEnabled = true
```

### Meaning

Enables JavaScript.

### Simple English

Allows websites that use JavaScript to work properly.

---

## Enable DOM Storage

```kotlin
a.settings.domStorageEnabled = true
```

### Meaning

Enables DOM Storage.

### Simple English

Allows websites to store local data.

---

## Load Images Automatically

```kotlin
a.settings.loadsImagesAutomatically = true
```

### Meaning

Automatically loads webpage images.

### Simple English

Images appear without extra code.

---

## Wide ViewPort

```kotlin
a.settings.useWideViewPort = true
```

### Meaning

Uses the webpage's viewport settings.

### Simple English

Displays websites correctly on different screen sizes.

---

## Overview Mode

```kotlin
a.settings.loadWithOverviewMode = true
```

### Meaning

Fits the webpage to the screen.

### Simple English

Shows the complete webpage without excessive zooming.

---

## Safe Browsing

```kotlin
a.settings.safeBrowsingEnabled = true
```

### Meaning

Enables Safe Browsing protection.

### Simple English

Helps protect users from harmful websites.

---

## Load URL

```kotlin
a.loadUrl("https://mohitkumarshaw.netlify.app")
```

### Meaning

Loads the specified website.

### Simple English

Opens the portfolio website inside the WebView.

---

## Closing Braces

```kotlin
}
```

### Meaning

Ends the function, Activity, and class.

### Simple English

Marks the end of the program.

# Concepts Used

- Activity
- AppCompatActivity
- Bundle
- WebView
- WebViewClient
- WebSettings
- Android Lifecycle
- `onCreate()`
- `setContentView()`
- `findViewById()`
- Function
- `RequiresApi`
- `Build.VERSION_CODES`
- `lateinit`
- Back Press Dispatcher
- `addCallback()`
- `canGoBack()`
- `goBack()`
- `finish()`
- JavaScript
- DOM Storage
- Safe Browsing
- ViewPort
- Overview Mode
- `loadUrl()`
- Internet Access
- XML Layout
- Kotlin
- Android SDK

---

# Flow of the App

```text
App Starts
      ↓
MainActivity is Created
      ↓
onCreate() Executes
      ↓
activity_main.xml Loads
      ↓
WebView is Connected using findViewById()
      ↓
webViewSetup() Function is Called
      ↓
WebViewClient is Assigned
      ↓
JavaScript Enabled
      ↓
DOM Storage Enabled
      ↓
Images Load Automatically
      ↓
Wide ViewPort Enabled
      ↓
Overview Mode Enabled
      ↓
Safe Browsing Enabled
      ↓
Website URL Loads inside WebView
      ↓
User Browses Website
      ↓
User Presses Back Button
      ↓
Previous Page Available?
      ↓
      Yes ----------------------→ goBack()
       │
       No
       │
       ↓
finish()
       ↓
Activity Closes
```

---

# Important Points

- `WebView` displays web pages inside an Android application.
- `WebViewClient` prevents links from opening in an external browser.
- `WebSettings` is used to configure WebView behavior.
- `javaScriptEnabled` enables JavaScript support.
- `domStorageEnabled` enables HTML5 local storage.
- `loadsImagesAutomatically` loads webpage images automatically.
- `useWideViewPort` makes webpages fit different screen sizes.
- `loadWithOverviewMode` scales the webpage to fit the screen.
- `safeBrowsingEnabled` protects users from malicious websites.
- `loadUrl()` loads a webpage into the WebView.
- `findViewById()` connects XML views with Kotlin.
- `lateinit` delays variable initialization until runtime.
- `onBackPressedDispatcher` provides custom Back button handling.
- `canGoBack()` checks whether a previous webpage exists.
- `goBack()` navigates to the previous webpage.
- `finish()` closes the current Activity.
- `@RequiresApi` ensures the method runs only on supported Android versions.
- `Build.VERSION_CODES.O` refers to Android Oreo (API 26).
- `onCreate()` is the first lifecycle method executed when an Activity starts.
- XML designs the user interface.
- Kotlin controls the application's behavior.

---

# Revision Notes

- **WebView** = Displays web pages inside the app.
- **WebViewClient** = Opens webpages inside WebView instead of the browser.
- **WebSettings** = Configures WebView settings.
- **loadUrl()** = Opens a webpage.
- **javaScriptEnabled** = Enables JavaScript execution.
- **domStorageEnabled** = Enables website local storage.
- **loadsImagesAutomatically** = Loads webpage images automatically.
- **useWideViewPort** = Displays webpages correctly on different screen sizes.
- **loadWithOverviewMode** = Fits the webpage to the screen.
- **safeBrowsingEnabled** = Protects against unsafe websites.
- **findViewById()** = Connects XML views with Kotlin.
- **lateinit** = Declares a variable that will be initialized later.
- **onBackPressedDispatcher** = Handles the Back button.
- **canGoBack()** = Checks for browsing history.
- **goBack()** = Opens the previous webpage.
- **finish()** = Closes the Activity.
- **@RequiresApi** = Restricts code to a specific Android version or above.
- **Build.VERSION_CODES.O** = Android Oreo (API 26).
- **onCreate()** = Starting point of an Activity.
- **Activity** = A single screen in an Android application.
- **XML** = Designs the user interface.
- **Kotlin** = Controls the application logic.

# XML Explanation (activity_main.xml)

## XML Declaration

```xml
<?xml version="1.0" encoding="utf-8"?>
```

### Meaning

Specifies that this is an XML file encoded using UTF-8.

### Simple English

It tells Android that this file is written in XML.

---

## Root Layout

```xml
<LinearLayout
```

### Meaning

Creates a LinearLayout container.

### Simple English

A layout that holds child views.

---

## Android Namespace

```xml
xmlns:android="http://schemas.android.com/apk/res/android"
```

### Meaning

Provides access to Android XML attributes.

### Simple English

Allows Android attributes like `layout_width` and `layout_height` to be used.

---

## App Namespace

```xml
xmlns:app="http://schemas.android.com/apk/res-auto"
```

### Meaning

Provides access to custom attributes from AndroidX libraries.

### Simple English

Used when AndroidX components require custom XML attributes.

---

## Tools Namespace

```xml
xmlns:tools="http://schemas.android.com/tools"
```

### Meaning

Provides design-time attributes used by Android Studio.

### Simple English

Helps during UI designing but is ignored when the app runs.

---

## Layout ID

```xml
android:id="@+id/main"
```

### Meaning

Assigns a unique ID to the LinearLayout.

### Simple English

Kotlin can access this layout using its ID.

---

## Layout Width

```xml
android:layout_width="match_parent"
```

### Meaning

Makes the layout occupy the full width of the screen.

### Simple English

The layout stretches from left to right.

---

## Layout Height

```xml
android:layout_height="match_parent"
```

### Meaning

Makes the layout occupy the full height of the screen.

### Simple English

The layout covers the entire screen.

---

## Context

```xml
tools:context=".MainActivity"
```

### Meaning

Specifies that this layout belongs to MainActivity.

### Simple English

Android Studio knows this XML is used by MainActivity.

---

# WebView

## WebView Tag

```xml
<WebView
```

### Meaning

Creates a WebView component.

### Simple English

Displays web pages inside the application.

---

## WebView ID

```xml
android:id="@+id/webview"
```

### Meaning

Assigns a unique ID to the WebView.

### Simple English

Kotlin uses this ID to access the WebView.

---

## WebView Width

```xml
android:layout_width="match_parent"
```

### Meaning

Makes the WebView occupy the full width.

### Simple English

The webpage fills the screen horizontally.

---

## WebView Height

```xml
android:layout_height="match_parent"
```

### Meaning

Makes the WebView occupy the full height.

### Simple English

The webpage fills the screen vertically.

---

## Closing Tag

```xml
/>
```

### Meaning

Closes the WebView element.

### Simple English

Marks the end of the WebView definition.

---

## Closing LinearLayout

```xml
</LinearLayout>
```

### Meaning

Ends the LinearLayout.

### Simple English

Marks the end of the XML layout.

---

# Concepts Used

- XML
- LinearLayout
- WebView
- Android Namespace
- App Namespace
- Tools Namespace
- ID
- Layout Width
- Layout Height
- match_parent
- XML Attributes
- User Interface (UI)

---

# Important Points

- `LinearLayout` is the root container.
- `WebView` displays web pages inside the application.
- `android:id` gives a unique identity to a View.
- `match_parent` makes a View occupy all available space.
- `tools:context` links the layout to an Activity for preview.
- `xmlns:android` enables Android XML attributes.
- `xmlns:app` enables AndroidX custom attributes.
- `xmlns:tools` is only used during design time.
- XML is responsible for designing the application's user interface.
- The WebView occupies the entire screen because both width and height use `match_parent`.

---

# Revision Notes

- **XML** = Designs the application's UI.
- **LinearLayout** = Container that holds child views.
- **WebView** = Displays websites inside the app.
- **android:id** = Unique identifier for a View.
- **match_parent** = Occupies the available space.
- **layout_width** = Sets the width of a View.
- **layout_height** = Sets the height of a View.
- **tools:context** = Connects the XML with its Activity for preview.
- **xmlns:android** = Enables Android attributes.
- **xmlns:app** = Enables AndroidX custom attributes.
- **xmlns:tools** = Used only by Android Studio.
- The WebView fills the entire screen in this project.

# Interview Questions and Answers

## 1. What is a WebView?

A WebView is an Android component used to display web pages inside an application without opening an external browser.

---

## 2. Why is WebView used?

It allows users to browse web content without leaving the application.

---

## 3. Which class is used to display web pages inside an Android app?

```kotlin
WebView
```

---

## 4. Which class keeps web pages inside the WebView?

```kotlin
WebViewClient
```

---

## 5. What happens if a WebViewClient is not set?

The website opens in the device's default browser instead of inside the app.

---

## 6. Which method loads a website into a WebView?

```kotlin
loadUrl()
```

---

## 7. Give an example of loading a website.

```kotlin
webView.loadUrl("https://example.com")
```

---

## 8. What is WebSettings?

WebSettings is used to configure the behavior of a WebView.

---

## 9. Why is JavaScript enabled?

Many modern websites require JavaScript to function properly.

---

## 10. Which property enables JavaScript?

```kotlin
settings.javaScriptEnabled = true
```

---

## 11. What is DOM Storage?

DOM Storage allows websites to store data locally on the user's device.

---

## 12. Which property enables DOM Storage?

```kotlin
settings.domStorageEnabled = true
```

---

## 13. Why is `loadsImagesAutomatically` used?

It automatically loads images from webpages.

---

## 14. What does `useWideViewPort` do?

It displays webpages correctly on different screen sizes.

---

## 15. What is `loadWithOverviewMode`?

It scales the webpage to fit the screen.

---

## 16. What is Safe Browsing?

Safe Browsing helps protect users from harmful and malicious websites.

---

## 17. Which property enables Safe Browsing?

```kotlin
settings.safeBrowsingEnabled = true
```

---

## 18. What is `findViewById()`?

It connects an XML view with Kotlin code.

---

## 19. Why is `lateinit` used?

It allows a variable to be initialized later instead of immediately.

---

## 20. What is `onCreate()`?

It is the first lifecycle method called when an Activity starts.

---

## 21. Why is `super.onCreate()` called?

It allows Android to perform its default Activity initialization.

---

## 22. What is `setContentView()`?

It loads the XML layout into the Activity.

---

## 23. What is `@RequiresApi`?

It specifies that a method requires a minimum Android API level.

---

## 24. What is `Build.VERSION_CODES.O`?

It represents Android Oreo (API Level 26).

---

## 25. Why is `webViewSetup()` created?

To keep all WebView configuration code in one separate function.

---

## 26. What is `onBackPressedDispatcher`?

It is the modern API for handling the Back button.

---

## 27. What does `canGoBack()` do?

It checks whether the WebView has a previous page.

---

## 28. What does `goBack()` do?

It navigates to the previously visited webpage.

---

## 29. What happens when there is no previous page?

The Activity closes using `finish()`.

---

## 30. What does `finish()` do?

It closes the current Activity.

---

## 31. What is an Activity?

An Activity represents a single screen in an Android application.

---

## 32. What is AppCompatActivity?

It is the base Activity class that provides backward compatibility.

---

## 33. What is Bundle?

Bundle stores Activity state information and data.

---

## 34. Which XML view is used in this project?

```text
WebView
```

---

## 35. Which layout is used?

```text
LinearLayout
```

---

## 36. What does `match_parent` mean?

The View occupies all available space in its parent.

---

## 37. What is the purpose of XML?

XML is used to design the application's user interface.

---

## 38. What is the purpose of Kotlin?

Kotlin is used to write the application's logic.

---

## 39. What are the main concepts used in this project?

- Activity
- WebView
- WebViewClient
- WebSettings
- Bundle
- XML
- Kotlin
- loadUrl()
- findViewById()
- onBackPressedDispatcher
- goBack()
- finish()

---

## 40. What is the application flow?

1. App starts.
2. MainActivity is created.
3. XML layout loads.
4. WebView connects with Kotlin.
5. WebView settings are configured.
6. Website loads inside the app.
7. User browses the website.
8. Back button checks browsing history.
9. Previous page opens or the Activity closes.

---

## 41. Why is WebView useful?

It provides an in-app browsing experience without opening an external browser.

---

## 42. Can WebView display online websites?

Yes. It can display both online websites and local HTML files.

---

## 43. What is the benefit of using WebViewClient?

It keeps the user inside the application while browsing.

---

## 44. Which function loads a URL?

```kotlin
loadUrl()
```

---

## 45. Why is WebView important in Android?

It allows developers to integrate web content directly into Android applications.

---

# Keywords Learned

- WebView
- WebViewClient
- WebSettings
- loadUrl()
- JavaScript
- DOM Storage
- Safe Browsing
- ViewPort
- Overview Mode
- Activity
- AppCompatActivity
- Bundle
- XML
- Kotlin
- LinearLayout
- findViewById()
- lateinit
- onCreate()
- onBackPressedDispatcher
- addCallback()
- canGoBack()
- goBack()
- finish()
- RequiresApi
- Build.VERSION_CODES.O
- Android SDK

---

# Summary

- **WebView** displays web pages inside an Android application.
- **WebViewClient** prevents web pages from opening in an external browser.
- **WebSettings** configures the behavior of the WebView.
- **JavaScript** is enabled for interactive websites.
- **DOM Storage** allows websites to store local data.
- **Safe Browsing** helps protect users from unsafe websites.
- **loadUrl()** loads a webpage into the WebView.
- **findViewById()** connects the XML WebView with Kotlin.
- **onBackPressedDispatcher** customizes Back button behavior.
- **canGoBack()** checks whether a previous webpage exists.
- **goBack()** navigates to the previous webpage.
- **finish()** closes the Activity when no browsing history is available.
- XML is used to design the application's user interface.
- Kotlin controls the application's functionality.
- This project demonstrates how to build a simple in-app web browser using Android WebView.