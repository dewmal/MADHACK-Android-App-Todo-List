# UI Design
![image](https://user-images.githubusercontent.com/499015/218116763-2c9f1436-9950-44f7-b4fb-1d89e793d4ab.png)

https://www.figma.com/file/DMYi45Gf77sgoTpshwbVjN/Todo-Mobile-App-(Community)-(Community)?node-id=0%3A1&t=0w5cCOsqi2NwYle8-0

# Project implementation


## Activity
- An Android Activity is a fundamental building block of an Android application and represents a single screen or task that the user can interact with

![image](https://user-images.githubusercontent.com/499015/218118924-a07e7221-9737-4670-92d1-dc799aac762c.png)


Here we override oncreate method


Step 1
```java
package com.syigen.dewmal.madhack.android.todoapp;

import android.app.Activity;
import android.os.Bundle;

public class MyActivity extends Activity {

    /**
     * Called when the activity is first created.
     */
    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.my_layout);
    }

}

```

Step 2 Layout file

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent">
</LinearLayout>
```

Step 3 - Manifest File
```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">

    <application
        android:allowBackup="true"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:supportsRtl="true"
        android:theme="@style/Theme.MyTodoApplication"
        tools:targetApi="31">
        <activity
            android:name=".MyActivity"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>


</manifest>
```


