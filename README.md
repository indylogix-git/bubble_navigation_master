# Bubble Navigation

## Demos

| FloatingTopBarActivity  | TopBarActivity  |
| ------------- |:-------------:| 
| <img src="https://raw.githubusercontent.com/gauravk95/bubble-navigation/master/sample/bn_two.gif" width="270" height="480"> |<img src="https://raw.githubusercontent.com/gauravk95/bubble-navigation/master/sample/bn_one.gif" width="270" height="480">|

|   BottomBarActivity    |    EqualBottomBarActivity  |
| ------------- |:-------------:| 
| <img src="https://raw.githubusercontent.com/gauravk95/bubble-navigation/master/sample/bn_four.gif" width="270" height="480"> |<img src="https://raw.githubusercontent.com/gauravk95/bubble-navigation/master/sample/bn_three.gif" width="270" height="480">|


### Features:
- Support for API Level 16+ 
- Highly customizable
- Light weight and easy-to-use
- Supports TransitionDrawable for cool state changes
- 2 types of NavigationView for different use cases
    - **BubbleNavigationConstraintView:** supports `spread`, `inside` and `packed` mode
    - **BubbleNavigationLinearView:** allows equal distribution using weight or packed mode
- Bonus **BubbleToggleView** to create new UI components, other than navigation
- Add Badges

## Usage

Check out the Sample app, to see how its implemented.

### Gradle
* This library is available on JCenter. To use it, add the following to `build.gradle`
```gradle
dependencies {
    implementation 'com.gauravk.bubblenavigation:bubblenavigation:1.0.7'
}
```

### XML
```xml
<com.gauravk.bubblenavigation.BubbleNavigationConstraintView
        android:id="@+id/top_navigation_constraint"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginBottom="380dp"
        android:background="@color/white"
        android:elevation="4dp"
        android:padding="12dp"
        app:bnc_mode="spread">

        <com.gauravk.bubblenavigation.BubbleToggleView
            android:id="@+id/c_item_rest"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            app:bt_active="true"
            app:bt_colorActive="@color/search_active"
            app:bt_colorInactive="@color/search_inactive"
            app:bt_icon="@drawable/ic_restaurant"
            app:bt_shape="@drawable/transition_background_drawable_restaurant"
            app:bt_title="@string/restaurant"
            app:bt_padding="@dimen/internal_padding"
            app:bt_titlePadding="@dimen/title_padding" />

         <!-- Add more child items here - max upto 5 -->
    
    </com.gauravk.bubblenavigation.BubbleNavigationConstraintView>
```
| **attr**     | **Description**                                       |
| ------------ | ----------------------------------------------------- | 
| bnc_mode     | Changes the display mode the child elements           |
|              | - **spread** : equally distributes the child elements | 
|              | - **packed** : elements are packed with center gravity|
|              | - **inside** : inside elements are equally distributed|

### OR

```xml
<com.gauravk.bubblenavigation.BubbleNavigationLinearView
        android:id="@+id/bottom_navigation_view_linear"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:background="@color/white"
        android:elevation="8dp"
        android:orientation="horizontal"
        android:padding="12dp">

        <com.gauravk.bubblenavigation.BubbleToggleView
            android:id="@+id/l_item_home"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            app:bt_active="true"
            app:bt_colorActive="@color/home_active"
            app:bt_colorInactive="@color/home_inactive"
            app:bt_icon="@drawable/ic_home"
            app:bt_shape="@drawable/transition_background_drawable_home"
            app:bt_title="@string/home"
            app:bt_padding="@dimen/internal_padding"
            app:bt_titlePadding="@dimen/title_padding" />
  
    <!-- Add more child items here - max upto 5 -->
    
    </com.gauravk.bubblenavigation.BubbleNavigationLinearView>
```

### Activity/Fragment
In Java
```java
  bubbleNavigation.setNavigationChangeListener(new BubbleNavigationChangeListener() {
            @Override
            public void onNavigationChanged(View view, int position) {
                //navigation changed, do something
            }
        });
```
Or in Kotlin
```kotlin
  navigation_view.setNavigationChangeListener { view , position ->
            //navigation changed, do something here
        }
```
| **Method**      | **Description**  |
| ------------- | ------------- | 
| `void setCurrentActiveItem(int position)`  | Changes the current active state for the navigation view | 
| `void setTypeface(Typeface typeface)`   | Updates the typeface of the text  |
| `void setNavigationChangeListener(BubbleNavigationChangeListener listener)` | Sets the navigation change listener|
| `int getCurrentActiveItemPosition()` | Returns the current active position |
| `void setBadgeValue(int position, String value)` | Updates the corresponding badge text value |

## Contribute

Users are welcome to suggest ideas or feature requests, or report bugs and issues [here](https://github.com/gauravk95/bubble-navigation/issues)

I am always open to new suggestions and good contributions.

## Contact

If you want to outsource your Flutter project, email us on info@indylogix.com

# bubble_navigation_master
