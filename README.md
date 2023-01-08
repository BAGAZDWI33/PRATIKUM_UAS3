# PRATIKUM_UAS3
# PROJECT QR CODE APP MOBILE DENGAN 5 FUNGSI

## 1. FUNGSI JSON
JSON (JavaScript Object Notation) adalah sebuah format data yang digunakan untuk pertukaran dan penyimpanan data.
Kata kunci yang perlu diingat: “pertukaran & penyimpanan data”.JSON merupakan bagian (subset) dari Javascript. JSON bisa dibaca dengan berbagai macam bahasa pemrograman seperti C, C++, C#, Java, Javascript Perl, Python, dan banyak lagi.Hal ini membuat JSON menjadi bahasa yang ideal untuk perturakan data antar aplikasi.JSON bahkan mendominasi pendahulunya si XML (eXtensible Markup Language).Kalau dibandingkan dengan XML, JSON lebih sederhana dan mudah dibaca.

code JAVA JSON pada APP QR CODE yang saya buat

// JSON
                try {

                    JSONObject jsonObject = new JSONObject(result.getContents());
                    textViewName.setText(jsonObject.getString("nama"));
                    textViewClass.setText(jsonObject.getString("kelas"));
                    textViewID.setText(jsonObject.getString("nim"));

                }  catch (JSONException e){
                    e.printStackTrace();
                    Toast.makeText(this, result.getContents(), Toast.LENGTH_LONG).show();
                }

                Toast.makeText(this, "Scanned : " + result.getContents(), Toast.LENGTH_LONG).show();
            }
        }


    berikut ini adalah gambar QR yang saya buat untuk praktek projek JSON

