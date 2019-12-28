# Material Design Components (MDC)

* [Material Design Codelab #1](https://codelabs.developers.google.com/codelabs/mdc-101-java/index.html#0)
    * [My Version #1](https://github.com/Gonzz-96/material-design-codelab/tree/101-starter)

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

# MaterialButton

MDC Button features include:

* Built-in touch feedback (called the MDC Ripple) by default
* Default elevation
* Customizable corner radius and stroke

<hr>

