# Ex.No:2a Develop program to create a text field and a button “Navigate”. When you enter “www.gmail.com” and press navigate button it should open google page using Implicit Intents.


## AIM:

To create a navigate button using Implicit Intent to display the gmail page using Android Studio.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:

1.Start Android Studio and create a new project with an Empty Activity template.

2.Name the project (e.g., exp_2a) and finish setup.

3.Design the UI in activity_main.xml:
         Add an EditText for entering a URL.
         Add a Button labeled "Search".

4.Open MainActivity.java:

5.Declare EditText and Button objects.

6.In the onCreate() method:

         Initialize the objects using findViewById().
         Set an OnClickListener for the button.

7.On button click:

         Get the text entered in the EditText (URL string).
         Create an implicit intent using:
         Intent intent = new Intent(Intent.ACTION_VIEW, Uri.parse(url));
         Start the activity with startActivity(intent).

8.Run the application on an emulator or real device.

9.Enter a URL (e.g., https://www.geeksforgeeks.org) in the EditText.

10.Click the Search button.

11.The system will open the entered URL in a web browser (default app that can handle ACTION_VIEW).

## PROGRAM:
```
/*
Program to print the text “Implicitintent”.
Developed by: RESHMITHAA B
Registeration Number : 212224220080
*/
```

MainActivity.java

```
package com.example.exp_2a;

import androidx.appcompat.app.AppCompatActivity;
import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;

import com.example.exp_2a.R;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {

        EditText editText;
        Button button;

        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        button = findViewById(R.id.btn);
        editText = (EditText) findViewById(R.id.editText);

        button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                String url=editText.getText().toString();
                Intent intent = new Intent(Intent.ACTION_VIEW, Uri.parse(url));
                startActivity(intent);
            }
        });
    }
}
```
activity_main.xml

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <EditText
        android:id="@+id/editText"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/btn"
        android:text="Search"
        android:onClick="search"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/editText"
        tools:ignore="OnClick" />


</androidx.constraintlayout.widget.ConstraintLayout>
```

## OUTPUT

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/a3f45e5f-1b77-4627-b93d-ac3ee5297522" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/abd12c3b-17ad-4c83-bf6f-30b583ac7bce" />





## RESULT
Thus a Simple Android Application create a navigate button using Implicit Intent to display the gmail page using Android Studio is developed and executed successfully.
