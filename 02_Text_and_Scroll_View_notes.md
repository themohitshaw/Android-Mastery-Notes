# Project: 02 Text and ScrollView

## Project Repository

**GitHub Project:**

```text
https://github.com/themohitshaw/Android-Mastery/tree/main/02%20TextAndScrollView
```

---

## Project Information

* **Project Number:** 02
* **Project Name:** Text and ScrollView
* **Technology:** Kotlin, XML
* **IDE:** Android Studio

---

## Objective

This project demonstrates how to display images and large amounts of text using ImageView, TextView, and ScrollView.

The user can scroll long text while viewing images placed above and below the content.

---

## Complete Code

### MainActivity.kt

```kotlin
package com.example.textandscrollview

import android.os.Bundle
import androidx.activity.enableEdgeToEdge
import androidx.appcompat.app.AppCompatActivity
import androidx.core.view.ViewCompat
import androidx.core.view.WindowInsetsCompat

class MainActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        enableEdgeToEdge()

        setContentView(R.layout.activity_main)

        ViewCompat.setOnApplyWindowInsetsListener(
            findViewById(R.id.main)
        ) { v, insets ->

            val systemBars =
                insets.getInsets(
                    WindowInsetsCompat.Type.systemBars()
                )

            v.setPadding(
                systemBars.left,
                systemBars.top,
                systemBars.right,
                systemBars.bottom
            )

            insets
        }
    }
}
```

---

### activity_main.xml

```xml
<LinearLayout
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">

    <ImageView
        android:id="@+id/imageView1"
        android:layout_width="match_parent"
        android:layout_height="200dp"
        android:layout_margin="10dp"
        android:layout_gravity="center"
        android:src="@drawable/mohit2024" />

    <ScrollView
        android:layout_width="match_parent"
        android:layout_height="150dp">

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="150dp"
            android:text="Long Text Here"
            android:layout_gravity="center"/>
    </ScrollView>

    <ImageView
        android:id="@+id/imageView2"
        android:layout_width="match_parent"
        android:layout_height="200dp"
        android:layout_margin="10dp"
        android:layout_gravity="center"
        android:src="@drawable/mohit2024" />

</LinearLayout>
```

---

# Line by Line Explanation

## Line 1

```kotlin
package com.example.textandscrollview
```

### Meaning

This tells Android that the file belongs to the textandscrollview package.

### Simple English

The file lives inside the textandscrollview folder.

---

## Line 2

```kotlin
import android.os.Bundle
```

### Meaning

Bundle stores activity data.

### Simple English

It carries information to the activity.

---

## Line 3

```kotlin
import androidx.activity.enableEdgeToEdge
```

### Meaning

Allows the app to use the full screen.

### Simple English

The app uses the complete display area.

---

## Line 4

```kotlin
import androidx.appcompat.app.AppCompatActivity
```

### Meaning

Provides Activity features.

### Simple English

MainActivity becomes an Android screen.

---

## Line 5

```kotlin
import androidx.core.view.ViewCompat
```

### Meaning

Provides compatibility support for views.

### Simple English

Helps views work correctly on all Android versions.

---

## Line 6

```kotlin
import androidx.core.view.WindowInsetsCompat
```

### Meaning

Handles system bar spaces.

### Simple English

It manages the status bar and navigation bar area.

---

# Class

```kotlin
class MainActivity : AppCompatActivity()
```

### Meaning

Creates the main screen.

### Simple English

This is the first screen of the application.

---

# onCreate()

```kotlin
override fun onCreate(savedInstanceState: Bundle?)
```

### Meaning

Runs when the application starts.

### Simple English

Android starts the code here.

---

# Super

```kotlin
super.onCreate(savedInstanceState)
```

### Meaning

Calls the parent activity.

### Simple English

Android performs its setup first.

---

# Edge to Edge

```kotlin
enableEdgeToEdge()
```

### Meaning

Allows the app to use the entire screen.

### Simple English

The app uses the full display.

---

# XML Connection

```kotlin
setContentView(R.layout.activity_main)
```

### Meaning

Connects XML with Kotlin.

### Simple English

Displays activity_main.xml.

---

# findViewById()

```kotlin
findViewById(R.id.main)
```

### Meaning

Finds the main layout.

### Simple English

Kotlin gets access to the layout.

---

# Window Insets

```kotlin
WindowInsetsCompat.Type.systemBars()
```

### Meaning

Gets the system bar area.

### Simple English

Finds the space used by the status and navigation bars.

---

# Padding

```kotlin
v.setPadding()
```

### Meaning

Adds space inside the layout.

### Simple English

Prevents views from hiding behind system bars.

---

# Concepts Used

* Activity
* AppCompatActivity
* Bundle
* LinearLayout
* ImageView
* TextView
* ScrollView
* ViewCompat
* WindowInsetsCompat
* Resource Management
* Edge-to-Edge Design

---

# Flow of the App

```text
App Starts
      ↓
onCreate()
      ↓
XML Loads
      ↓
ImageView Displays Image
      ↓
TextView Displays Text
      ↓
User Scrolls Content
```

---

# Important Points

