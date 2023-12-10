# samruddhi
<!-- res/layout/activity_main.xml -->

<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:padding="16dp"
    tools:context=".MainActivity">

    <EditText
        android:id="@+id/editTextValue"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter value"
        android:inputType="numberDecimal" />

    <Spinner
        android:id="@+id/spinnerFrom"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/editTextValue"
        android:layout_marginTop="8dp"/>

    <Spinner
        android:id="@+id/spinnerTo"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/spinnerFrom"
        android:layout_marginTop="8dp"/>

    <Button
        android:id="@+id/btnConvert"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/spinnerTo"
        android:layout_marginTop="16dp"
        android:text="Convert" />

    <TextView
        android:id="@+id/textViewResult"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@id/btnConvert"
        android:layout_marginTop="16dp"
        android:text=""
        android:textSize="18sp" />

</RelativeLayout>
<!-- res/layout/activity_main.xml -->

<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:padding="16dp"
    tools:context=".MainActivity">

    <EditText
        android:id="@+id/editTextValue"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter value"
        android:inputType="numberDecimal" />

    <Spinner
        android:id="@+id/spinnerFrom"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/editTextValue"
        android:layout_marginTop="8dp"/>

    <Spinner
        android:id="@+id/spinnerTo"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/spinnerFrom"
        android:layout_marginTop="8dp"/>

    <Button
        android:id="@+id/btnConvert"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/spinnerTo"
        android:layout_marginTop="16dp"
        android:text="Convert" />

    <TextView
        android:id="@+id/textViewResult"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@id/btnConvert"
        android:layout_marginTop="16dp"
        android:text=""
        android:textSize="18sp" />

</RelativeLayout>
// src/main/java/com.example.unitconverter/MainActivity.java

import android.os.Bundle;
import android.view.View;
import android.widget.AdapterView;
import android.widget.ArrayAdapter;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Spinner;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    private EditText editTextValue;
    private Spinner spinnerFrom, spinnerTo;
    private Button btnConvert;
    private TextView textViewResult;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Initialize views
        editTextValue = findViewById(R.id.editTextValue);
        spinnerFrom = findViewById(R.id.spinnerFrom);
        spinnerTo = findViewById(R.id.spinnerTo);
        btnConvert = findViewById(R.id.btnConvert);
        textViewResult = findViewById(R.id.textViewResult);

        // Populate spinners with unit options
        ArrayAdapter<CharSequence> adapter = ArrayAdapter.createFromResource(
                this, R.array.length_units, android.R.layout.simple_spinner_item);
        adapter.setDropDownViewResource(android.R.layout.simple_spinner_dropdown_item);
        spinnerFrom.setAdapter(adapter);
        spinnerTo.setAdapter(adapter);

        // Set default selection
        spinnerFrom.setSelection(0);
        spinnerTo.setSelection(1);

        // Set event listener for the Convert button
        btnConvert.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                convertUnits();
            }
        });
    }

    private void convertUnits() {
        // Get user input
        double inputValue;
        try {
            inputValue = Double.parseDouble(editTextValue.getText().toString());
        } catch (NumberFormatException e) {
            textViewResult.setText("Invalid input");
            return;
        }

        // Get selected units
        String fromUnit = spinnerFrom.getSelectedItem().toString();
        String toUnit = spinnerTo.getSelectedItem().toString();

        // Perform unit conversion
        double result;
        if (fromUnit.equals("Meters") && toUnit.equals("Feet")) {
            result = inputValue * 3.28084;
        } else if (fromUnit.equals("Feet") && toUnit.equals("Meters")) {
            result = inputValue / 3.28084;
        } else {
            textViewResult.setText("Unsupported conversion");
            return;
        }

        // Display result
        textViewResult.setText(String.format("%.2f %s = %.2f %s", inputValue, fromUnit, result, toUnit));
    }
}
<!-- res/values/strings.xml -->

<resources>
    <string-array name="length_units">
        <item>Meters</item>
        <item>Feet</item>
    </string-array>
</resources>
