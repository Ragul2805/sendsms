
# Ex.No:3 Design an android application Send SMS using Intent.


## AIM:

To create and design an android application Send SMS using Intent using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as smsintent and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Send SMS and Display details give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
```
/*
Program to create and design an android application Send SMS using Intent.
Developed by: Ragul D
Registeration Number : 212225230221
*/
```
**MainActivity.java**
```
package com.example.sms_app;

import android.os.Bundle;
import android.content.Intent;
import android.net.Uri;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    EditText phonenumber, message;
    Button send;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        send = findViewById(R.id.button);
        phonenumber = findViewById(R.id.editText);
        message = findViewById(R.id.editText2);

        send.setOnClickListener(new View.OnClickListener() {

            @Override
            public void onClick(View view) {

                String number = phonenumber.getText().toString();
                String msg = message.getText().toString();

                if (number.isEmpty() || msg.isEmpty()) {
                    Toast.makeText(getApplicationContext(),
                            "Please fill all fields",
                            Toast.LENGTH_LONG).show();
                }
                else {
                    Intent intent = new Intent(Intent.ACTION_SENDTO);

                    intent.setData(Uri.parse("smsto:" + number));
                    intent.putExtra("sms_body", msg);

                    startActivity(intent);
                }
            }
        });
    }
}

```

**activity_main.xml**
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="60dp"
        android:background="#041B75"
        android:fontFamily="sans-serif-black"
        android:text="SMS Message Sender"
        android:textColor="#FFFFFF"
        android:textSize="26sp"
        android:textStyle="italic"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <TextView
        android:id="@+id/textView2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="60dp"
        android:text="Mobile Number:"
        android:textColor="#000080"
        android:textSize="22sp"
        android:textStyle="bold"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@id/textView" />

    <EditText
        android:id="@+id/editText"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginTop="10dp"
        android:hint="Enter mobile number"
        android:inputType="phone"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@id/textView2" />

    <TextView
        android:id="@+id/edit"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="40dp"
        android:text="Message to be Sent:"
        android:textColor="#1B098C"
        android:textSize="22sp"
        android:textStyle="bold"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@id/editText" />

    <EditText
        android:id="@+id/editText2"
        android:layout_width="0dp"
        android:layout_height="120dp"
        android:layout_marginTop="10dp"
        android:background="#EBE6E6"
        android:gravity="top"
        android:hint="Type something..."
        android:inputType="textMultiLine"
        android:padding="10dp"
        android:textSize="18sp"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@id/edit" />

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="40dp"
        android:text="SEND"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@id/editText2" />

</androidx.constraintlayout.widget.ConstraintLayout>

```

**AndroidManifest.xml**
```
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android">

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:supportsRtl="true"
        android:theme="@style/Theme.Sms_app">

        <activity
            android:name=".MainActivity"
            android:exported="true">

            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>

        </activity>

    </application>

</manifest>

```

## OUTPUT
<img width="1920" height="1020" alt="Screenshot 2026-11-04 125533" src="https://github.com/user-attachments/assets/67406e67-e673-449d-8595-15771b089441" />

<img width="1920" height="1020" alt="Screenshot 2026-11-04 125048" src="https://github.com/user-attachments/assets/118b0eff-38cc-4b53-af00-f2773e41796e" />

<img width="1920" height="1020" alt="Screenshot 2026-11-04 124904" src="https://github.com/user-attachments/assets/03d663bc-e55c-4f7b-8692-d5c97d08b20b" />

<img width="1920" height="1020" alt="Screenshot 2026-11-04 124847" src="https://github.com/user-attachments/assets/9c27ff10-3d74-4fb2-9dba-be9d0d6342a7" />

## RESULT
Thus a Simple Android Application create and design an android application Send SMS using Intent using Android Studio is developed and executed successfully.
