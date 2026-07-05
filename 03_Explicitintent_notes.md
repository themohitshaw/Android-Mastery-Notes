# Project: 03 Explicit Intent

## Project Repository

**GitHub Project:**

```text
https://github.com/themohitshaw/Android-Mastery/tree/main/03%20ExplicitIntent
```


---

## Project Information

* **Project Number:** 03
* **Project Name:** Explicit Intent
* **Technology:** Kotlin, XML
* **IDE:** Android Studio

---

## Objective

This project demonstrates how to navigate from one Activity to another using **Explicit Intent**.

When the user clicks the button on the first screen, Android opens the second screen using the `Intent` class and the `startActivity()` method.

---

# Complete Code

## MainActivity.kt

```kotlin
package com.example.explicitintent

import android.content.Intent
import android.os.Bundle
import android.widget.Button
import androidx.activity.enableEdgeToEdge
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        enableEdgeToEdge()

        setContentView(R.layout.activity_main)

        val btnIntent = findViewById<Button>(R.id.button)

        btnIntent.setOnClickListener {

            // Open New Activity
            intent = Intent(applicationContext, SecondActivity::class.java)

            startActivity(intent)

        }
    }
}
```

---

## SecondActivity.kt

```kotlin
package com.example.explicitintent

import android.os.Bundle
import androidx.activity.enableEdgeToEdge
import androidx.appcompat.app.AppCompatActivity

class SecondActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        enableEdgeToEdge()

        setContentView(R.layout.activity_second)
    }
}
```

---

## activity_main.xml

```xml
<?xml version="1.0" encoding="utf-8"?>

<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center"
        android:layout_marginTop="100dp"
        android:width="300dp"
        android:text="CLICK ME"/>

</LinearLayout>
```

---

## activity_second.xml

```xml
<?xml version="1.0" encoding="utf-8"?>

<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".SecondActivity">

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center"
        android:layout_marginTop="100dp"
        android:gravity="center"
        android:text="I am screen 2"
        android:textSize="30sp"
        android:textStyle="bold"/>

</LinearLayout>
```

---

# Line by Line Explanation (MainActivity.kt)



## Line 1

```kotlin
package com.example.explicitintent
```

### Meaning

This tells Android that the file belongs to the `explicitintent` package.

### Simple English

The file is stored inside the `explicitintent` package.

---

## Line 2

```kotlin
import android.content.Intent
```

### Meaning

Imports the `Intent` class, which is used to move from one Activity to another.

### Simple English

It allows one screen to open another screen.

---

## Line 3

```kotlin
import android.os.Bundle
```

### Meaning

Imports the `Bundle` class.

A Bundle stores data that Android passes to an Activity.

### Simple English

It carries information to the Activity when it starts.

---

## Line 4

```kotlin
import android.widget.Button
```

### Meaning

Imports the Button widget.

### Simple English

Allows us to use a Button in Kotlin.

---

## Line 5

```kotlin
import androidx.activity.enableEdgeToEdge
```

### Meaning

Enables Edge-to-Edge display.

### Simple English

The app uses the complete screen.

---

## Line 6

```kotlin
import androidx.appcompat.app.AppCompatActivity
```

### Meaning

Imports the AppCompatActivity class.

### Simple English

It makes MainActivity an Android screen.

---

# Class

```kotlin
class MainActivity : AppCompatActivity()
```

### Meaning

Creates a new Activity named MainActivity.

It inherits all the features of AppCompatActivity.

### Simple English

This is the first screen of the application.

---

# onCreate()

```kotlin
override fun onCreate(savedInstanceState: Bundle?)
```

### Meaning

`onCreate()` is the first lifecycle method called when the Activity starts.

### Simple English

Android starts executing the code from here.

---

# super.onCreate()

```kotlin
super.onCreate(savedInstanceState)
```

### Meaning

Calls the parent Activity's `onCreate()` method.

### Simple English

Android performs its default setup before running your code.

---

# Edge to Edge

```kotlin
enableEdgeToEdge()
```

### Meaning

Allows the application to use the entire screen.

### Simple English

The app can display content from edge to edge.

---

# Connecting XML

```kotlin
setContentView(R.layout.activity_main)
```

### Meaning

Loads the XML layout for MainActivity.

### Simple English

Displays the `activity_main.xml` screen.

---

# findViewById()

```kotlin
val btnIntent = findViewById<Button>(R.id.button)
```

### Meaning

Finds the Button using its ID.

The returned Button is stored inside the variable `btnIntent`.

