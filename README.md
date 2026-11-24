# EX.NO: 12 – Drawing Basic Graphical Primitives Using Android Studio

## AIM

To create and design an Android application that draws basic graphical primitives on the screen using Android Studio.

## EQUIPMENTS REQUIRED

- Android Studio (Latest Version)
- Java Programming Language
- Android Emulator

## ALGORITHM

1. Open Android Studio and select File → New → New Project.
2. Enter the application name as `graphical` and click Next.
3. Select the required Minimum SDK and click Next.
4. Choose Empty Views Activity and click Finish.
5. Design the application layout in `activity_main.xml`.
6. Implement the drawing operations for basic graphical primitives in `MainActivity.java`.
7. Save and run the application.
8. Observe the graphical primitives displayed on the screen.

## PROGRAM

### MainActivity.java

```java
/*
Program to create and design an Android application
that draws basic graphical primitives on the screen.

Developed by: JAYANI N
Registration Number: 212224100025
*/

package com.example.graphical;

import android.os.Bundle;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }
}



```


### GraophicalView.java



```java
package com.example.graphical;

import android.content.Context;
import android.graphics.Canvas;
import android.graphics.Color;
import android.graphics.Paint;
import android.graphics.Path;
import android.view.View;

public class GraphicalView extends View {

    Paint paint;

    public GraphicalView(Context context) {
        super(context);
        paint = new Paint();
        paint.setAntiAlias(true);
    }

    @Override
    protected void onDraw(Canvas canvas) {
        super.onDraw(canvas);

        float width = getWidth();

        // Background
        canvas.drawColor(Color.WHITE);

        // Title
        paint.setColor(Color.BLACK);
        paint.setTextSize(28);
        paint.setTextAlign(Paint.Align.CENTER);
        paint.setFakeBoldText(true);
        canvas.drawText("Basic Graphical Primitives",
                width / 2, 50, paint);
        paint.setFakeBoldText(false);

        // Draw Line
        paint.setColor(Color.RED);
        paint.setStrokeWidth(6);
        canvas.drawLine(50, 100, width - 50, 100, paint);

        // Draw Rectangle
        paint.setColor(Color.BLUE);
        paint.setStyle(Paint.Style.STROKE);
        paint.setStrokeWidth(5);
        canvas.drawRect(50, 140, 250, 250, paint);

        // Draw Circle
        paint.setColor(Color.GREEN);
        paint.setStyle(Paint.Style.FILL);
        canvas.drawCircle(width / 2, 330, 65, paint);

        // Draw Oval
        paint.setColor(Color.MAGENTA);
        canvas.drawOval(50, 430, width - 50, 520, paint);

        // Draw Triangle
        paint.setColor(Color.rgb(255, 140, 0));

        Path path = new Path();
        path.moveTo(width / 2, 560);
        path.lineTo(width / 2 - 90, 700);
        path.lineTo(width / 2 + 90, 700);
        path.close();

        canvas.drawPath(path, paint);

        // Draw Text
        paint.setColor(Color.BLACK);
        paint.setTextSize(25);
        paint.setTextAlign(Paint.Align.CENTER);

        canvas.drawText("Android Graphics",
                width / 2, 770, paint);
    }
}




```





### activity_main.xml

```xml

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:background="#FFFFFF">

    <com.example.graphical.GraphicalView
        android:id="@+id/graphicalView"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />

</LinearLayout>


```

## OUTPUT

### 1. Application Screen

<img width="1088" height="817" alt="image" src="https://github.com/user-attachments/assets/715d9bb0-5e3e-4429-964d-0434bd2c182c" />


### 2. Graphical Primitives Output

<img width="235" height="457" alt="image" src="https://github.com/user-attachments/assets/14c9b8b7-9160-481d-8f72-07ea321516bb" />


## RESULT

Thus, a simple Android application to create and design graphical primitives on the screen using Android Studio was developed and executed successfully.
