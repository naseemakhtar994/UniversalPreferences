# UniversalPreferences
UniversalPreferences is simple Android library that allows you to use Shared Preferences in an easy way. 

The main goal of this library is to reduce boilerplate code when you work with Shared Preferences. You only need to initalize library and then literally in one line of the code you can store or retrive any type of values that Shared Preferences allows.

# Usage

Add to your module's build.gradle:
```
allprojects {
    repositories {
        maven { url "https://jitpack.io" }
    }
}
```
and to your app build.gradle:
```
dependencies {
    compile 'com.github.zookey:universalpreferences:0.0.2'
}
```

First you do need to initalize this libarary inside onCreate of the Application class of your project.
```Java
public class UniversalPreferencesApplication extends Application {

    @Override
    public void onCreate() {
        super.onCreate();
        UniversalPreferences.initialize(this);
    }
}
```
Now you can use UniversalPreferences library in any class of your project.

UniversalPreferences library is "universal" at accepting object types, so there is only one method to store and only one method to retrive values.

###### Store and retrive String
```Java
UniversalPreferences.getInstance().put("string", "some value");
String string =  UniversalPreferences.getInstance().get("string");
```
###### Store and retrive Integer
```Java
UniversalPreferences.getInstance().put("int", 30);
int value =  UniversalPreferences.getInstance().get("int");
```

###### Store and retrive Float
```Java
UniversalPreferences.getInstance().put("float", 3.0f);
float valueFloat = UniversalPreferences.getInstance().get("float");
```

###### Store and retrive Boolean
```Java
UniversalPreferences.getInstance().put("bool", true);
boolean bool = UniversalPreferences.getInstance().get("bool");
```

###### Store and retrive Set<String>
```Java
Set<String> set = new HashSet<String>();
set.add("test 1");
set.add("test 2");
UniversalPreferences.getInstance().put("set", set);
Set<String> savedSet = UniversalPreferences.getInstance().get("set");
```
