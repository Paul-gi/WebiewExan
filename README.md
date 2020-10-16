# WebiewExan
webview實作
----------------------------------------------------------------------------------------------------------------------
package com.sinopac.videoview_exam;

import androidx.appcompat.app.AppCompatActivity;

import android.annotation.SuppressLint;
import android.os.Bundle;
import android.view.View;
import android.webkit.WebSettings;
import android.webkit.WebView;
import android.webkit.WebViewClient;
import android.widget.Button;
import android.widget.EditText;

public class MainActivity extends AppCompatActivity {
    Button b1;
    EditText ed1;
    private WebView wv1;
    @SuppressLint("SetJavaScriptEnabled")
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);


        b1=(Button)findViewById(R.id.button);
        ed1=(EditText)findViewById(R.id.editText);

        wv1=(WebView)findViewById(R.id.webView);
        wv1.setWebViewClient(new MyBrowser());

        b1.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String url = ed1.getText().toString();

                wv1.getSettings().setLoadsImagesAutomatically(true);
                wv1.getSettings().setJavaScriptEnabled(true);
                wv1.setScrollBarStyle(View.SCROLLBARS_INSIDE_OVERLAY);
                wv1.loadUrl("https://yamol.tw/cat-%E8%AD%89%E7%85%A7%E2%97%86%E9%87%91%E8%9E%8D%E5%B8%82%E5%A0%B4%E5%B8" +
                        "%B8%E8%AD%98%E8%88%87%E8%81%B7%E6%A5%AD%E9%81%93%E5%BE%B7%E6%B8%AC%E9%A9%97%E9%A1%8C%E5%BA%AB%E5%BD%99%E7%B7%A8-149.htm");
            }
        });
    }

    private class MyBrowser extends WebViewClient {
        @Override
        public boolean shouldOverrideUrlLoading(WebView view, String url) {
            view.loadUrl("https://yamol.tw/cat-%E8%AD%89%E7%85%A7%E2%97%86%E9%87%91%E8%9E%8D%E5%B8%82%E5%A0%B4%E5%B8\" +\n" +
                    "                        \"%B8%E8%AD%98%E8%88%87%E8%81%B7%E6%A5%AD%E9%81%93%E5%BE%B7%E6%B8%AC%E9%A9%97%E9%A1%8C%E5%BA%AB%E5%BD%99%E7%B7%A8-149.htm");
            return true;
        }
    }
}


------------------------------------------------------------------------------------------------------------------
XML
--------------------------------------------------------------------------------------------------------------------
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <EditText
        android:id="@+id/editText"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@+id/imageView"
        android:layout_alignEnd="@+id/imageView"
        android:layout_alignRight="@+id/imageView"
        android:layout_alignParentStart="true"
        android:layout_alignParentLeft="true"
        android:layout_marginTop="8dp"
        android:layout_marginEnd="176dp"
        android:focusable="true"
        android:hint="Enter Text"
        android:textColorHighlight="#ff7eff15"
        android:textColorHint="#ffff25e6"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/webView" />

    <ImageView
        android:id="@+id/imageView"
        android:layout_width="80dp"
        android:layout_height="49dp"

        android:layout_below="@+id/textView"
        android:layout_centerHorizontal="true"
        android:layout_marginTop="8dp"
        app:layout_constraintEnd_toStartOf="@+id/editText"
        app:layout_constraintHorizontal_bias="0.514"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/webView" />

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignTop="@+id/editText"
        android:layout_marginTop="8dp"
        android:layout_marginEnd="64dp"
        android:layout_toEndOf="@+id/imageView"
        android:layout_toRightOf="@+id/imageView"
        android:text="Enter"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/webView" />

    <WebView
        android:id="@+id/webView"
        android:layout_width="397dp"
        android:layout_height="596dp"
        android:layout_below="@+id/button"
        android:layout_alignParentStart="true"
        android:layout_alignParentLeft="true"
        android:layout_alignParentEnd="true"
        android:layout_alignParentRight="true"
        android:layout_alignParentBottom="true"
        android:layout_marginTop="4dp"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.47"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>
