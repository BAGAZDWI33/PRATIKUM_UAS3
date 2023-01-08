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

 
![Screenshot_PHONE_QRCode](https://user-images.githubusercontent.com/92739297/211197351-0ff31fbb-2ba2-4140-b348-646e2c62e672.jpg)

saat saya melakukan scan pada barqode diatas, maka akan menghasilkan 

 
![Screenshot_Hasil dari scan PHONE](https://user-images.githubusercontent.com/92739297/211197391-d2743b65-575d-4d84-aacc-8d1154bcbc8f.jpg)

itu tampil secara langsung cepat dan tepat sesuai isi barqode yang saya buat.

maka dari hasil diatas, code java PHONE yang saya buat sukses dan tidak terjadi error.