### Simple English

Kotlin gets access to the Button created in XML.

---

# Button Variable

```kotlin
val btnIntent
```

### Meaning

Creates a read-only variable.

### Simple English

Stores the Button so it can be used later.

---

# Generic Type

```kotlin
<Button>
```

### Meaning

Specifies that the view is a Button.

### Simple English

Android knows the view is a Button.

---

# View ID

```kotlin
R.id.button
```

### Meaning

Represents the ID of the Button declared in XML.

### Simple English

Connects Kotlin with the XML Button.

---

# Click Listener

```kotlin
btnIntent.setOnClickListener
```

### Meaning

Registers a click event for the Button.

### Simple English

Runs the code whenever the user clicks the Button.

---

# Lambda Block

```kotlin
{
```

### Meaning

Starts the code block that executes after the Button is clicked.

### Simple English

Everything inside runs after the click.

---

# Intent Object

```kotlin
intent = Intent(applicationContext, SecondActivity::class.java)
```

### Meaning

Creates an Explicit Intent.

It tells Android to open `SecondActivity`.

### Simple English

Android is instructed to move from Screen 1 to Screen 2.

---

# applicationContext

```kotlin
applicationContext
```

### Meaning

Provides the current application's context.

### Simple English

Android knows from which application the request is coming.

---

# Target Activity

```kotlin
SecondActivity::class.java
```

### Meaning

Specifies the Activity that should open.

### Simple English

The destination screen is SecondActivity.

---

# startActivity()

```kotlin
startActivity(intent)
```

### Meaning

Starts the Activity specified by the Intent.

### Simple English

Opens the second screen.

---

# Closing Braces

```kotlin
}
```

### Meaning

Ends the click listener, `onCreate()` function, and MainActivity class.

### Simple English

Marks the end of the code blocks.

---
# Concepts Used

* Activity
* AppCompatActivity
* Bundle
* Intent
* Explicit Intent
* Button
* LinearLayout
* Kotlin
* XML Layout
* findViewById()
* setOnClickListener()
* startActivity()
* applicationContext
* Resource Management
* Edge-to-Edge Design

---

# Flow of the App

```text
App Starts
      ↓
onCreate()
      ↓
activity_main.xml Loads
      ↓
Button Displays
      ↓
User Clicks Button
      ↓
Intent Object Created
      ↓
startActivity() Called
      ↓
SecondActivity Opens
```

---

# Important Points

* Activity represents a single screen.
* Intent is used to communicate between Activities.
* Explicit Intent opens a specific Activity.
* Button detects user click events.
* findViewById() connects XML views with Kotlin.
* setOnClickListener() handles button clicks.
* startActivity() launches a new Activity.
* applicationContext provides the application context.
* enableEdgeToEdge() uses the full screen.
* MainActivity is the entry point of the application.

---

# Revision Notes

* Activity = A screen in Android.
* MainActivity = First screen of the app.
* Intent = Used to move between Activities.
* Explicit Intent = Opens a specific Activity.
* Button = Performs an action when clicked.
* findViewById() = Connects XML views with Kotlin.
* setOnClickListener() = Executes code on button click.
* startActivity() = Opens another Activity.
* applicationContext = Provides application information.
* XML creates the user interface.
* Kotlin controls the application logic.
* enableEdgeToEdge() allows the app to use the complete screen.
* Resource IDs connect XML components with Kotlin code.

---

# Line by Line Explanation (SecondActivity.kt)

## Line 1

```kotlin
package com.example.explicitintent
```

### Meaning

This tells Android that the file belongs to the `explicitintent` package.

### Simple English

The file is stored inside the `explicitintent` package.

---

## Line 2

```kotlin
import android.os.Bundle
```

### Meaning

Imports the `Bundle` class.

A `Bundle` stores data that Android passes to an Activity.

### Simple English

It carries information to the Activity when it starts.

---

## Line 3

```kotlin
import androidx.activity.enableEdgeToEdge
```

### Meaning

Imports the `enableEdgeToEdge()` function.

### Simple English

It allows the application to use the full screen.

---

## Line 4

```kotlin
import androidx.appcompat.app.AppCompatActivity
```

### Meaning

Imports the `AppCompatActivity` class.

### Simple English

It provides all the basic features required for an Android Activity.

---

# Class

```kotlin
class SecondActivity : AppCompatActivity()
```

### Meaning

Creates a new Activity named `SecondActivity`.

It inherits all the features of `AppCompatActivity`.

