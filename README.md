Приложение где при на жатии на кнопку "Нажми меня" пользователю показывается рандомное число от 1 до 6
Выполнил студент Кондусова Ульяна
<img width="522" height="462" alt="image" src="https://github.com/user-attachments/assets/0ae928a9-4e6c-43f3-8162-cd33449e3312" />
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/result"
        android:layout_width="70dp"
        android:layout_height="50dp"
        android:text="0"
        android:textAlignment="center"
        android:textColor="#900837"
        android:textSize="34sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/button"
        android:layout_width="181dp"
        android:layout_height="76dp"
        android:background="#CC5858"
        android:backgroundTint="#DB1212"
        android:text="Нажми меня"
        android:textColor="#E2AFAF"
        android:textSize="24sp"
        android:textStyle="bold"
        app:iconPadding="10dp"
        app:iconTint="#210000"
        app:rippleColor="#280A0A"
        app:strokeColor="#A44B4B"
        tools:layout_editor_absoluteX="115dp"
        tools:layout_editor_absoluteY="504dp" />

</androidx.constraintlayout.widget.ConstraintLayout>


package com.example.KondysovaKlinrina

import android.os.Bundle
import androidx.activity.enableEdgeToEdge
import androidx.appcompat.app.AppCompatActivity
import androidx.core.view.ViewCompat
import androidx.core.view.WindowInsetsCompat

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        enableEdgeToEdge()
        setContentView(R.layout.activity_main)
        ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main)) { v, insets ->
            val systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars())
            v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom)
            insets

            val knopka: Button = findViewById(R.id.button)
            val tablo: TextView = findViewById(R.id.result)

            knopka.setOnClickListener {
                val chislo = (0..6).random()
                tablo.text = chislo.toString()
            }
        }
    }
}
