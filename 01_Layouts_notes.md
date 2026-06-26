

# Project: 01 Layouts (Colour Buttons)

## Project Repository

**GitHub Project:**

https://github.com/themohitshaw/Android-Mastery/tree/2e3fa1ebef71b3702415a472241b7c3c465a1df5/02%20Text%20and%20Scroll%20View

---

## Project Information

* **Project Number:** 01
* **Project Name:** Layouts
* **Technology:** Kotlin, XML
* **IDE:** Android Studio

---

## Objective

This project demonstrates how to change the background color of a layout using multiple buttons.

---
## Complete Code
### MainActivity.kt

```kotlin
package com.example.layouts

import android.os.Bundle
import android.widget.Button
import android.widget.LinearLayout
import androidx.activity.enableEdgeToEdge
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        enableEdgeToEdge()
        setContentView(R.layout.activity_main)

        val buttonBlack = findViewById<Button>(R.id.btnblack)
        val buttonYellow = findViewById<Button>(R.id.btnyellow)
        val buttonRed = findViewById<Button>(R.id.btnred)
        val buttonGreen = findViewById<Button>(R.id.btngreen)
        val buttonBlue = findViewById<Button>(R.id.btnblue)
        val buttonWhite = findViewById<Button>(R.id.btnwhite)

        val layout = findViewById<LinearLayout>(R.id.l_layout)

        buttonBlack.setOnClickListener {
            layout.setBackgroundResource(R.color.black)
        }

        buttonYellow.setOnClickListener {
            layout.setBackgroundResource(R.color.yellow)
        }

        buttonRed.setOnClickListener {
            layout.setBackgroundResource(R.color.red)
        }

        buttonGreen.setOnClickListener {
            layout.setBackgroundResource(R.color.green)
        }

        buttonBlue.setOnClickListener {
            layout.setBackgroundResource(R.color.blue)
        }

        buttonWhite.setOnClickListener {
            layout.setBackgroundResource(R.color.white)
        }
    }
}

```
### activity_main.xml
```xml

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/l_layout"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="bottom"
    tools:context=".MainActivity">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="30dp"
        android:orientation="horizontal">


        <Button
            android:id="@+id/btnblack"
            android:layout_width="50dp"
            android:layout_height="50dp"
            android:layout_weight="1"
            android:layout_margin="5dp"
            android:backgroundTint="@color/black"
            app:strokeColor="#FF0000"

            app:strokeWidth="2dp"

            app:backgroundTint="#FFFFFF"

            app:cornerRadius="8dp"
            android:text="" />

        <Button
            android:id="@+id/btnyellow"
            android:layout_width="50dp"
            android:layout_height="50dp"
            android:layout_weight="1"
            android:layout_margin="5dp"
            android:backgroundTint="@color/yellow"
            app:strokeColor="#FF0000"

            app:strokeWidth="2dp"

            app:backgroundTint="#FFFFFF"

            app:cornerRadius="8dp"
            android:text="" />

        <Button
            android:id="@+id/btnred"
            android:layout_width="50dp"
            android:layout_height="50dp"
            android:layout_weight="1"
            android:layout_margin="5dp"
            android:backgroundTint="@color/red"
            app:strokeColor="#FF0000"

            app:strokeWidth="2dp"

            app:backgroundTint="#FFFFFF"

            app:cornerRadius="8dp"
            android:text="" />

        <Button
            android:id="@+id/btngreen"
            android:layout_width="50dp"
            android:layout_height="50dp"
            android:layout_weight="1"
            android:layout_margin="5dp"
            android:backgroundTint="@color/green"
            app:strokeColor="#FF0000"

            app:strokeWidth="2dp"

            app:backgroundTint="#FFFFFF"

            app:cornerRadius="8dp"
            android:text="" />

        <Button
            android:id="@+id/btnblue"
            android:layout_width="50dp"
            android:layout_height="50dp"
            android:layout_weight="1"
            android:layout_margin="5dp"
            app:strokeColor="#FF0000"

            app:strokeWidth="2dp"

            app:backgroundTint="#FFFFFF"

            app:cornerRadius="8dp"
            android:backgroundTint="@color/blue"
            android:text="" />

        <Button
            android:id="@+id/btnwhite"
            android:layout_width="50dp"
            android:layout_height="50dp"
            android:layout_weight="1"
            android:layout_margin="5dp"
            android:backgroundTint="@color/white"
            app:strokeColor="#FF0000"

            app:strokeWidth="2dp"

            app:backgroundTint="#FFFFFF"

            app:cornerRadius="8dp"
            android:text="" />
    </LinearLayout>



</LinearLayout>
```