### Simple English

This is the second screen of the application.

---

# onCreate()

```kotlin
override fun onCreate(savedInstanceState: Bundle?)
```

### Meaning

`onCreate()` is the first lifecycle method called when the Activity is created.

### Simple English

Android starts executing the Activity from here.

---

# super.onCreate()

```kotlin
super.onCreate(savedInstanceState)
```

### Meaning

Calls the parent Activity's `onCreate()` method.

### Simple English

Android performs its default setup before executing your code.

---

# Edge to Edge

```kotlin
enableEdgeToEdge()
```

### Meaning

Allows the application to use the complete display area.

### Simple English

The app uses the entire screen.

---

# Connecting XML

```kotlin
setContentView(R.layout.activity_second)
```

### Meaning

Connects the `activity_second.xml` layout with `SecondActivity`.

### Simple English

Android displays the second screen's user interface.

---

# Layout Resource

```kotlin
R.layout.activity_second
```

### Meaning

Represents the XML layout resource for the second Activity.

### Simple English

Android loads the `activity_second.xml` file.

---

# Closing Braces

```kotlin
}
```

### Meaning

Ends the `onCreate()` function and the `SecondActivity` class.

### Simple English

Marks the end of the code blocks.

---


# Keywords Learned

* package
* import
* Bundle
* AppCompatActivity
* Activity
* onCreate()
* super.onCreate()
* enableEdgeToEdge()
* setContentView()
* activity_second.xml
* TextView
* Resource Management

---

# Concepts Used

* Activity
* AppCompatActivity
* Bundle
* TextView
* XML Layout
* Resource Management
* enableEdgeToEdge()
* setContentView()
* Android Activity Lifecycle
* Edge-to-Edge Design

---

# Flow of the App

```text
MainActivity Opens
        ↓
User Clicks Button
        ↓
SecondActivity Starts
        ↓
onCreate()
        ↓
activity_second.xml Loads
        ↓
TextView Displays
        ↓
User Views Screen 2
```

---

# Important Points

* SecondActivity is the destination screen.
* onCreate() is the first lifecycle method.
* setContentView() connects Kotlin with XML.
* TextView displays text on the screen.
* enableEdgeToEdge() allows the app to use the full display.
* AppCompatActivity provides Android Activity features.
* XML defines the user interface.
* Kotlin controls the Activity behavior.
* Resources are stored inside the `res` folder.

---

# Revision Notes

* SecondActivity is the second screen of the application.
* Activity represents a single screen.
* XML creates the user interface.
* Kotlin controls the application logic.
* TextView displays text.
* onCreate() runs when the Activity starts.
* setContentView() loads the XML layout.
* enableEdgeToEdge() enables full-screen display.
* Resources are stored inside the `res` folder.
* AppCompatActivity provides backward compatibility.

---

# XML Explanation (activity_main.xml)

## Root Layout

```xml
<LinearLayout
```

### Meaning

Creates a LinearLayout.

### Simple English

A container that holds views.

---

## ID

```xml
android:id="@+id/main"
```

### Meaning

Provides a unique ID for the layout.

### Simple English

Kotlin uses this ID to access the layout.

---

## Layout Width

```xml
android:layout_width="match_parent"
```

### Meaning

Makes the layout occupy the full width of the screen.

### Simple English

Stretches from the left edge to the right edge.

---

## Layout Height

```xml
android:layout_height="match_parent"
```

### Meaning

Makes the layout occupy the full height of the screen.

### Simple English

Covers the entire screen.

---

## Orientation

```xml
android:orientation="vertical"
```

### Meaning

Arranges child views vertically.

### Simple English

Views are displayed one below another.

---

## Button

```xml
<Button
```

### Meaning

Creates a clickable Button.

### Simple English

The user taps this button to perform an action.

---

## Button ID

```xml
android:id="@+id/button"
```

### Meaning

Assigns a unique ID to the Button.

### Simple English

Kotlin uses this ID with `findViewById()`.

---

## Layout Width

```xml
android:layout_width="wrap_content"
```

### Meaning

Makes the Button only as wide as its content.

### Simple English

The Button uses only the required width.

---

## Layout Height

```xml
android:layout_height="wrap_content"
```

### Meaning

Makes the Button only as tall as its content.

### Simple English

The Button uses only the required height.

---

## Layout Gravity

```xml
android:layout_gravity="center"
```

### Meaning

Places the Button in the center of its parent layout.

### Simple English

The Button appears in the center.

---

