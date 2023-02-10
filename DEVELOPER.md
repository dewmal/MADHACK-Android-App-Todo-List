
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

### Create Simple Android App using button and Toast



```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <Button
        android:id="@+id/button"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Button" />
</LinearLayout>
```


```java


        findViewById(R.id.button).setOnClickListener(
                new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                        Log.i("MyActivity", "Hello World");
                    }
                }
        );

```

# Android Studio

## Studio Features

### Logcat
![image](https://user-images.githubusercontent.com/499015/218123400-4ef295cf-bb91-4437-9b67-d8f4c6492430.png)


### Device Manager 
![image](https://user-images.githubusercontent.com/499015/218123522-94a73878-d52a-4dbd-a50a-619429181d53.png)



### Project Structure

![image](https://user-images.githubusercontent.com/499015/218123729-de04b6b1-be3a-464b-b2c8-90d10d35a6b8.png)


### Resource Manager
![image](https://user-images.githubusercontent.com/499015/218123853-abc046e6-f76a-4962-9f84-1063ae9a2421.png)

### Build Varient
![image](https://user-images.githubusercontent.com/499015/218124121-84619df4-1517-48fd-8713-54f3d0760e12.png)



## Emulator And its features

![image](https://user-images.githubusercontent.com/499015/218123239-9aa25fb7-108a-4d08-b472-269158ea9d6c.png)




## Second Example

### Hello World Text Change on Button press

```java
final TextView textView = findViewById(R.id.my_layout_text_view);

        findViewById(R.id.button).setOnClickListener(
                new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                        textView.setText("Hello World 22");
                        Log.i("MyActivity", "Hello World");
                    }
                }
        );
        
```

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <Button
        android:id="@+id/button"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Button" />

    <TextView
        android:id="@+id/my_layout_text_view"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="TextView" />


</LinearLayout>
```

### Example 3 - How to connect with external API

![image](https://user-images.githubusercontent.com/499015/218143117-66045f0a-bc7d-44aa-96f3-533f5bfe30f3.png)



![image](https://user-images.githubusercontent.com/499015/218143902-9f30f55b-1909-4f9b-8be4-aeb2e4be422f.png)


#### Code Examples

```java
package com.syigen.dewmal.madhack.android.todoapp;

import android.app.Activity;
import android.os.Bundle;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

public class MyActivity extends Activity {

    /**
     * Called when the activity is first created.
     */
    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.my_layout);


        EditText etText = findViewById(R.id.my_layout_et_text);
        Button btnTranslate = findViewById(R.id.my_layout_btn_translate);
        TextView tvTranslatedText = findViewById(R.id.my_layout_tv_text);


        btnTranslate.setOnClickListener(v -> {
            String text = etText.getText().toString();
            tvTranslatedText.setText(text);
        });


    }
}

```

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">

    <EditText
        android:id="@+id/my_layout_et_text"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:ems="10"
        android:inputType="textPersonName"
        android:text="Name" />

    <Button
        android:id="@+id/my_layout_btn_translate"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Button" />

    <TextView
        android:id="@+id/my_layout_tv_text"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="TextView" />
</LinearLayout>
```

#### Add permisson to mainefets file
```xml
   <uses-permission
        android:name="android.permission.INTERNET" />
```

### Access thirdparty library

- https://google.github.io/volley/
- https://square.github.io/okhttp/


```groovy
implementation("com.squareup.okhttp3:okhttp:4.10.0")

```

### Send Request to API

```java
package com.syigen.dewmal.madhack.android.todoapp;

import android.app.Activity;
import android.os.Bundle;
import android.util.Log;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

import java.io.IOException;

import okhttp3.FormBody;
import okhttp3.OkHttpClient;
import okhttp3.Request;
import okhttp3.RequestBody;
import okhttp3.Response;

public class MyActivity extends Activity {

    /**
     * Called when the activity is first created.
     */
    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.my_layout);


        EditText etText = findViewById(R.id.my_layout_et_text);
        Button btnTranslate = findViewById(R.id.my_layout_btn_translate);
        TextView tvTranslatedText = findViewById(R.id.my_layout_tv_text);


        btnTranslate.setOnClickListener(v -> {
            String text = etText.getText().toString();


            OkHttpClient client = new OkHttpClient();

            RequestBody body = new FormBody.Builder()
                    .add("source", "en")
                    .add("target", "zh-CN")
                    .add("q", text)
                    .build();

            Request request = new Request.Builder()
                    .url("https://google-translate1.p.rapidapi.com/language/translate/v2")
                    .post(body)
                    .addHeader("content-type", "application/x-www-form-urlencoded")
                    .addHeader("Accept-Encoding", "application/gzip")
                    .addHeader("X-RapidAPI-Key", "UfkFmhNi14mshygPj2wkF6Ti7HN7p19GicSjsneiMcn90aoewZ")
                    .addHeader("X-RapidAPI-Host", "google-translate1.p.rapidapi.com")
                    .build();

            try {
                Response response = client.newCall(request).execute();
                Log.i("Response", response.body().string());
            } catch (IOException e) {
                throw new RuntimeException(e);
            }


            tvTranslatedText.setText(text);
        });


    }
}

```


### How anroid background threads work

https://developer.android.com/guide/background/asynchronous/java-threads

![image](https://user-images.githubusercontent.com/499015/218150991-68dd3c47-c0ca-4045-96f7-89af21bd44cb.png)


```java
package com.syigen.dewmal.madhack.android.todoapp;

import android.app.Activity;
import android.os.Bundle;
import android.os.Handler;
import android.util.JsonReader;
import android.util.Log;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

import java.io.IOException;

import okhttp3.FormBody;
import okhttp3.OkHttpClient;
import okhttp3.Request;
import okhttp3.RequestBody;
import okhttp3.Response;

public class MyActivity extends Activity {

    /**
     * Called when the activity is first created.
     */
    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.my_layout);


        EditText etText = findViewById(R.id.my_layout_et_text);
        Button btnTranslate = findViewById(R.id.my_layout_btn_translate);
        TextView tvTranslatedText = findViewById(R.id.my_layout_tv_text);


        btnTranslate.setOnClickListener(v -> {
            String text = etText.getText().toString();


            new Thread(
                    () -> {
                        OkHttpClient client = new OkHttpClient();

                        RequestBody body = new FormBody.Builder()
                                .add("source", "en")
                                .add("target", "zh-CN")
                                .add("q", text)
                                .build();

                        Request request = new Request.Builder()
                                .url("https://google-translate1.p.rapidapi.com/language/translate/v2")
                                .post(body)
                                .addHeader("content-type", "application/x-www-form-urlencoded")
                                .addHeader("Accept-Encoding", "application/gzip")
                                .addHeader("X-RapidAPI-Key", "UfkFmhNi14mshygPj2wkF6Ti7HN7p19GicSjsneiMcn90aoewZ")
                                .addHeader("X-RapidAPI-Host", "google-translate1.p.rapidapi.com")
                                .build();

                        try {
                            Response response = client.newCall(request).execute();
                            Log.i("Response", response.body().string());
                        } catch (IOException e) {
                            throw new RuntimeException(e);
                        }
                    }
            ).start();


           tvTranslatedText.setText(text);
        });


    }
}
```
 Convert Response string into Json and get Transalated text
```java
 try {
                            Response response = client.newCall(request).execute();
                            String responseString = response.body().string();
                            Log.i("Response", responseString);
                            JSONObject responseJson = new JSONObject(responseString);
                            JSONObject data = responseJson.getJSONObject("data");
                            JSONArray translations = data.getJSONArray("translations");
                            JSONObject translation = translations.getJSONObject(0);
                            String translatedText = translation.getString("translatedText");

                            Log.i("translatedText", translatedText);


                        } catch (IOException e) {
                            throw new RuntimeException(e);
                        } catch (JSONException e) {
                            throw new RuntimeException(e);
                        }
```

new Handler()

**We cant touch background thread to main thread directly so handler is going to collect all events which are available in main thread in a queue and posses this queue to looper class.**

```java
 new Handler().post(() -> tvTranslatedText.setText(translatedText));
 ```



# UI Design
![image](https://user-images.githubusercontent.com/499015/218116763-2c9f1436-9950-44f7-b4fb-1d89e793d4ab.png)

https://www.figma.com/file/DMYi45Gf77sgoTpshwbVjN/Todo-Mobile-App-(Community)-(Community)?node-id=0%3A1&t=0w5cCOsqi2NwYle8-0


```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">

    <RelativeLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:background="@drawable/header"
        android:orientation="horizontal"
        android:padding="24dp">

        <ImageButton
            android:id="@+id/imageButton"
            android:layout_width="50dp"
            android:layout_height="50dp"
            android:background="@drawable/rounded_button"
            app:srcCompat="@drawable/close_x" />

        <TextView
            android:id="@+id/textView"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_centerHorizontal="true"
            android:layout_centerVertical="true"
            android:layout_weight="1"
            android:text="Add New Task"
            android:textSize="24dp"
            android:textColor="#fff" />
    </RelativeLayout>
</LinearLayout>
```

#### Drawable Resources

```xml
<?xml version="1.0" encoding="utf-8"?>
<shape xmlns:android="http://schemas.android.com/apk/res/android"
    android:padding="1dp"
    android:shape="oval">
    <solid android:color="#fff" />
</shape>


```
