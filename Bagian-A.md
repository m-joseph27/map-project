Technical test

- Bagian A
1. 
.btn-sample {
  background-color: white;
  border: 1px solid black;
  padding: 10px 30px;
  color: black;
  border-radius: 15px;
  transition: font-size 0.3s ease, background-color 0.3s ease;
}

.btn-sample:hover {
  background-color: black;
  color: white;
  font-size: larger;
}

2.
Langkah - Langkah yang dapat dilakukan adalah
- menggabbungkan file css menjadi satu file css, untuk lebih mengoptimalkan bisa menggunakn minify file css menggunakan tools seperti uglifyCss yang berguna untuk menghapus spasi, komentar dan karakter yang tidak digunakan
- Menggabungkan file js menjadi satu file js, untuk fils js sendiri juga dapat melakukan hal yang sama dengan menggunakan tools uglifyJs yang bertujuan untuk menghapus spasi, komentar tau karater yang tidak digunakan

Contoh implementasi:

- HTML sebelum digabung:

<script src=“jquery.js”></script>
<script src=“appjs”></script>
<script src=“index.js”></script>

- HTML setelah digabungkan:

<script src=“script.minjs”></script>

- CSS sebelum digabung:

<link rel=“stylesheet” href=“index.css”>
<link rel=“stylesheet” href=“layout.css”>
<link rel=“stylesheet” href=“theme.css”>

- CSS setelah digabungkan:

<link rel=“stylesheet” href=“app.min.css”>


- CSS yang di minify menggunakan UglifyCss
// berisi file css yang telah digabung
body {margin: 0; padding: 0; dll} .container {width: 100%; dll}

- JS yang di minfy menggunakan UglifyJs
// berisi file js yang telah di gabung
$(document).ready(function(){...});

3.  
- Menggunakan element HTML5(Semantic HTML) dalam membuat tombol: menggunakan tag <button> dan menghindari tag sexerti <div> atau <span> untuk tombol
- Menambahkan css yang membantu tombol lebih interaktif seperti button:focus atau button:hover
- Elemen <button> secara otomatis mendukung interaksi dengan keyboard seperti ketika tombol, maka dałam mengembangkan statu tombol sangat di sarankan menggunakan tag <button>
- Serta memberikan caption pada button yang dibuat sehingga membantu menjelaskan fungsi button yang telah dibuat