## Layout Margin Top

```xml
android:layout_marginTop="100dp"
```

### Meaning

Adds space above the Button.

### Simple English

Moves the Button downward.

---

## Width

```xml
android:width="300dp"
```

### Meaning

Sets the Button width to 300dp.

### Simple English

Makes the Button wider.

---

## Text

```xml
android:text="CLICK ME"
```

### Meaning

Sets the text displayed on the Button.

### Simple English

Shows "CLICK ME" on the Button.

---

# Concepts Used

* LinearLayout
* Button
* Layout Width
* Layout Height
* Orientation
* Gravity
* Margin
* ID
* Text Attribute
* Resource Management
* XML Layout
* User Interface (UI)

---

# Important Points

* LinearLayout arranges views vertically.
* Button receives user click events.
* IDs connect XML views with Kotlin code.
* `layout_gravity` positions the Button.
* `layout_marginTop` creates space above the Button.
* `match_parent` occupies the available space.
* `wrap_content` uses only the required space.
* `android:width` sets a fixed width.
* `android:text` displays text on the Button.
* XML is used to design the user interface.

---

# Revision Notes

* `match_parent` = full available space.
* `wrap_content` = size according to content.
* `vertical` = top-to-bottom arrangement.
* `Button` = clickable view.
* `layout_gravity` = positions a view.
* `layout_marginTop` = adds top spacing.
* `android:text` = displays text.
* IDs are used by `findViewById()`.
* XML designs the UI.
* Kotlin controls the UI.

---

# XML Explanation (activity_second.xml)

## Root Layout

```xml
<LinearLayout
```

### Meaning

Creates a LinearLayout.

### Simple English

A container that holds views.

---

## ID

```xml
android:id="@+id/main"
```

### Meaning

Provides a unique ID.

### Simple English

Kotlin can access this layout using its ID.

---

## Layout Width

```xml
android:layout_width="match_parent"
```

### Meaning

Uses the full width of the screen.

### Simple English

Stretches from left to right.

---

## Layout Height

```xml
android:layout_height="match_parent"
```

### Meaning

Uses the full height of the screen.

### Simple English

Covers the entire screen.

---

## Orientation

```xml
android:orientation="vertical"
```

### Meaning

Displays child views vertically.

### Simple English

Views appear one below another.

---

## TextView

```xml
<TextView
```

### Meaning

Creates a TextView.

### Simple English

Displays text on the screen.

---

## TextView ID

```xml
android:id="@+id/textView"
```

### Meaning

Provides a unique ID for the TextView.

### Simple English

Kotlin uses this ID if it needs to access the TextView.

---

## Layout Width

```xml
android:layout_width="wrap_content"
```

### Meaning

Uses only the required width.

### Simple English

Fits the text size.

---

## Layout Height

```xml
android:layout_height="wrap_content"
```

### Meaning

Uses only the required height.

### Simple English

Fits the text height.

---

## Layout Gravity

```xml
android:layout_gravity="center"
```

### Meaning

Places the TextView in the center.

### Simple English

Centers the TextView.

---

## Layout Margin Top

```xml
android:layout_marginTop="100dp"
```

### Meaning

Adds space above the TextView.

### Simple English

Moves the TextView downward.

---

## Gravity

```xml
android:gravity="center"
```

### Meaning

Centers the text inside the TextView.

### Simple English

The text appears in the middle.

---

## Text

```xml
android:text="I am screen 2"
```

### Meaning

Sets the text displayed by the TextView.

### Simple English

Shows "I am screen 2" on the screen.

---

## Text Size

```xml
android:textSize="30sp"
```

### Meaning

Sets the text size to 30sp.

### Simple English

Makes the text larger.

---

## Text Style

```xml
android:textStyle="bold"
```

### Meaning

Displays the text in bold.

### Simple English

Makes the text thicker.

---

# Concepts Used

* LinearLayout
* TextView
* Layout Width
* Layout Height
* Orientation
* Gravity
* Margin
* Text Size
* Text Style
* Resource Management
* XML Layout
* User Interface (UI)

---

# Important Points

* LinearLayout arranges views vertically.
* TextView displays text.
* IDs connect XML views with Kotlin code.
* `layout_gravity` positions the TextView.
* `gravity` aligns text inside the TextView.
* `layout_marginTop` creates top spacing.
* `textSize` controls text size.
* `textStyle` changes text appearance.
* `match_parent` occupies the available space.
* `wrap_content` uses only the required space.

---

# Revision Notes

