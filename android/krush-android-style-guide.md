# Krush Android Style Guide

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**

- [1. Project guidelines](#1-project-guidelines)
  - [1.1 Project structure](#11-project-structure)
  - [1.2 File naming](#12-file-naming)
    - [1.2.1 Class files](#121-class-files)
    - [1.2.2 Resources files](#122-resources-files)
      - [1.2.2.1 Drawable files](#1221-drawable-files)
      - [1.2.2.2 Layout files](#1222-layout-files)
      - [1.2.2.3 Menu files](#1223-menu-files)
      - [1.2.2.4 Values files](#1224-values-files)
- [2 Code guidelines](#2-code-guidelines)
  - [2.1 Java language rules](#21-java-language-rules)
    - [2.1.1 Don't ignore exceptions](#211-dont-ignore-exceptions)
    - [2.1.2 Don't catch generic exception](#212-dont-catch-generic-exception)
    - [2.1.3 Don't use finalizers](#213-dont-use-finalizers)
    - [2.1.4 Fully qualify imports](#214-fully-qualify-imports)
  - [2.2 Java style rules](#22-java-style-rules)
    - [2.2.1 Fields definition and naming](#221-fields-definition-and-naming)
    - [2.2.2 Treat acronyms as words](#222-treat-acronyms-as-words)
    - [2.2.3 Use spaces for indentation](#223-use-spaces-for-indentation)
    - [2.2.4 Use standard brace style](#224-use-standard-brace-style)
    - [2.2.5 Annotations](#225-annotations)
      - [2.2.5.1 Annotations practices](#2251-annotations-practices)
      - [2.2.5.2 Annotations style](#2252-annotations-style)
    - [2.2.6 Limit variable scope](#226-limit-variable-scope)
    - [2.2.7 Order import statements](#227-order-import-statements)
    - [2.2.8 Logging guidelines](#228-logging-guidelines)
    - [2.2.9 Class member ordering](#229-class-member-ordering)
    - [2.2.10 Parameter ordering in methods](#2210-parameter-ordering-in-methods)
    - [2.2.11 Arguments in Fragments and Activities](#2211-arguments-in-fragments-and-activities)
    - [2.2.12 Line length limit](#2212-line-length-limit)
      - [2.2.12.1 Line-wrapping strategies](#22121-line-wrapping-strategies)
    - [2.2.13 Increment/Decrement Operators](#2213-incrementdecrement-operators)
    - [2.2.14 Conditional Statements] (#2214-conditional-statements)
  - [2.3 XML style rules](#23-xml-style-rules)
    - [2.3.1 Resources naming](#231-resources-naming)
      - [2.3.1.1 ID naming](#2311-id-naming)
      - [2.3.1.2 Strings](#2312-strings)
      - [2.3.1.3 Styles and Themes](#2313-styles-and-themes)
      - [2.3.1.4 Colors](#2314-colors)
    - [2.3.2 Attributes ordering](#232-attributes-ordering)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# 1. Project guidelines

## 1.1 Project structure

New projects should follow the Android Gradle project structure that is defined on the [Android Gradle plugin user guide](http://tools.android.com/tech-docs/new-build-system/user-guide#TOC-Project-Structure).

## 1.2 File naming

### 1.2.1 Class files
Class names are written in [UpperCamelCase](http://en.wikipedia.org/wiki/CamelCase). With the exception of names of our branded products. For example, a class name with ooVoo is allowed and does not have to be Oovoo.

For classes that extend an Android component, the name of the class should end with the name of the component; for example: `SignInActivity`, `SignInFragment`, `ImageUploaderService`, `ChangePasswordDialog`.

### 1.2.2 Resources files

Resources file names are written in __lowercase_underscore__.

#### 1.2.2.1 Drawable files

Naming conventions for drawables:


| Asset Type   | Prefix            |        Example              |
|--------------| ------------------|-----------------------------|
| Action bar   | `ab_`             | `ab_stacked.9.png`          |
| Button       | `btn_`            | `btn_send_pressed.9.png`    |
| Dialog       | `dialog_`         | `dialog_top.9.png`          |
| Divider      | `divider_`        | `divider_horizontal.9.png`  |
| Icon         | `ic_`             | `ic_star.png`               |
| Menu         | `menu_    `       | `menu_submenu_bg.9.png`     |
| Notification | `notification_`   | `notification_bg.9.png`     |
| Tabs         | `tab_`            | `tab_pressed.9.png`         |

Naming conventions for icons (taken from [Android iconography guidelines](http://developer.android.com/design/style/iconography.html)):

| Asset Type                      | Prefix             | Example                      |
| --------------------------------| ----------------   | ---------------------------- |
| Icons                           | `ic_`              | `ic_star.png`                |
| Launcher icons                  | `ic_launcher`      | `ic_launcher_calendar.png`   |
| Menu icons and Action Bar icons | `ic_menu`          | `ic_menu_archive.png`        |
| Status bar icons                | `ic_stat_notify`   | `ic_stat_notify_msg.png`     |
| Tab icons                       | `ic_tab`           | `ic_tab_recent.png`          |
| Dialog icons                    | `ic_dialog`        | `ic_dialog_info.png`         |

Naming conventions for selector states:

| State        | Suffix          | Example                     |
|--------------|-----------------|-----------------------------|
| Normal       | `_normal`       | `btn_order_normal.9.png`    |
| Pressed      | `_pressed`      | `btn_order_pressed.9.png`   |
| Focused      | `_focused`      | `btn_order_focused.9.png`   |
| Disabled     | `_disabled`     | `btn_order_disabled.9.png`  |
| Selected     | `_selected`     | `btn_order_selected.9.png`  |


#### 1.2.2.2 Layout files

Layout files should match the name of the Android components that they are intended for but moving the top level component name to the beginning. For example, if we are creating a layout for the `SignInActivity`, the name of the layout file should be `activity_sign_in.xml`.

| Component        | Class Name             | Layout Name                   |
| ---------------- | ---------------------- | ----------------------------- |
| Activity         | `UserProfileActivity`  | `activity_user_profile.xml`   |
| Fragment         | `SignUpFragment`       | `fragment_sign_up.xml`        |
| Dialog           | `ChangePasswordDialog` | `dialog_change_password.xml`  |
| AdapterView item | ---                    | `item_person.xml`             |
| Partial layout   | ---                    | `partial_stats_bar.xml`       |

A slightly different case is when we are creating a layout that is going to be inflated by an `Adapter`, e.g to populate a `ListView`. In this case, the name of the layout should start with `item_`.

Note that there are cases where these rules will not be possible to apply. For example, when creating layout files that are intended to be part of other layouts. In this case you should use the prefix `partial_`.

#### 1.2.2.3 Menu files

Similar to layout files, menu files should match the name of the component. For example, if we are defining a menu file that is going to be used in the `UserActivity`, then the name of the file should be `activity_user.xml`

A good practice is to not include the word `menu` as part of the name because these files are already located in the `menu` directory.

#### 1.2.2.4 Values files

Resource files in the values folder should be __plural__, e.g. `strings.xml`, `styles.xml`, `colors.xml`, `dimens.xml`, `attrs.xml`

# 2 Code guidelines

## 2.1 Java language rules

### 2.1.1 Don't ignore exceptions

You must never do the following:

```java
void setServerPort(String value) {
    try {
        serverPort = Integer.parseInt(value);
    } catch (NumberFormatException e) { }
}
```

_While you may think that your code will never encounter this error condition or that it is not important to handle it, ignoring exceptions like above creates mines in your code for someone else to trip over some day. You must handle every Exception in your code in some principled way. The specific handling varies depending on the case._ - ([Android code style guidelines](https://source.android.com/source/code-style.html))

See alternatives [here](https://source.android.com/source/code-style.html#dont-ignore-exceptions).

### 2.1.2 Don't catch generic exception

You should not do this:

```java
try {
    someComplicatedIOFunction();        // may throw IOException
    someComplicatedParsingFunction();   // may throw ParsingException
    someComplicatedSecurityFunction();  // may throw SecurityException
    // phew, made it all the way
} catch (Exception e) {                 // I'll just catch all exceptions
    handleError();                      // with one generic handler!
}
```

See the reason why and some alternatives [here](https://source.android.com/source/code-style.html#dont-catch-generic-exception)

### 2.1.3 Don't use finalizers

_We don't use finalizers. There are no guarantees as to when a finalizer will be called, or even that it will be called at all. In most cases, you can do what you need from a finalizer with good exception handling. If you absolutely need it, define a `close()` method (or the like) and document exactly when that method needs to be called. See `InputStream` for an example. In this case it is appropriate but not required to print a short log message from the finalizer, as long as it is not expected to flood the logs._ - ([Android code style guidelines](https://source.android.com/source/code-style.html#dont-use-finalizers))


### 2.1.4 Fully qualify imports

This is bad: `import foo.*;`

This is good: `import foo.Bar;`

See more info [here](https://source.android.com/source/code-style.html#fully-qualify-imports)

## 2.2 Java style rules

### 2.2.1 Fields definition and naming

Fields should be defined at the __top of the file__ and they should follow the naming rules listed below.

* Private, non-static field names start with __m__.
* Private, static field names start with __s__.
* Other fields start with a lower case letter.
* Static final fields (constants) are ALL_CAPS_WITH_UNDERSCORES.

Example:

```java
public class MyClass {
    public static final int SOME_CONSTANT = 42;
    public int publicField;
    private static MyClass sSingleton;
    int mPackagePrivate;
    private int mPrivate;
    protected int mProtected;
}
```

### 2.2.2 Treat acronyms as words

| Good             | Bad              |
| --------------   | --------------   |
| `XmlHttpRequest` | `XMLHTTPRequest` |
| `getCustomerId`  | `getCustomerID`  |
| `String url`     | `String URL`     |
| `long id`        | `long ID`        |

### 2.2.3 Use spaces for indentation

Use __4 space__ indents for blocks:

```java
if (x == 1) {
    x += 1;
}
```

Use __8 space__ indents for line wraps:

```java
Instrument i =
        someLongExpression(that, wouldNotFit, on, one, line);
```

### 2.2.4 Use standard brace style

Braces go on the same line as the code before them.

```java
class MyClass {
    int func() {
        if (something) {
            // ...
        } else if (somethingElse) {
            // ...
        } else {
            // ...
        }
    }
}
```

Braces around the statements are required unless the condition and the body fit on one line.

This is __good__:

```java
if (condition) {
    body();
}
```

If the condition and the body fit on one line and that line is shorter than the max line length, then braces are not required, e.g.

This is __ok__:

```java
if (condition) body();
```

This is __bad__ and not allowed:

```java
if (condition)
    body();  // bad!
```

### 2.2.5 Annotations

#### 2.2.5.1 Annotations practices

According to the Android code style guide, the standard practices for some of the predefined annotations in Java are:

* `@Override`: The @Override annotation __must be used__ whenever a method overrides the declaration or implementation from a super-class. For example, if you use the @inheritdocs Javadoc tag, and derive from a class (not an interface), you must also annotate that the method @Overrides the parent class's method.

* `@SuppressWarnings`: The @SuppressWarnings annotation should only be used under circumstances where it is impossible to eliminate a warning. If a warning passes this "impossible to eliminate" test, the @SuppressWarnings annotation must be used, so as to ensure that all warnings reflect actual problems in the code.

More information about annotation guidelines can be found [here](http://source.android.com/source/code-style.html#use-standard-java-annotations).

#### 2.2.5.2 Annotations style

__Classes, Methods and Constructors__

When annotations are applied to a class, method, or constructor, they are listed after the documentation block and should appear as __one annotation per line__ .

```java
/* This is the documentation block about the class */
@AnnotationA
@AnnotationB
public class MyAnnotatedClass { }
```

__Fields__

Annotations applying to fields should be listed __on the same line__, unless the line reaches the maximum line length.

```java
@Nullable @Mock DataManager mDataManager;
```

### 2.2.6 Limit variable scope

_The scope of local variables should be kept to a minimum (Effective Java Item 29). By doing so, you increase the readability and maintainability of your code and reduce the likelihood of error. Each variable should be declared in the innermost block that encloses all uses of the variable._

_Local variables should be declared at the point they are first used. Nearly every local variable declaration should contain an initializer. If you don't yet have enough information to initialize a variable sensibly, you should postpone the declaration until you do._ - ([Android code style guidelines](https://source.android.com/source/code-style.html#limit-variable-scope))

### 2.2.7 Order import statements

If you are using an IDE such as Android Studio, you don't have to worry about this because your IDE is already obeying these rules. If not, have a look below.

The ordering of import statements is:

1. Android imports
2. Imports from third parties (com, junit, net, org)
3. java and javax
4. Same project imports

To exactly match the IDE settings, the imports should be:

* Alphabetically ordered within each grouping, with capital letters before lower case letters (e.g. Z before a).
* There should be a blank line between each major grouping (android, com, junit, net, org, java, javax).

More info [here](https://source.android.com/source/code-style.html#limit-variable-scope)

### 2.2.8 Logging guidelines

Use the logging methods provided by the `Log` class to print out error messages or other information that may be useful for developers to identify issues:

* `Log.v(String tag, String msg)` (verbose)
* `Log.d(String tag, String msg)` (debug)
* `Log.i(String tag, String msg)` (information)
* `Log.w(String tag, String msg)` (warning)
* `Log.e(String tag, String msg)` (error)

As a general rule, we use the class name as tag and we define it as a `static final` field at the top of the file. For example:

```java
public class MyClass {
    private static final String TAG = MyClass.class.getSimpleName();

    public myMethod() {
        Log.e(TAG, "My error message");
    }
}
```

VERBOSE and DEBUG logs __must__ be disabled on release builds. It is also recommended to disable INFORMATION, WARNING and ERROR logs but you may want to keep them enabled if you think they may be useful to identify issues on release builds. If you decide to leave them enabled, you have to make sure that they are not leaking private information such as email addresses, user ids, etc.

To only show logs on debug builds:

```java
if (BuildConfig.DEBUG) Log.d(TAG, "The value of x is " + x);
```

### 2.2.9 Class member ordering

There is no single correct solution for this but using a __logical__ and __consistent__ order will improve code learnability and readability. It is recommendable to use the following order:

1. Constants
2. Fields
3. Constructors
4. Override methods and callbacks (public or private)
5. Public methods
6. Private methods
7. Inner classes or interfaces

Example:

```java
public class MainActivity extends Activity {

    private String mTitle;
    private TextView mTextViewTitle;

    public void setTitle(String title) {
        mTitle = title;
    }

    @Override
    public void onCreate() {
        ...
    }

    private void setUpView() {
        ...
    }

    static class AnInnerClass {

    }

}
```

If your class is extending an __Android component__ such as an Activity or a Fragment, it is a good practice to order the override methods so that they __match the component's lifecycle__. For example, if you have an Activity that implements `onCreate()`, `onDestroy()`, `onPause()` and `onResume()`, then the correct order is:

```java
public class MainActivity extends Activity {

    //Order matches Activity lifecycle
    @Override
    public void onCreate() {}

    @Override
    public void onResume() {}

    @Override
    public void onPause() {}

    @Override
    public void onDestroy() {}

}
```

### 2.2.10 Parameter ordering in methods

When programming for Android, it is quite common to define methods that take a `Context`. If you are writing a method like this, then the __Context__ must be the __first__ parameter.

The opposite case are __callback__ interfaces that should always be the __last__ parameter.

Examples:

```java
// Context always goes first
public User loadUser(Context context, int userId);

// Callbacks always go last
public void loadUserAsync(Context context, int userId, UserCallback callback);
```

### 2.2.11 Arguments in Fragments and Activities

When data is passed into an `Activity `or `Fragment` via an `Intent` or a `Bundle`, the keys for the different values __must__ follow the rules described in the section above.

When an `Activity` or `Fragment` expects arguments, it should provide a `public static` method that facilitates the creation of the relevant `Intent` or `Fragment`.

In the case of Activities the method is usually called `getStartIntent()`:

```java
public static Intent getStartIntent(Context context, User user) {
    Intent intent = new Intent(context, ThisActivity.class);
    intent.putParcelableExtra(EXTRA_USER, user);
    return intent;
}
```

For Fragments it is named `newInstance()` and handles the creation of the Fragment with the right arguments:

```java
public static UserFragment newInstance(User user) {
    UserFragment fragment = new UserFragment;
    Bundle args = new Bundle();
    args.putParcelable(ARGUMENT_USER, user);
    fragment.setArguments(args)
    return fragment;
}
```

__Note 1__: These methods should go at the top of the class before `onCreate()`.

__Note 2__: If we provide the methods described above, the keys for extras and arguments should be `private` because there is not need for them to be exposed outside the class.

### 2.2.12 Line length limit

Code lines should not exceed __121 characters__. If the line is longer than this limit there are usually two options to reduce its length:

* Extract a local variable or method (preferable).
* Apply line-wrapping to divide a single line into multiple ones.

There are two __exceptions__ where it is possible to have lines longer than 100:

* Lines that are not possible to split, e.g. long URLs in comments.
* `package` and `import` statements.

#### 2.2.12.1 Line-wrapping strategies

There isn't an exact formula that explains how to line-wrap and quite often different solutions are valid. However there are a few rules that can be applied to common cases.

__Break at operators__

When the line is broken at an operator, the break comes __before__ the operator. For example:

```java
int longName = anotherVeryLongVariable + anEvenLongerOne - thisRidiculousLongOne
        + theFinalOne;
```

__Assignment Operator Exception__

An exception to the `break at operators` rule is the assignment operator `=`, where the line break should happen __after__ the operator.

```java
int longName =
        anotherVeryLongVariable + anEvenLongerOne - thisRidiculousLongOne + theFinalOne;
```

### 2.2.13 Increment/Decrement Operators

We should only use += and -=, and avoid using ++/--. This will help to avoid and confusion around post/pre decrements/increments.

This is __good__:

```java
x += 1;
y -= 1;
```

This is __bad__:

```java
x++;
++x;
y--;
--y;
```
__Exception: for loops usage of increment__

If you are using an older for loop where you need to increment/decrement in the declaration of the for loop that is OK. For example, the following is accept:

```java
for (int i = 0; i < 10; i ++) {
    System.out.println(i);
}
```

### 2.2.14 Conditional Statements

Use appropriate conditional statements for the task at hand. We should prefer `if/else` statements in cases where the result is binary, regardless of the number of conditions.

This is __good__:
```java
if (mColor == Color.GREEN || mColor == Color.BLUE || mColor == Color.RED) {
    return true;
} else {
    return false;
}
```

Use of `switch`'s fallthrough for binary results is __discouraged__:
```java
switch (mColor) {
    case Color.GREEN:
    case Color.BLUE:
    case Color.RED:
        return true;
    default:
        return false;
}
```

For non-binary results, use your best judgment for `if/else/else if` and `switch/case`.

## 2.3 XML style rules

### 2.3.1 Resources naming

Resource IDs and names are written in __lowercase_underscore__.

#### 2.3.1.1 ID naming

IDs should be prefixed with the name of the element in lowercase underscore. For example:


| Element              | Prefix              |
| -----------------    | -----------------   |
| `TextView`           | `text_`             |
| `ImageView`          | `image_`            |
| `Button`             | `button_`           |
| `Menu`               | `menu_`             |

Image view example:

```xml
<ImageView
    android:id="@+id/image_profile"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content" />
```

Menu example:

```xml
<menu>
    <item
        android:id="@+id/menu_done"
        android:title="Done" />
</menu>
```

#### 2.3.1.2 Strings

String names start with a prefix that identifies the section they belong to. For example `registration_email_hint` or `registration_name_hint`. If a string __doesn't belong__ to any section, then you should follow the rules below:


| Prefix               | Description                           |
| -----------------    | --------------------------------------|
| `error_`             | An error message                      |
| `msg_`               | A regular information message         |
| `title_`             | A title, i.e. a dialog title          |
| `action_`            | An action such as "Save" or "Create"  |



#### 2.3.1.3 Styles and Themes

Unless the rest of resources, style names are written in __UpperCamelCase__.

#### 2.3.1.4 Colors

When naming colors, the percentage of opacity should be appended to the color name to delineate between multiple variations of a semitransparent color. For instance, black with 50% alpha (`#80000000`) could be named `black_50`. Solid colors can drop this specification, leaving simply `black`.

### 2.3.2 Attributes ordering

As a general rule you should try to group similar attributes together. A good way of ordering the most common attributes is:

1. View Id
2. Style
3. Layout width and layout height
4. Other layout attributes, sorted alphabetically
5. Remaining attributes, sorted alphabetically
