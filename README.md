package com.example.calculator;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.EditText;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {
    EditText num1, num2;
    TextView result;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        num1 = findViewById(R.id.num1);
        num2 = findViewById(R.id.num2);
        result = findViewById(R.id.result);
    }

    public void add(View view) {
        double a = Double.parseDouble(num1.getText().toString());
        double b = Double.parseDouble(num2.getText().toString());
        result.setText("Result: " + (a + b));
    }

    public void subtract(View view) {
        double a = Double.parseDouble(num1.getText().toString());
        double b = Double.parseDouble(num2.getText().toString());
        result.setText("Result: " + (a - b));
    }

    public void multiply(View view) {
        double a = Double.parseDouble(num1.getText().toString());
        double b = Double.parseDouble(num2.getText().toString());
        result.setText("Result: " + (a * b));
    }

    public void divide(View view) {
        double a = Double.parseDouble(num1.getText().toString());
        double b = Double.parseDouble(num2.getText().toString());
        if (b == 0) {
            result.setText("Cannot divide by 0");
        } else {
            result.setText("Result: " + (a / b));
        }
    }
}
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:padding="24dp"
    android:gravity="center">

    <EditText
        android:id="@+id/num1"
        android:hint="Enter number 1"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <EditText
        android:id="@+id/num2"
        android:hint="Enter number 2"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:onClick="add"
        android:text="Add"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:onClick="subtract"
        android:text="Subtract"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:onClick="multiply"
        android:text="Multiply"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:onClick="divide"
        android:text="Divide"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <TextView
        android:id="@+id/result"
        android:text="Result:"
        android:textSize="20sp"
        android:layout_marginTop="20dp"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />

</LinearLayout>