---

# Line by Line Explanation

## Line 1

```kotlin
package com.example.layouts
```

### Meaning

This tells Android that this file belongs to the layouts package.

### Simple English

The file lives inside the layouts folder.

---

## Line 2

```kotlin
import android.os.Bundle
```

### Meaning

Bundle stores data when the activity starts.

### Simple English

It carries information to the activity.

---

## Line 3

```kotlin
import android.widget.Button
```

### Meaning

Allows us to use Button in Kotlin code.

### Simple English

We are telling Kotlin that we want to work with buttons.

---

## Line 4

```kotlin
import android.widget.LinearLayout
```

### Meaning

Allows us to access the LinearLayout.

### Simple English

We want to change the screen background, so we need LinearLayout.

---

## Line 5

```kotlin
import androidx.activity.enableEdgeToEdge
```

### Meaning

Allows the app to use the entire screen.

### Simple English

The app can use the full display area.

---

## Line 6

```kotlin
import androidx.appcompat.app.AppCompatActivity
```

### Meaning

Provides Activity features.

### Simple English

MainActivity becomes an Android screen.

---

# Class

```kotlin
class MainActivity : AppCompatActivity()
```

### Meaning

Creates the main screen.

### Simple English

This is the first screen of our app.

---

# onCreate

```kotlin
override fun onCreate(savedInstanceState: Bundle?)
```

### Meaning

Runs when the app opens.

### Simple English

Android starts executing code from here.

---

# Super

```kotlin
super.onCreate(savedInstanceState)
```

### Meaning

Calls the parent Activity.

### Simple English

Android does its own setup first.

---

# Edge to Edge

```kotlin
enableEdgeToEdge()
```

### Meaning

Makes the app use the whole screen.

### Simple English

The app can use the complete display area.

---

# XML Connection

```kotlin
setContentView(R.layout.activity_main)
```

### Meaning

Connects XML with Kotlin.

### Simple English

Show activity_main.xml on the screen.

---

# Button Connection

```kotlin
val buttonBlack = findViewById<Button>(R.id.btnblack)
```

### Meaning

Connects XML button to Kotlin variable.

### Simple English

Now Kotlin can control this button.

---

# Layout Connection

```kotlin
val layout = findViewById<LinearLayout>(R.id.l_layout)
```

### Meaning

Gets the main layout.

### Simple English

We want to change this layout color.

---

# Click Listener

```kotlin
buttonBlack.setOnClickListener {
```

### Meaning

Runs code when the button is clicked.

### Simple English

When the user presses the button, do something.

---

# Change Background

```kotlin
layout.setBackgroundResource(R.color.black)
```

### Meaning

Changes the layout color.

### Simple English

Make the screen black.

---

# Concepts Used

* Activity
* AppCompatActivity
* Bundle
* LinearLayout
* Button
* findViewById()
* Click Listener
* Resource Management
* Kotlin Variables
* Event Handling

---

# Flow of the App

```text
App Starts
      ↓
onCreate()
      ↓
Buttons Connected
      ↓
User Clicks Button
      ↓
Click Listener Executes
      ↓
Background Color Changes
```

---

# Important Points

* `onCreate()` runs first.
* `findViewById()` connects XML with Kotlin.
* `setOnClickListener()` handles clicks.
* `setBackgroundResource()` changes the background.
* `LinearLayout` acts as the parent layout.

---


# Revision Notes

* Activity is a screen.
* onCreate() starts the activity.
* XML creates UI.
* Kotlin controls the UI.
* Click listeners handle user actions.
* Resources store colors, strings, and images.


# XML Explanation

