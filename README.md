# ProjectFibonacci

Nama           : Amanda Puspa Negara

Nim            : 312210129

Kelas          : TI.22.A1

Mata Kuliah    : Pemrograman Mobile 1

Dosen Pengampu : Donny Maulana, S.Kom, M.Kom

### Tugas

![Screenshot (363)](https://github.com/amandaaaapn/ProjectFibonacci/assets/115678845/46a6ac83-3f58-4fc6-9457-301d3ea2f647)

# Langkah-Langkah

1. Membuat project baru terlebih dahulu dengan nama project "tugasenam"

2. Kemudian pada layout activity_main ditambahkan 3 "button" dan 1 "textview" seperti berikut

![Screenshot 2023-11-04 103053](https://github.com/amandaaaapn/ProjectFibonacci/assets/115678845/31baca9c-8cef-4345-b043-a504bb383ecc)

3. Untuk button yang pertama berfungsi sebagai tombol "Toast" yang nantinya ketika ditekan akan muncul sebuah toast message yaitu "Bilangan Fibonacci". Button yang kedua, berfungsi sebagai tombol “count” yang nantinya ketika tombol ditekan akan menghitung bilangan fibonaccinya. Dan yang terakhir Textview, yang berfungsi untuk menampilkan angka atau bilangan fibonaccinya yang tepat berada di tengah.

4. Kemudian kita masukkan untuk codingan didalam activity_fibonacci seperti berikut

 * activity_fibonacci.xml
  
            <?xml version="1.0" encoding="utf-8"?>
            <androidx.constraintlayout.widget.ConstraintLayout
              xmlns:android="http://schemas.android.com/apk/res/android"
              xmlns:app="http://schemas.android.com/apk/res-auto"
              xmlns:tools="http://schemas.android.com/tools"
              android:layout_width="match_parent"
              android:layout_height="match_parent"
              tools:context=".MainActivity">
          
              <EditText
                  android:id="@+id/edit_max_fibonacci"
                  android:layout_width="0dp"
                  android:layout_height="wrap_content"
                  android:layout_marginEnd="8dp"
                  android:layout_marginTop="8dp"
                  android:hint="Maksimum Fibonacci"
                  android:inputType="number"
                  app:layout_constraintEnd_toEndOf="parent"
                  app:layout_constraintTop_toTopOf="parent"
                  tools:ignore="MissingTranslation"/>
          
              <Button
                  android:id="@+id/button_toast"
                  android:layout_width="190dp"
                  android:layout_height="48dp"
                  android:layout_marginStart="8dp"
                  android:layout_marginTop="8dp"
                  android:background="@color/colorPrimary"
                  android:onClick="showToast"
                  android:textColor="@android:color/white"
                  android:text="@string/button_label_toast"
                  app:layout_constraintStart_toStartOf="parent"
                  app:layout_constraintTop_toTopOf="parent" />
          
          
              <Button
                  android:id="@+id/button_count"
                  android:layout_width="190dp"
                  android:layout_height="48dp"
                  android:layout_marginStart="8dp"
                  android:layout_marginEnd="8dp"
                  android:layout_marginBottom="8dp"
                  android:background="@color/colorPrimary"
                  android:onClick="countUp"
                  android:text="@string/button_label_count"
                  android:textColor="@android:color/white"
                  app:layout_constraintBottom_toBottomOf="parent"
                  app:layout_constraintEnd_toEndOf="parent"
                  app:layout_constraintHorizontal_bias="0.0"
                  app:layout_constraintStart_toStartOf="parent"
                  tools:ignore="UsingOnClickInXml,VisualLintButtonSize" />
          
              <Button
                  android:id="@+id/button_finish"
                  android:layout_width="190dp"
                  android:layout_height="48dp"
                  android:layout_marginStart="8dp"
                  android:layout_marginEnd="8dp"
                  android:layout_marginBottom="8dp"
                  android:background="@color/colorPrimary"
                  android:onClick="back1"
                  android:text="@string/button_label_finish"
                  android:textColor="@android:color/white"
                  app:layout_constraintBottom_toBottomOf="parent"
                  app:layout_constraintEnd_toEndOf="parent"
                  app:layout_constraintHorizontal_bias="1.0"
                  app:layout_constraintStart_toStartOf="parent"
                  tools:ignore="UsingOnClickInXml" />
          
              <TextView
                  android:id="@+id/show_count"
                  android:layout_width="0dp"
                  android:layout_height="0dp"
                  android:layout_marginStart="8dp"
                  android:layout_marginTop="8dp"
                  android:layout_marginEnd="8dp"
                  android:layout_marginBottom="8dp"
                  android:background="#FFFF00"
                  android:gravity="center_vertical"
                  android:text="@string/count_initial_value"
                  android:textAlignment="center"
                  android:textColor="@color/colorPrimary"
                  android:textSize="160sp"
                  android:textStyle="bold"
                  app:layout_constraintBottom_toTopOf="@id/button_count"
                  app:layout_constraintEnd_toEndOf="parent"
                  app:layout_constraintStart_toStartOf="parent"
                  app:layout_constraintTop_toBottomOf="@id/button_toast"
                  tools:ignore="RtlCompat" />
          
          </androidx.constraintlayout.widget.ConstraintLayout>

  * strings.xml
 
        <resources>
            <string name="app_name">Tugasenam</string>
            <string name="button_label_toast">Toast</string>
            <string name="button_label_count">Count</string>
            <string name="count_initial_value">1</string>
            <string name="toast_message">Bilangan Fibonacci</string>
            <string name="button_label_finish">Reset</string>
            <string name="enter_fibonacci_limit">Masukan Limit Angka</string>
        </resources>

* colors.xml
   
           <?xml version="1.0" encoding="utf-8"?>
           <resources>
                <color name="black">#FF000000</color>
                <color name="white">#FFFFFFFF</color>
                <color name="colorPrimary">#3F5185</color>
                <color name="colorPrimaryDark">#303F9F</color>
                <color name="colorAccent">#FF4081</color>
            
            </resources>

  # Tampilan Design

![Screenshot (404)](https://github.com/amandaaaapn/ProjectFibonacci/assets/115678845/491426e4-2b25-4bb5-bd45-486f24a963f2)

  # MainActivity.java

  Pada MainActivity.java berisi semua codingan untuk fungsi-fungsinya. Seperti, fungsi untuk 
  tombol-tombol dan rumus bilangan fibonaccinya.

         package com.tugasenam;

            import android.os.Bundle;
            import android.view.View;
            import android.widget.EditText;
            import android.widget.TextView;
            import android.widget.Toast;
            
            import androidx.appcompat.app.AppCompatActivity;
            
            public class MainActivity extends AppCompatActivity {
                private TextView showCount;
                private int count = 0;
                private long fibNMinus1 = 1;
                private long fibNMinus2 = 0;
                private EditText edit_max_fibonacci;
            
                @Override
                protected void onCreate(Bundle savedInstanceState) {
                    super.onCreate(savedInstanceState);
                    setContentView(R.layout.activity_fibonacci);
            
                    showCount = findViewById(R.id.show_count);
                    edit_max_fibonacci = findViewById(R.id.edit_max_fibonacci);
            
                    updateCountDisplay();
            
                    fibNMinus1 = 1;
                    fibNMinus2 = 0;
                }
            
                private void updateCountDisplay() {
                    showCount.setText(String.valueOf(fibNMinus1));
            
                    if (count % 4 == 0) {
                        showCount.setTextColor(getResources().getColor(R.color.colorPrimary));
                    } else if (count % 4 == 1) {
                        showCount.setTextColor(getResources().getColor(R.color.colorAccent));
                    } else if (count % 4 == 2) {
                        showCount.setTextColor(getResources().getColor(R.color.colorPrimary));
                    } else {
                        showCount.setTextColor(getResources().getColor(R.color.colorAccent));
                    }
                }
            
                public void showToast(View view){
                    Toast.makeText(this, "Bilangan Fibonacci",
                            Toast.LENGTH_SHORT).show();
                }
            
                public void countUp(View view) {
                    int maxFibonacci = Integer.parseInt(edit_max_fibonacci.getText().toString());
            
                    if (count >= maxFibonacci) {
                        Toast.makeText(this, "Maksimum Fibonacci tercapai", Toast.LENGTH_SHORT).show();
                        return;
                    }
            
                    long fibCurrent;
                    if (count == 0 || count == 1) {
                        fibCurrent = 1;
                    } else {
                        fibCurrent = fibNMinus1 + fibNMinus2;
                    }
            
                    fibNMinus2 = fibNMinus1;
                    fibNMinus1 = fibCurrent;
                    updateCountDisplay();
            
                    count++;
                }
            
                public void back1(View view) {
                    count = 0;
                    fibNMinus1 = 1;
                    fibNMinus2 = 0;
                    updateCountDisplay();
                }
            }

# Hasil Run

Untuk run app ini saya menggunakan software emulator yaitu Genymotion. Berikut ini adalah tampilan dari aplikasi yang telah saya buat :

* Tombol Toast ditekan, maka akan muncul message "Bilangan Fibonacci" seperti gambar dibawah

![Screenshot 2023-11-04 102436](https://github.com/amandaaaapn/ProjectFibonacci/assets/115678845/d4206ef1-6094-4d21-adad-77eefc2a3b0b)

* Tombol Count ditekan, maka angka "1" akan berubah menjadi Bilangan Fibonacci seperti berikut.
  
![Screenshot 2023-11-04 102455](https://github.com/amandaaaapn/ProjectFibonacci/assets/115678845/bd5e9f20-591f-41ce-9015-f0da72ff9ace)

![Screenshot 2023-11-04 102510](https://github.com/amandaaaapn/ProjectFibonacci/assets/115678845/337297c5-4b9f-4095-8940-463631b345bb)

![Screenshot 2023-11-04 102633](https://github.com/amandaaaapn/ProjectFibonacci/assets/115678845/ec399dbf-3f8a-4836-8d43-16aa952a48b4)

![Screenshot 2023-11-04 102644](https://github.com/amandaaaapn/ProjectFibonacci/assets/115678845/715b60ab-874a-4337-96bd-03f7f2384ded)

![Screenshot 2023-11-04 102709](https://github.com/amandaaaapn/ProjectFibonacci/assets/115678845/c8e10c02-47ad-4a59-bc77-620063a6b726)

![Screenshot 2023-11-04 102718](https://github.com/amandaaaapn/ProjectFibonacci/assets/115678845/0619b7f9-05bb-4e6a-b775-227f02e6ed8c)

![Screenshot 2023-11-04 102728](https://github.com/amandaaaapn/ProjectFibonacci/assets/115678845/d2ff7db6-da10-425b-8113-19b77120982c)

![Screenshot 2023-11-04 102740](https://github.com/amandaaaapn/ProjectFibonacci/assets/115678845/8f92e663-424b-4a56-8440-1f0729461133)

![Screenshot 2023-11-04 102750](https://github.com/amandaaaapn/ProjectFibonacci/assets/115678845/300d005d-2f4a-4451-b15f-2a2b141099e4)

* Setelah itu lakukan reset ulang untuk kembali ke awal

# Sekian, Terima Kasih

