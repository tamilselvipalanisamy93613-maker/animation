# Ex.No: 11 Develop a application to add animations to ImageView,Move,blink,fade,clockwise,zoom,slide operations are perform in android studio.


## AIM:

To develop a application to add animation to imageview,move,blink,fade,clockwise,zoom,slide operation using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:


1. Start.
2. Create a new Android application using Android Studio.
3. Design the layout with ImageView and buttons.
4. Display the cat image in the ImageView.
5. Initialize all animation buttons in MainActivity.
6. Implement Move animation using TranslateAnimation.
7. Implement Blink and Fade animations using AlphaAnimation.
8. Implement Clockwise animation using RotateAnimation.
9. Implement Zoom animation using ScaleAnimation.
10. Implement Slide animation using TranslateAnimation.
11. Run the application and verify all animations.
12. Stop.



## PROGRAM:


Program to display animation operation”.
Developed by: TAMILSELVI P
Registeration Number : 212225040460

## activity_main.xml:
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:padding="20dp"
    android:background="#ECEFF1">

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Animation App"
        android:textSize="26sp"
        android:textStyle="bold"
        android:textColor="#FFFFFF"
        android:gravity="center"
        android:padding="15dp"
        android:background="#455A64"
        android:layout_marginBottom="20dp"/>

    <ImageView
        android:id="@+id/imageView"
        android:layout_width="200dp"
        android:layout_height="200dp"
        android:src="@drawable/ic_launcher_foreground"
        android:contentDescription="Animation Image"
        android:layout_marginBottom="25dp"/>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal">

        <Button
            android:id="@+id/moveButton"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:text="Move"
            android:backgroundTint="#455A64"
            android:textColor="#FFFFFF"/>

        <Button
            android:id="@+id/blinkButton"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:text="Blink"
            android:backgroundTint="#455A64"
            android:textColor="#FFFFFF"/>
    </LinearLayout>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal">

        <Button
            android:id="@+id/fadeButton"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:text="Fade"
            android:backgroundTint="#455A64"
            android:textColor="#FFFFFF"/>

        <Button
            android:id="@+id/rotateButton"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:text="Rotate"
            android:backgroundTint="#455A64"
            android:textColor="#FFFFFF"/>
    </LinearLayout>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal">

        <Button
            android:id="@+id/zoomButton"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:text="Zoom"
            android:backgroundTint="#455A64"
            android:textColor="#FFFFFF"/>

        <Button
            android:id="@+id/slideButton"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:text="Slide"
            android:backgroundTint="#455A64"
            android:textColor="#FFFFFF"/>
    </LinearLayout>

</LinearLayout>
```

## MainActivity.java:
```
package com.example.graphical;

import android.os.Bundle;
import android.view.animation.Animation;
import android.view.animation.TranslateAnimation;
import android.view.animation.AlphaAnimation;
import android.view.animation.RotateAnimation;
import android.view.animation.ScaleAnimation;
import android.widget.Button;
import android.widget.ImageView;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    ImageView imageView;
    Button moveButton, blinkButton, fadeButton,
            rotateButton, zoomButton, slideButton;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        imageView = findViewById(R.id.imageView);
        moveButton = findViewById(R.id.moveButton);
        blinkButton = findViewById(R.id.blinkButton);
        fadeButton = findViewById(R.id.fadeButton);
        rotateButton = findViewById(R.id.rotateButton);
        zoomButton = findViewById(R.id.zoomButton);
        slideButton = findViewById(R.id.slideButton);

        // Move Animation
        moveButton.setOnClickListener(v -> {
            TranslateAnimation move = new TranslateAnimation(
                    0, 300, 0, 0);
            move.setDuration(1000);
            move.setRepeatCount(1);
            move.setRepeatMode(Animation.REVERSE);
            imageView.startAnimation(move);
        });

        // Blink Animation
        blinkButton.setOnClickListener(v -> {
            AlphaAnimation blink = new AlphaAnimation(0, 1);
            blink.setDuration(500);
            blink.setRepeatCount(Animation.INFINITE);
            blink.setRepeatMode(Animation.REVERSE);
            imageView.startAnimation(blink);
        });

        // Fade Animation
        fadeButton.setOnClickListener(v -> {
            AlphaAnimation fade = new AlphaAnimation(1, 0);
            fade.setDuration(1000);
            fade.setRepeatCount(1);
            fade.setRepeatMode(Animation.REVERSE);
            imageView.startAnimation(fade);
        });

        // Clockwise Rotation
        rotateButton.setOnClickListener(v -> {
            RotateAnimation rotate = new RotateAnimation(
                    0, 360,
                    Animation.RELATIVE_TO_SELF, 0.5f,
                    Animation.RELATIVE_TO_SELF, 0.5f);
            rotate.setDuration(1000);
            rotate.setRepeatCount(1);
            imageView.startAnimation(rotate);
        });

        // Zoom Animation
        zoomButton.setOnClickListener(v -> {
            ScaleAnimation zoom = new ScaleAnimation(
                    1, 2, 1, 2,
                    Animation.RELATIVE_TO_SELF, 0.5f,
                    Animation.RELATIVE_TO_SELF, 0.5f);
            zoom.setDuration(1000);
            zoom.setRepeatCount(1);
            zoom.setRepeatMode(Animation.REVERSE);
            imageView.startAnimation(zoom);
        });

        // Slide Animation
        slideButton.setOnClickListener(v -> {
            TranslateAnimation slide = new TranslateAnimation(
                    Animation.RELATIVE_TO_PARENT, 1,
                    Animation.RELATIVE_TO_PARENT, 0,
                    0, 0, 0, 0);
            slide.setDuration(1000);
            imageView.startAnimation(slide);
        });
    }
}
```


## OUTPUT
## Move
<img width="1917" height="1017" alt="Screenshot 2026-11-24 203012" src="https://github.com/user-attachments/assets/2b36e4ba-c249-4673-9fc3-8b3cfe962042" />

## Blink
<img width="1917" height="1077" alt="Screenshot 2026-11-24 203042" src="https://github.com/user-attachments/assets/e1ccaa5a-5097-4c80-8061-5d37b2b7c0dc" />

## Fade
<img width="1917" height="1078" alt="Screenshot 2026-11-24 203054" src="https://github.com/user-attachments/assets/98e2b627-a9d8-4f2f-951d-17fa50ef0157" />

## Rotate
<img width="1917" height="1077" alt="Screenshot 2026-11-24 203102" src="https://github.com/user-attachments/assets/66542e2b-0185-461a-aa35-cdfce8ad126c" />

## Zoom
<img width="1917" height="1075" alt="Screenshot 2026-11-24 203114" src="https://github.com/user-attachments/assets/8e1e19d9-bba5-4a8f-a4bb-30d9ef91b83e" />

## Slide
<img width="1917" height="1078" alt="Screenshot 2026-11-24 203134" src="https://github.com/user-attachments/assets/df944b58-2bc1-4402-8a75-4f8c0e57671e" />

## Execution



https://github.com/user-attachments/assets/c674a5a5-7f6a-416c-8bf3-0369692859ff





## RESULT


Thus, the Android application to perform Move, Blink, Fade, Clockwise, Zoom and Slide animations on an ImageView was developed and executed successfully.