## activity_main.xml

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
android:id="@+id/l_layout"
```

### Meaning

Gives the layout a unique name.

### Simple English

Kotlin uses this ID to find the layout.

---

## Layout Width

```xml
android:layout_width="match_parent"
```

### Meaning

The layout takes the full width of the screen.

### Simple English

The layout stretches from left to right.

---

## Layout Height

```xml
android:layout_height="match_parent"
```

### Meaning

The layout takes the full height of the screen.

### Simple English

The layout covers the whole screen.

---

## Orientation

```xml
android:orientation="vertical"
```

### Meaning

Views are arranged from top to bottom.

### Simple English

Items appear one below another.

---

## Gravity

```xml
android:gravity="bottom"
```

### Meaning

Places child views at the bottom of the layout.

### Simple English

The buttons appear at the bottom of the screen.

---

# Inner LinearLayout

```xml
<LinearLayout
    android:orientation="horizontal">
```

### Meaning

Places views side by side.

### Simple English

Buttons appear in a single row.

---

## Button

```xml
<Button
    android:id="@+id/btnblack"
```

### Meaning

Creates a button and gives it an ID.

### Simple English

This creates the black color button.

---

## Width

```xml
android:layout_width="50dp"
```

### Meaning

Sets the button width.

### Simple English

The button width is 50dp.

---

## Height

```xml
android:layout_height="50dp"
```

### Meaning

Sets the button height.

### Simple English

The button height is 50dp.

---

## Margin

```xml
android:layout_margin="5dp"
```

### Meaning

Adds space around the button.

### Simple English

There is a small gap between buttons.

---

## Layout Weight

```xml
android:layout_weight="1"
```

### Meaning

Distributes equal space among all buttons.

### Simple English

All buttons get equal width.

---

## Background Tint

```xml
android:backgroundTint="@color/black"
```

### Meaning

Changes the button color.

### Simple English

The button becomes black.

---

## Corner Radius

```xml
app:cornerRadius="8dp"
```

### Meaning

Rounds the corners of the button.

### Simple English

The button corners become smooth.

---

## Stroke Width

```xml
app:strokeWidth="2dp"
```

### Meaning

Sets the border thickness.

### Simple English

The button gets a 2dp border.

---

## Stroke Color

```xml
app:strokeColor="#FF0000"
```

### Meaning

Changes the border color.

### Simple English

The border becomes red.

---

# Concepts Used

* LinearLayout
* Vertical Orientation
* Horizontal Orientation
* Layout Width
* Layout Height
* Gravity
* Margin
* Layout Weight
* Button Widget
* Background Tint
* Corner Radius
* Stroke Color
* Resource Management

---

# Important Points

* The outer LinearLayout controls the entire screen.
* The inner LinearLayout arranges buttons horizontally.
* `layout_weight` gives equal space to all buttons.
* `backgroundTint` changes the button color.
* `gravity="bottom"` places buttons at the bottom.
* IDs connect XML views with Kotlin code.

---

# Revision Notes

* `match_parent` = full available space.
* `wrap_content` = size according to content.
* `vertical` = top to bottom.
* `horizontal` = left to right.
* `layout_weight` = equal space distribution.
* `backgroundTint` = button color.
* IDs are used by `findViewById()`.


# Interview Questions and Answers

## 1. What is an Activity?

### Answer:

An Activity is a single screen in an Android application. Every screen that the user sees is usually an Activity.

**Example:** Login screen, Home screen, Settings screen.

---

## 2. What is AppCompatActivity?

### Answer:

AppCompatActivity is a base class for activities. It provides compatibility features so that the application works on older Android versions.

```kotlin
class MainActivity : AppCompatActivity()
```

---

## 3. What is onCreate()?

### Answer:

`onCreate()` is a lifecycle method that is called when the activity is created.

```kotlin
override fun onCreate(savedInstanceState: Bundle?)
```

This is the first method where we write our code.

---

## 4. What is Bundle?

### Answer:

Bundle is used to store and pass data between activities or save activity state.

```kotlin
savedInstanceState: Bundle?
```

---

## 5. What is setContentView()?

### Answer:

It connects the XML layout with the Kotlin activity.

```kotlin
setContentView(R.layout.activity_main)
```

---

## 6. What is findViewById()?

### Answer:

It finds a view from the XML layout using its ID.

```kotlin
val buttonBlack = findViewById<Button>(R.id.btnblack)
```

---

## 7. What is a Button?

### Answer:

A Button is a UI component that performs an action when the user clicks it.

```xml
<Button />
```

---

## 8. What is LinearLayout?

### Answer:

LinearLayout is a ViewGroup that arranges its child views vertically or horizontally.

```xml
android:orientation="vertical"
```

---

## 9. What is android:orientation?

### Answer:

It determines how views are arranged.

* vertical → top to bottom
* horizontal → left to right

---

## 10. What is android:gravity?

### Answer:

Gravity controls the position of child views inside a layout.

```xml
android:gravity="bottom"
```

This places the buttons at the bottom.

---

## 11. What is android:layout_weight?

### Answer:

It distributes available space equally among views.

```xml
android:layout_weight="1"
```

All buttons receive equal width.

---

## 12. What is android:backgroundTint?

### Answer:

It changes the color of the button.

```xml
android:backgroundTint="@color/red"
```

---

## 13. What is setOnClickListener()?

### Answer:

It listens for click events.

```kotlin
buttonBlack.setOnClickListener {
}
```

The code inside it runs when the button is clicked.

---

## 14. What is setBackgroundResource()?

### Answer:

It changes the background using a resource.

```kotlin
layout.setBackgroundResource(R.color.black)
```

---

## 15. What is a Resource in Android?

### Answer:

Resources are files stored inside the `res` folder.

Examples:

* colors.xml
* strings.xml
* drawable
* layouts

---

## 16. Why do we use IDs in XML?

### Answer:

IDs uniquely identify views.

```xml
android:id="@+id/btnblack"
```

Kotlin uses these IDs with `findViewById()`.

---

## 17. What is enableEdgeToEdge()?

### Answer:

`enableEdgeToEdge()` allows the application to use the entire screen, including the system bar area.

The **system bar area** consists of:

- **Status Bar (Top)** → Shows battery, time, Wi-Fi, notifications, etc.
- **Navigation Bar (Bottom)** → Shows Back, Home, and Recent Apps buttons.

Without `enableEdgeToEdge()`, the app starts below these bars.

With `enableEdgeToEdge()`, the app can draw behind these bars, giving the application a modern full-screen appearance.

```text
┌─────────────────────────┐
│ 🔋  📶  🕒             │  ← Status Bar
├─────────────────────────┤
│                         │
│      Your App UI        │
│                         │
├─────────────────────────┤
│ ◀   ○   ■              │  ← Navigation Bar
└─────────────────────────┘
```

```kotlin
enableEdgeToEdge()
```

### Simple English

This function allows the app to use the complete screen, including the areas behind the status bar and navigation bar.

---

## 18. What is a Click Event?

### Answer:

A click event occurs when the user presses a button.

Example:

```kotlin
buttonBlack.setOnClickListener {
    layout.setBackgroundResource(R.color.black)
}
```

---

## 19. What is match_parent?

### Answer:

The view occupies all available space.

```xml
android:layout_width="match_parent"
```

---

## 20. What is wrap_content?

### Answer:

The view takes only the required space.

```xml
android:layout_height="wrap_content"
```

---

## 21. What is a ViewGroup?

### Answer:

A ViewGroup is a container that holds other views.

Examples:

* LinearLayout
* ConstraintLayout
* RelativeLayout

---

## 22. What is the purpose of IDs?

### Answer:

IDs allow Kotlin code to access XML views.

Without IDs, `findViewById()` cannot work.

---

## 23. Explain the flow of this application.

### Answer:

1. Application starts.
2. `onCreate()` executes.
3. XML layout loads.
4. Buttons are connected.
5. User clicks a button.
6. Click listener executes.
7. Background color changes.

---

## 24. Which concepts are used in this project?

### Answer:

* Activity
* AppCompatActivity
* Bundle
* LinearLayout
* Button
* Resource Management
* Event Handling
* Click Listener
* findViewById
* XML Layout
* Kotlin Variables

---

## 25. How can this project be improved?

### Answer:

In the current project, we write the same code many times.

```kotlin
buttonBlack.setOnClickListener {
    layout.setBackgroundResource(R.color.black)
}