* `match_parent` = full available space.
* `wrap_content` = size according to content.
* `vertical` = top-to-bottom arrangement.
* `TextView` = displays text.
* `gravity` = aligns text inside a view.
* `layout_gravity` = positions a view.
* `layout_marginTop` = adds top spacing.
* `textSize` = changes text size.
* `textStyle` = changes text appearance.
* XML creates the user interface.

---


# Interview Questions and Answers

## 1. What is an Activity?

An Activity represents a single screen in an Android application.

---

## 2. What is AppCompatActivity?

It is the base class for Activities that provides backward compatibility for older Android versions.

---

## 3. What is Explicit Intent?

An Explicit Intent is used to open a specific Activity within an application.

---

## 4. What is an Intent?

An Intent is a messaging object used to request an action from another component.

---

## 5. Why is Explicit Intent called "Explicit"?

Because the destination Activity is explicitly specified by the programmer.

---

## 6. What is the syntax of an Explicit Intent?

```kotlin
Intent(applicationContext, SecondActivity::class.java)
```

---

## 7. What is the purpose of `startActivity()`?

It starts a new Activity specified by the Intent.

---

## 8. Which Activity starts first in this project?

MainActivity starts first.

---

## 9. Which Activity opens after clicking the Button?

SecondActivity opens.

---

## 10. What is `applicationContext`?

It provides the current application's context.

---

## 11. Why do we use `findViewById()`?

To access XML views from Kotlin code.

---

## 12. What is `setOnClickListener()`?

It detects when the user clicks a View such as a Button.

---

## 13. What is the purpose of `Button`?

A Button allows the user to perform an action when clicked.

---

## 14. What is the purpose of `TextView`?

TextView displays text on the screen.

---

## 15. What is `setContentView()`?

It connects an XML layout with an Activity.

---

## 16. What is `onCreate()`?

It is the first lifecycle method called when an Activity is created.

---

## 17. Why do we call `super.onCreate()`?

To allow Android to perform its default Activity initialization.

---

## 18. What is `enableEdgeToEdge()`?

It allows the application to use the complete display area.

---

## 19. What is `Bundle`?

Bundle stores and transfers Activity data.

---

## 20. What is XML in Android?

XML is used to design the user interface.

---

## 21. What is Kotlin used for?

Kotlin is used to write the application's logic.

---

## 22. What is `LinearLayout`?

LinearLayout arranges views vertically or horizontally.

---

## 23. What is `match_parent`?

It occupies all available space in the parent layout.

---

## 24. What is `wrap_content`?

It occupies only the space required by the content.

---

## 25. What is `layout_gravity`?

It positions a View inside its parent layout.

---

## 26. What is `layout_marginTop`?

It adds space above a View.

---

## 27. Why do we assign IDs to Views?

IDs allow Kotlin to access XML views.

---

## 28. What happens when the Button is clicked?

An Explicit Intent is created, and `SecondActivity` is opened.

---

## 29. Can an Explicit Intent open Activities from another application?

No.

Explicit Intents are mainly used to open known Activities, usually within the same application.

---

## 30. What is the application flow?

1. App starts.
2. MainActivity opens.
3. XML layout loads.
4. Button is displayed.
5. User clicks the Button.
6. Explicit Intent is created.
7. `startActivity()` is called.
8. SecondActivity opens.
9. The TextView is displayed.

---

## 31. Which class represents the destination Activity?

```kotlin
SecondActivity::class.java
```

---

## 32. Which method loads the XML file?

```kotlin
setContentView()
```

---

## 33. Which method is used to launch another Activity?

```kotlin
startActivity()
```

---

## 34. Which widget receives the click event?

Button.

---

## 35. Which widget displays "I am screen 2"?

TextView.

---

## 36. What are the main concepts used in this project?

* Activity
* AppCompatActivity
* Bundle
* Intent
* Explicit Intent
* Button
* TextView
* LinearLayout
* XML
* Kotlin
* findViewById()
* setOnClickListener()
* startActivity()

---

## 37. What is the advantage of Explicit Intent?

It provides direct and secure navigation to a specific Activity.

---

## 38. When should Explicit Intent be used?

When the destination Activity is already known.

---

## 39. What is the difference between Explicit Intent and Implicit Intent?

**Explicit Intent:** Opens a specific Activity.

**Implicit Intent:** Requests Android to choose a suitable application for the action.

---

## 40. Why is Explicit Intent important?

It enables navigation between screens and is one of the most commonly used features in Android application development.

---

