# Material Design Components (MDC)

* [Material Design Codelab #1](https://codelabs.developers.google.com/codelabs/mdc-101-java/index.html#0)
    * [My Version #1](https://github.com/Gonzz-96/material-design-codelab/tree/101-starter)
* [Material Design Codelab #2](https://codelabs.developers.google.com/codelabs/mdc-102-kotlin/#0)
    * [My version #2](https://github.com/Gonzz-96/material-design-codelab/tree/102-starter)
* [Material Design Codelab #3](https://codelabs.developers.google.com/codelabs/mdc-103-kotlin/)
    * [My Version #3](https://github.com/Gonzz-96/material-design-codelab/tree/103-starter)

This components help to build beautiful layouts in Android, iOs, Web and Flutter.

They are designed according to the Google standards.

Material Design dependency: `api 'com.google.android.material:material:1.1.0-alpha06'`


### TextInputLayout & TextInputEditText

The TextInput in MDC include built-in funcionalitites to show floating labels and error message.

TODO: checkout this [article](https://material.io/components/text-fields/)

To use the MDC, it's necessary to include a `TextInputLayout` with a `TextInputEditText` child:

```
<com.google.android.material.textfield.TextInputLayout
   android:layout_width="match_parent"
   android:layout_height="wrap_content"
   android:layout_margin="4dp"
   android:hint="@string/shr_hint_username">

   <com.google.android.material.textfield.TextInputEditText
       android:layout_width="match_parent"
       android:layout_height="wrap_content" />

</com.google.android.material.textfield.TextInputLayout>
```

`TextInputLayout` components provide built-in error feedback functionality.

`app:errorEnabled` will add extra spacing for error messages

MDC Text Field features include:

* Displaying built-in error feedback
* Supporting a toggle for password visibility using `app:passwordToggleEnabled`
* Offering built-in helper text functionality using `app:helperText`
* Displaying total and max character counts using `app:counterEnabled` and `app:counterMaxLength`

To show an error message:

```
<variable-name>.error = <value>
```

### MaterialButton

MDC Button features include:

* Built-in touch feedback (called the MDC Ripple) by default
* Default elevation
* Customizable corner radius and stroke

<hr>

### TopAppBar

[AppBar docs](https://material.io/components/app-bars-bottom/)

To add an AppBar, include:

```
<com.google.android.material.appbar.AppBarLayout
   android:layout_width="match_parent"
   android:layout_height="wrap_content">

   <androidx.appcompat.widget.Toolbar
       android:id="@+id/app_bar"
       style="@style/Widget.Shrine.Toolbar"
       android:layout_width="match_parent"
       android:layout_height="?attr/actionBarSize"
       app:title="@string/shr_app_name" />
</com.google.android.material.appbar.AppBarLayout>
```

TODO: read about [action buttons](https://developer.android.com/training/appbar/actions)

To create a menu, the function `override fun onCreateOptionsMenu(menu: Menu, inflater: MenuInflater)` must be overriden. In it, we must inflate the menu using the menu layout resource, like this:

```
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto">
    <item
        android:id="@+id/search"
        android:icon="@drawable/shr_search"
        android:title="@string/shr_search_title"
        app:showAsAction="always" />
    <item
        android:id="@+id/filter"
        android:icon="@drawable/shr_filter"
        android:title="@string/shr_filter_title"
        app:showAsAction="always" />
</menu>

```

### MaterialCardView

[Docs](https://material.io/components/cards/)
Usage:

```
<com.google.android.material.card.MaterialCardView
        android:layout_width="160dp"
        android:layout_height="180dp"
        android:layout_marginBottom="16dp"
        android:layout_marginLeft="16dp"
        android:layout_marginRight="16dp"
        android:layout_marginTop="70dp"
        app:cardBackgroundColor="?attr/colorPrimaryDark"
        app:cardCornerRadius="4dp">

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_gravity="bottom"
            android:background="#FFFFFF"
            android:orientation="vertical"
            android:padding="8dp">

            <TextView
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:padding="2dp"
                android:text="@string/shr_product_title"
                android:textAppearance="?attr/textAppearanceHeadline6" />

            <TextView
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:padding="2dp"
                android:text="@string/shr_product_description"
                android:textAppearance="?attr/textAppearanceBody2" />
        </LinearLayout>
    </com.google.android.material.card.MaterialCardView>
```
The MaterialCardView can contain any elements inside of it.

For animations, we create an xml files in res/animator like this:

```
<?xml version="1.0" encoding="utf-8"?>
<selector xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">

    <!-- Pressed state -->
    <item
        android:state_enabled="true"
        android:state_pressed="true">
        <set>
            <objectAnimator
                android:duration="100"
                android:propertyName="translationZ"
                android:valueTo="2dp"
                android:valueType="floatType" />
            <objectAnimator
                android:duration="0"
                android:propertyName="elevation"
                android:valueTo="6dp"
                android:valueType="floatType" />
        </set>
    </item>
```