buttonYellow.setOnClickListener {
    layout.setBackgroundResource(R.color.yellow)
}

buttonRed.setOnClickListener {
    layout.setBackgroundResource(R.color.red)
}
```

The only thing changing is the color.

To reduce repeated code, we can create a function.

```kotlin
private fun changeColor(color: Int) {
    layout.setBackgroundResource(color)
}
```

### Explanation

#### `changeColor`

This is the function name.

Its job is to change the background color.

---

#### `color: Int`

The variable `color` stores an integer value.

In Android:

```kotlin
R.color.black
R.color.red
R.color.blue
```

are integer resource IDs.

For example:

```text
R.color.black → 2131034112
R.color.red   → 2131034113
```

Android automatically creates these numbers.

---

#### `layout.setBackgroundResource(color)`

This line uses the resource ID stored in `color` and changes the background.

---

### Using the Function

```kotlin
buttonBlack.setOnClickListener {
    changeColor(R.color.black)
}

buttonYellow.setOnClickListener {
    changeColor(R.color.yellow)
}

buttonRed.setOnClickListener {
    changeColor(R.color.red)
}
```

When the user clicks the black button:

1. `R.color.black` is passed to the function.
2. The value is stored in `color`.
3. `setBackgroundResource()` uses that value.
4. The background changes.

---

### Flow

```text
Button Click
      ↓