* ScrollView provides scrolling.
* TextView displays large text.
* ImageView displays images.
* LinearLayout arranges views vertically.
* enableEdgeToEdge() uses the full screen.
* WindowInsets prevent overlapping.

---

# Revision Notes

* Activity is a screen.
* XML creates UI.
* Kotlin controls the UI.
* ScrollView enables scrolling.
* ImageView shows images.
* TextView shows text.

---

# XML Explanation

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

Kotlin uses this ID.

---

## Layout Width

```xml
android:layout_width="match_parent"
```

### Meaning

Uses full width.

### Simple English

Stretches from left to right.

---

## Layout Height

```xml
android:layout_height="match_parent"
```

### Meaning

Uses full height.

### Simple English

Covers the screen.

---

## Orientation

```xml
android:orientation="vertical"
```

### Meaning

Views appear vertically.

### Simple English

One below another.

---

## ImageView

```xml
<ImageView
```

### Meaning

Displays an image.

### Simple English

Shows a picture.

---

## android:src

```xml
android:src="@drawable/mohit2024"
```

### Meaning

Loads the image.

### Simple English

Displays the drawable image.

---

## ScrollView

```xml
<ScrollView
```

### Meaning

Allows vertical scrolling.

### Simple English

The user can scroll.

---

## TextView

```xml
<TextView
```

### Meaning

Displays text.

### Simple English

Shows written content.

---

## layout_margin

```xml
android:layout_margin="10dp"
```

### Meaning

Adds outer spacing.

### Simple English

Creates gaps between views.

---

## layout_gravity

```xml
android:layout_gravity="center"
```

### Meaning

Positions the view.

### Simple English

Places the view in the center.

---

# Concepts Used

* LinearLayout
* ImageView
* ScrollView
* TextView
* Layout Width
* Layout Height
* Orientation
* Margin
* Gravity
* Drawable Resources
* Resource Management
* Edge-to-Edge Design

---

# Important Points

* The outer LinearLayout controls the entire screen.
* ImageView displays images from the drawable folder.
* ScrollView allows vertical scrolling.
* ScrollView can contain only one direct child.
* TextView stores the long text content.
* `layout_margin` creates spacing around views.
* `layout_gravity` controls view position.
* `match_parent` occupies the available space.
* `wrap_content` uses only the required space.
* IDs connect XML views with Kotlin code.
* Drawable resources are stored inside the `drawable` folder.

---

# Revision Notes

* `match_parent` = full available space.
* `wrap_content` = size according to content.
* `vertical` = top to bottom.
* `ImageView` = displays images.
* `TextView` = displays text.
* `ScrollView` = provides scrolling.
* `layout_margin` = outside spacing.
* `layout_gravity` = view position.
* IDs are used by `findViewById()`.
* Drawables store images.

---


# Interview Questions and Answers

## 1. What is an Activity?

An Activity represents a single screen in Android.

---

## 2. What is AppCompatActivity?

It provides backward compatibility.

---

## 3. What is onCreate()?

The first lifecycle method that runs when the activity starts.

---

## 4. What is Bundle?

Bundle stores activity data.

---

## 5. What is enableEdgeToEdge()?

Allows the app to use the complete screen.

---

## 6. What is setContentView()?

Connects XML with Kotlin.

---

## 7. What is findViewById()?

Finds a view using its ID.

---

## 8. What is ViewCompat?

Provides compatibility support for views.

---

## 9. What is WindowInsetsCompat?

Handles system bar spaces.

---

## 10. What is LinearLayout?

Arranges views vertically or horizontally.

---

## 11. What is ScrollView?

Provides vertical scrolling.

---

## 12. Why do we use ScrollView?

To display large content.

---

## 13. How many direct children can ScrollView have?

Only one direct child.

---

## 14. What is TextView?

Displays text.

---

## 15. What is ImageView?

Displays images.

---

## 16. What is android:src?

Specifies the image resource.

---

## 17. What is android:orientation?

Determines the direction of views.

---

## 18. What is match_parent?

Occupies all available space.

---

## 19. What is wrap_content?

Uses only required space.

---

## 20. What is layout_margin?

Adds space outside a view.

---

## 21. What is layout_gravity?

Positions a view inside its parent.

---

## 22. What is a Resource?

Files stored inside the res folder.

Examples:

* drawable
* layout
* values

---

## 23. What is the purpose of IDs?

IDs allow Kotlin to access XML views.

---

## 24. Explain the application flow.

1. Application starts.
2. onCreate() executes.
3. XML loads.
4. Images appear.
5. Text loads.
6. User scrolls.

---

## 25. Which concepts are used?

* Activity
* Bundle
* LinearLayout
* ImageView
* TextView
* ScrollView
* WindowInsets
* Edge-to-Edge

---

# Advantages of ScrollView

* Displays large content.
* Improves user experience.
* Easy to implement.
* Useful for profile pages.
* Useful for article pages.

---

# Application Structure

```text
LinearLayout
│
├── ImageView
│
├── ScrollView
│     │
│     └── TextView
│
└── ImageView
```

---

# Real-Life Uses

* Profile Screen
* About Page
* Biography Page
* News Articles
* Terms and Conditions
* Blog Applications

---
