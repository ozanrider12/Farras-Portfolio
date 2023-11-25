# Natural Language Processing (NLP)

Project ini merupakan project yang saya gunakan sebagai topik tugas akhir saya yang akan digunakan dalam melayani pelayanan informasi dalam komputor yang dapat di ajak bicara
Dimana sistem yang saya gunakan ada 2 yakni Speech Recognition dan Text-to-Speech.
Perlu di ingat bahwa :
1. Menggunakan Bahasa Pemrograman Python
2. Saya hanya mencantumkan Coding, namun tidak cara instalan modulnya

## Speech Recognition
Speech recognition merupakan kemampuan yang memungkinkan komputor dapat mengenali kata yang manusia ucapkan menjadi sebuah tulisan seperti huruf (A, B, C), kata (Aku, Kamu, Mereka), ataupun kalimat (Ini Ibukota, Hello World). Pada penerapannya saya menggunakan model dari Google API yang telah memiliki kemampuan sistem dalam mengenali bahasa Indonesia.

## Text-to-Speech
Text-to-Speech merupakan kemampuan yang memungkinkan komputor dapat mengucapkan suatu huruf (A, B, C), kata (Aku, Kamu, Mereka), ataupun kalimat (Ini Ibukota, Hello World). Pada penerapannya saya menggunakan model dari Microsoft Windows yang telah memiliki kemampuan berucap menggunakan bahasa Indonesia 

## Cara Kerja
Untuk cara kerja sendiri, komputor akan menerima suara yang di ucapkan pengguna (sinyal analog) melalui michrophone. dari data ini kemudian komputornya mengubahnya menjadi sinyal digital yang dapat dibaca oleh komputor. dari data - data digital yang di dapatkan, komputor dapat mengenali huruf/kata/kalimat dari ucapan pengguna sebagai keywor (proses ini masuk ke dalam modul speech recognition). Setelah keyword didapatkan, maka kita dapat memasukkan dataset/database kata apa yang akan diucapkan yang akan dihasilkan oleh modul text-to-speech.

## Coding