R.color.black
      ↓
Passed to changeColor()
      ↓
Stored in color variable
      ↓
setBackgroundResource(color)
      ↓
Background changes
```

---

### Advantages

- Reduces repeated code.
- Makes the code shorter.
- Improves readability.
- Makes future changes easier.
- Promotes code reusability.

---


**Q: Why do we use a function here?**

**Answer:**

We use a function to avoid writing the same code multiple times. The function receives the color resource ID as an integer and changes the background color. This makes the code cleaner, reusable, and easier to maintain.


---

## 26. What is LinearLayout?

### Answer:

LinearLayout is a ViewGroup that arranges its child views in a single direction.

It can arrange views:

- Vertically (top to bottom)
- Horizontally (left to right)

```xml
<LinearLayout
    android:orientation="vertical">
```

### Example:

- Login form
- Button row
- Simple menus

### Advantage:

Easy to understand and use.

### Disadvantage:

Multiple nested LinearLayouts can reduce performance.

---

## 27. What is ConstraintLayout?

### Answer:

ConstraintLayout is a ViewGroup that positions views using constraints.

Each view can be connected to:

- Parent layout
- Another view

```xml
app:layout_constraintTop_toTopOf="parent"
app:layout_constraintStart_toStartOf="parent"
```

### Example:

- Modern Android applications
- Complex UI designs

### Advantage:

- Better performance
- Less nested layouts
- Flexible design

### Disadvantage:

Slightly difficult for beginners.

---

## 28. What is RelativeLayout?

### Answer:

RelativeLayout is a ViewGroup that positions views relative to other views.

Examples:

```xml
android:layout_below="@id/textView"
android:layout_toEndOf="@id/button"
```

### Example:

- Image beside text
- Button below a TextView

### Advantage:

Less nesting compared to LinearLayout.

### Disadvantage:

Complex layouts become difficult to manage.

---

## Comparison Question

### Q: What is the difference between LinearLayout, RelativeLayout, and ConstraintLayout?

| Layout | Arrangement Method | Performance | Complexity |
|--------|------------------|------------|------------|
| LinearLayout | Vertical or Horizontal | Good | Easy |
| RelativeLayout | Relative to other views | Better | Medium |
| ConstraintLayout | Constraints | Best | Moderate |

---


### Q: Which layout is mostly used in modern Android development?

### Answer:

ConstraintLayout is mostly used because:

- Better performance
- Flat view hierarchy
- Flexible UI design
- Recommended by Google

---


### Q: When should we use LinearLayout?

### Answer:

LinearLayout is best for simple layouts where views need to be arranged in a single row or a single column.

---


### Q: Why is ConstraintLayout preferred over RelativeLayout?

### Answer:

ConstraintLayout provides better performance, fewer nested views, and more flexible positioning than RelativeLayout.






