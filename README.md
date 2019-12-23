# Kotlin Bottom Navigation
A simple & curved & material bottom navigation for Android written in kotlin

[![](https://jitpack.io/v/hamzaahmedkhan/KBottomNavigation.svg)](https://jitpack.io/#hamzaahmedkhan/KBottomNavigation)


![](https://github.com/hamzaahmedkhan/KBottomNavigation/raw/master/resources/meow-bottom-navigation-normal.gif)

## Download
build.gradle (project path)
```groovy
buildscript {
    repositories {
        jcenter() // this line need
    }
    ....
}
```
build.gradle (module path)
```groovy
dependencies {
  implementation 'com.github.hamzaahmedkhan:KBottomNavigation:1.0.0'
}
```
use androidx by adding this lines to gradle.properties
```properties
android.useAndroidX=true
android.enableJetifier=true
```

## Usage
add Kotlin Bottom Navigation in xml
```xml
    <com.hk.kbottomnavigation.KBottomNavigation
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>
```

add menu items in code.

remember icons must be vector drawable
```kotlin
companion object {
  private const val ID_HOME = 1
  private const val ID_EXPLORE = 2
  private const val ID_MESSAGE = 3
  private const val ID_NOTIFICATION = 4
  private const val ID_ACCOUNT = 5
}
    
    val bottomNavigation = findView(R.id.bottomNavigation)
    bottomNavigation.add(KBottomNavigation.Model(ID_HOME, R.drawable.ic_home))
    bottomNavigation.add(KBottomNavigation.Model(ID_EXPLORE, R.drawable.ic_explore))
    bottomNavigation.add(KBottomNavigation.Model(ID_MESSAGE, R.drawable.ic_message))
    bottomNavigation.add(KBottomNavigation.Model(ID_NOTIFICATION, R.drawable.ic_notification))
    bottomNavigation.add(KBottomNavigation.Model(ID_ACCOUNT, R.drawable.ic_account))

// To set count
    bottomNavigation.setCount(ID_NOTIFICATION, "115")
....
```

## Customization
```xml
    <com.hk.kbottomnavigation.KBottomNavigation
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        app:mbn_backgroundBottomColor="#ffffff"
        app:mbn_countBackgroundColor="#ff6f00"
        app:mbn_countTextColor="#ffffff"
        app:mbn_countTypeface="fonts/SourceSansPro-Regular.ttf"
        app:mbn_defaultIconColor="#90a4ae"
        app:mbn_rippleColor="#2f424242"
        app:mbn_selectedIconColor="#3c415e"
        app:mbn_shadowColor="#1f212121"/>
```

## Listeners
```kotlin
        bottomNavigation.setOnShowListener {
            val name = when (it.id) {
                ID_HOME -> "HOME"
                ID_EXPLORE -> "EXPLORE"
                ID_MESSAGE -> "MESSAGE"
                ID_NOTIFICATION -> "NOTIFICATION"
                ID_ACCOUNT -> "ACCOUNT"
                else -> ""
            }
            tv_selected.text = "$name page is selected"
        }

        bottomNavigation.setOnClickMenuListener {
            val name = when (it.id) {
                ID_HOME -> "HOME"
                ID_EXPLORE -> "EXPLORE"
                ID_MESSAGE -> "MESSAGE"
                ID_NOTIFICATION -> "NOTIFICATION"
                ID_ACCOUNT -> "ACCOUNT"
                else -> ""
            }
```