![qr-code](https://user-images.githubusercontent.com/92739297/211195372-83cadfc5-9f00-4650-89d2-9a492fd32b7f.png)

    bila gambar diatas discan dengan app yang saya buat maka muncul seperti gambar dibawah

![Screenshot_JSHON1_QRCode](https://user-images.githubusercontent.com/92739297/211195751-2d8cb63b-217f-4d62-922d-50323c20f636.jpg)

![Screenshot_JSON_QRCode](https://user-images.githubusercontent.com/92739297/211195791-22425b41-9bbd-465e-ad54-e3c4d7ad2a7b.jpg)

    MAKA dinyatakan bahwa fungsi JSON yang saya buat berfungsi dan tidak terjadi error

## 2.FUNGSI WEB
    Digunakan untuk menampilkan QR CODE dari link website tertentu yang biasanya digunakan untuk mempermudah pengguna saat pencarian situs terkait

    berikut code java untuk WEB

    
            // WEBVIEW
            else if (Patterns.WEB_URL.matcher(result.getContents()).matches()) {
                Intent visitUrl = new Intent(Intent.ACTION_VIEW, Uri.parse(result.getContents()));
                startActivity(visitUrl);
            }

    berikut ini adalah gambar QR CODE yang saya buat untuk praktek projek pemanggilan WEB

![qr-code WEB](https://user-images.githubusercontent.com/92739297/211196157-d9301aa9-f1f8-4879-8015-8b1c904fb67b.png)

    bila gambar diatas discan dengan app yang saya buat maka muncul seperti gambar dibawah

     
![Screenshot_WEB_QRCode](https://user-images.githubusercontent.com/92739297/211196396-52fa29a9-a95c-4d62-8455-877a173acc4d.jpg)

ini adalah gambar saat melakukan scan barqode

 
![Screenshot_hasil scan qr web](https://user-images.githubusercontent.com/92739297/211196528-bfa8cb75-5800-45b7-b16d-fe71c1e616e4.jpg)

muncul seperti gambar diatas dan kita pilih maka 

![Screenshot_Chrome](https://user-images.githubusercontent.com/92739297/211196463-fb59d6e1-c3fe-4bbd-8757-d364de0e0d8b.jpg)

akan muncul sepeti gambar diatas dengan langsung menuju WEB yang ada di dalam barqode tersebut

maka dinyatakan code yang saya buat sukses dan tidak terjadi error

## 3. FUNGSI PHONE 
digunakan untuk pemanggilan call telephone saat di scan secara langsung
ini mempermudah dalam pemanggilan nomer telephon secara cepat menggunakan barqode dengan APP yang saya buat.

berikut code java untuk Pemanggilan Call Phone

 // DIAL UP, NOMOR TELEPON
            else if (Patterns.PHONE.matcher(result.getContents()).matches()) {
                Intent intent2 = new Intent(Intent.ACTION_CALL, Uri.parse("tel:" + result.getContents()));
                startActivity(intent2);}

dari code diatas dapat kita gunakan untuk melakukan scan barqode memanggil langsung pemilik nomer hp terkait 
berikut barqode yang telah saya buat untuk praktek project PHONE
![qr-code Telephon](https://user-images.githubusercontent.com/92739297/211197713-4cd7f883-858b-4c7e-adf5-3fd6e9cb7ce8.png)

kegiatan saat melakukan scan barqode 
![Screenshot_PHONE_QRCode](https://user-images.githubusercontent.com/92739297/211197351-0ff31fbb-2ba2-4140-b348-646e2c62e672.jpg)

saat saya melakukan scan pada barqode diatas, maka akan menghasilkan  

 
![Screenshot_Hasil dari scan PHONE](https://user-images.githubusercontent.com/92739297/211197391-d2743b65-575d-4d84-aacc-8d1154bcbc8f.jpg)

itu tampil secara langsung cepat dan tepat sesuai isi barqode yang saya buat.

maka dari hasil diatas, code java PHONE yang saya buat sukses dan tidak terjadi error.
 
## 4.FUNGSI MAPS
Dilakukan untuk pemanggilan lokasi yang tepat dan akurat sesuai apa yang pengguna scan, dengan barqode lokasi yang dituju 

berikut code java MAPs

// MAPS
            else if (result.getContents().startsWith("geo:")) {
                // Barcode merupakan koordinat
                Intent mapsIntent = new Intent(Intent.ACTION_VIEW, Uri.parse(result.getContents()));
                mapsIntent.setPackage("com.google.android.apps.maps");
                startActivity(mapsIntent);
            }

dari code diatas kita akan memanggil lokasi yang telah dibuatkan barqode,berikut barqode untuk praktek project fungsi MAPs

![qr-code MAPS](https://user-images.githubusercontent.com/92739297/211197978-35592064-f922-41ed-8c35-541eba8d2774.png)

kode barqode diatas menuju lokasi yang telah ditentukan 
maka

 
![Screenshot_MAPS_QRCode](https://user-images.githubusercontent.com/92739297/211198146-2eb38cc4-be81-4f4f-aa79-a2f635ec226d.jpg)

itu kegiatan saat melakukan scan barqode terkait

maka dihasilkan

![Screenshot_Hasil Maps](https://user-images.githubusercontent.com/92739297/211198190-6af9108d-f111-4736-afc6-dbd4d545e1f9.jpg)

gambar di atas akan muncul langsung menuju ke lokasi map yang kita scan secara tepat dan akurat

dari hasil diatas maka kode java yang saya buat berhasil atau sukses dan tidak terjadi error.

## 5. FUNGSI  EMAIL
Dilakukan untuk pemanggilan email agar lebih cepat dan akurat dengan menggunakan barqode, ini akan langsung menuju email terkait saat dilakukannya scan pada barqode APP yang saya buat.
berikut code java pemanggilan email pada android studio
 // EMAIL
            else if (result.getContents().startsWith("mailto:")) {
                // Barcode merupakan alamat email
                Intent emailIntent = new Intent(Intent.ACTION_SENDTO);
                emailIntent.setData(Uri.parse(result.getContents()));
                emailIntent.putExtra(Intent.EXTRA_SUBJECT, "Subject");
                emailIntent.putExtra(Intent.EXTRA_TEXT, "Body");
                if (emailIntent.resolveActivity(getPackageManager()) != null) {
                    startActivity(emailIntent);
                }

code diatas untuk pemanggilan email yang di buat barqode,untuk lebih jelasnya saya sudah buat barqode yang digunakan saat praktek project Pemanggilan Email

![qr-code EMAIL](https://user-images.githubusercontent.com/92739297/211198854-353e2dda-338a-4431-afd2-4add3136c3db.png)

saat saya melakukan kegiatan scan seperti gambar dibawah

 
![Screenshot_Email scan](https://user-images.githubusercontent.com/92739297/211199195-9287a6d7-928f-4eb1-a0b6-dcadbad59961.jpg)

dengan scan yang dilakukan maka menghasilkan

![Screenshot_Hasil dari melakukan Scan Email](https://user-images.githubusercontent.com/92739297/211199232-484301b5-9503-454d-b7b5-87a2466200db.jpg)

![Screenshot_hasil di email](https://user-images.githubusercontent.com/92739297/211199277-903ad189-9215-4d99-aba7-b4329e6814f9.jpg)

dari kegiatan diatas maka dapat disimpulkan bahwa kode java yang saya buat berhasil dan sukses untuk pemanggilan email secara langsung saat scan barqode yang telah dibuat untuk praktek.

dari penjelasan diatas maka 5 fungsi di project QRCODE APP MOBILE  yang telah dibuat telah terpenuhi dengan code java dan desain yang saya buat

beriku code java keseluruhan dari project yang dibuat:


package com.example.qrcode;


import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;
import android.widget.Toast;
import android.util.Patterns;

import androidx.appcompat.app.AppCompatActivity;
import com.google.zxing.integration.android.IntentIntegrator;
import com.google.zxing.integration.android.IntentResult;

import org.json.JSONException;
import org.json.JSONObject;

public class MainActivity extends AppCompatActivity implements View.OnClickListener {

    // objek
    private Button buttonScanning;
    private TextView textViewName, textViewClass, textViewID;

    // QRCode Scanner
    private IntentIntegrator qrscan;


    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // View
        buttonScanning = (Button) findViewById(R.id.buttonScan);
        textViewName = (TextView) findViewById(R.id.textViewNama);
        textViewClass = (TextView) findViewById(R.id.textViewKelas);
        textViewID = (TextView) findViewById(R.id.textViewNIM);

        qrscan = new IntentIntegrator(this);
        buttonScanning.setOnClickListener(this);
    }

    @Override
    public void onActivityResult(int requestCode, int resultCode, Intent data) {
        IntentResult result = IntentIntegrator.parseActivityResult(requestCode, resultCode, data);
        if(result != null) {
            if(result.getContents() == null) {
                Toast.makeText(this, "Not Scanned", Toast.LENGTH_LONG).show();
            }
            // DIAL UP, NOMOR TELEPON
            else if (Patterns.PHONE.matcher(result.getContents()).matches()) {
                Intent intent2 = new Intent(Intent.ACTION_CALL, Uri.parse("tel:" + result.getContents()));
                startActivity(intent2);}

            // WEBVIEW
            else if (Patterns.WEB_URL.matcher(result.getContents()).matches()) {
                Intent visitUrl = new Intent(Intent.ACTION_VIEW, Uri.parse(result.getContents()));
                startActivity(visitUrl);
            }
            // EMAIL
            else if (result.getContents().startsWith("mailto:")) {
                // Barcode merupakan alamat email
                Intent emailIntent = new Intent(Intent.ACTION_SENDTO);
                emailIntent.setData(Uri.parse(result.getContents()));
                emailIntent.putExtra(Intent.EXTRA_SUBJECT, "Subject");
                emailIntent.putExtra(Intent.EXTRA_TEXT, "Body");
                if (emailIntent.resolveActivity(getPackageManager()) != null) {
                    startActivity(emailIntent);
                }
            }
            // MAPS
            else if (result.getContents().startsWith("geo:")) {
                // Barcode merupakan koordinat
                Intent mapsIntent = new Intent(Intent.ACTION_VIEW, Uri.parse(result.getContents()));
                mapsIntent.setPackage("com.google.android.apps.maps");
                startActivity(mapsIntent);
            }

            else {



                // JSON
                try {

                    JSONObject jsonObject = new JSONObject(result.getContents());
                    textViewName.setText(jsonObject.getString("nama"));
                    textViewClass.setText(jsonObject.getString("kelas"));
                    textViewID.setText(jsonObject.getString("nim"));

                }  catch (JSONException e){
                    e.printStackTrace();
                    Toast.makeText(this, result.getContents(), Toast.LENGTH_LONG).show();
                }

                Toast.makeText(this, "Scanned : " + result.getContents(), Toast.LENGTH_LONG).show();
            }
        } else {
            super.onActivityResult(requestCode, resultCode, data);
        }
    }

    @Override
    public void onClick(View view) {
        qrscan.initiateScan();
    }
}


untuk menjalankan code java diatas memerlukan xml desain android studio yang telah saya buat

berikut codenya

<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:paddingBottom="@dimen/activity_vertical_margin"
    android:paddingTop="@dimen/activity_vertical_margin"
    android:paddingRight="@dimen/activity_horizontal_margin"
    android:padding="30dp"
    android:paddingLeft="@dimen/activity_horizontal_margin"
    android:background="@color/blue">

    <Button
        android:id="@+id/buttonScan"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="QR CODE SCAN"
        android:layout_alignParentBottom="true"
        android:textColor="@color/black"
        android:layout_marginBottom="50dp"
        android:backgroundTint="@color/biru"/>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        android:layout_centerVertical="true">

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Nama :"
            android:textSize="10pt"
            android:textColor="@color/black"/>

        <TextView
            android:id="@+id/textViewNama"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="BAGAS DWI PRASETYO"
            android:textStyle="bold"
            android:textColor="@color/black"
            android:textAppearance="@style/TextAppearance.AppCompat.Large"/>

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Kelas :"
            android:textSize="10pt"
            android:textColor="@color/black"/>

        <TextView
            android:id="@+id/textViewKelas"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:textColor="@color/black"
            android:text="TI.21.C5"
            android:textStyle="bold"
            android:textAppearance="@style/TextAppearance.AppCompat.Large"/>

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Nim :"
            android:textSize="10pt"
            android:textColor="@color/black"/>

        <TextView
            android:id="@+id/textViewNIM"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="312110053"
            android:textStyle="bold"
            android:textColor="@color/black"
            android:textAppearance="@style/TextAppearance.AppCompat.Large"/>

    </LinearLayout>
</RelativeLayout>

dari code diatas maka menghasilkan app mobile seperti gambar dibawah ini


![Screenshot (6)](https://user-images.githubusercontent.com/92739297/211199609-7fc4e923-4862-4035-af66-cc48d7379c8d.png)

selesai juga project APP MOBILE QR CODE yang saya buat, semoga mengedukasi dan memberikan ilmu pengetahuan yang nyata lagi benar.t\
Terima kasih kepada Bapak Dosen Donny Maulana,S.Kom.,M.M.S.I. yang telah membimbing saya dari dasar hingga menjadi project diatas. t\

Terima kasih kepada rekan mahasiswa yang ikut serta membuat saya bisa sepeti ini,dan Terima kasih kepada diri sendiri yang kuat menghadapi kerasnya dunia ini, Terima kasih kepada patner hidup yang selalu membuat segala hal terasa mudah yaitu Orang tua dan yang terkasih (Meli Agustina)semoga bermanfaat

saya

Nama : Bagas Dwi Prasetyo t\
NIM : 312110053 t\
Kelas : TI.21.C5 t\

by.mahasiswa hebat
















