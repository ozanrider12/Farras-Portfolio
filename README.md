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
import speech_recognition as sr  
import pyttsx3  

engine = pyttsx3.init()  
voices = engine.getProperty('voices')  
engine.setProperty('voice', voices[1].id)  
engine.setProperty('rate', 155)  

def myCommand():  
&nbsp; "listen for commands"  
&nbsp; r = sr.Recognizer()  
  
&nbsp; with sr.Microphone() as source:  
&ensp;&nbsp;&nbsp; print('Sedang mendengarkan')  
&ensp;&nbsp;&nbsp; r.pause_threshold = 1  
&ensp;&nbsp;&nbsp; r.adjust_for_ambient_noise(source, duration=1)  
&ensp;&nbsp;&nbsp; audio = r.listen(source)  
&nbsp; try:  
&nbsp;&nbsp;&nbsp; command = r.recognize_google(audio, language="id-ID").lower()  
&nbsp;&nbsp;&nbsp; print('Anda : ' + command + '\n')  
&nbsp; except sr.UnknownValueError:  
&nbsp;&nbsp;&nbsp; print('Suara anda tidak terdengar, silahkan ucapkan lagi')  
&nbsp;&nbsp;&nbsp; command = myCommand();  
&nbsp; return command  

def pembuka(command):  
&nbsp; global status  
&nbsp; if 'Dataset Keyword Aktivasi Penggunaan' in command:  
&nbsp;&nbsp;&nbsp; engine.say('Dataset Respon Komputor')  
&nbsp;&nbsp;&nbsp; engine.runAndWait()  
&nbsp;&nbsp;&nbsp; status = 1  
&nbsp; else:  
&nbsp;&nbsp;&nbsp; status = 0  
&nbsp; pass  

def main(command):  
&nbsp; if 'Dataset Keyword Pertanyaan' in command:  
&nbsp;&nbsp;&nbsp; engine.say('Dataset Respon Komputor')  
&nbsp;&nbsp;&nbsp; engine.runAndWait()  
&nbsp;&nbsp;&nbsp; main(myCommand())  
  
&nbsp; elif 'Dataset Keyword Pertanyaan' in command:  
&nbsp;&nbsp;&nbsp; engine.say('Dataset Respon Komputor')  
&nbsp;&nbsp;&nbsp; engine.runAndWait()  
&nbsp;&nbsp;&nbsp; status = 0  
&nbsp;&nbsp;&nbsp; assistan(myCommand())  
    
&nbsp; else:  
&nbsp;&nbsp;&nbsp; engine.say('Dataset Respon Komputor')  
&nbsp;&nbsp;&nbsp; engine.runAndWait()  
&nbsp;&nbsp;&nbsp; main(myCommand())  

while True:  
&nbsp; pembuka(myCommand())  
  
&nbsp; if status == 1:  
&nbsp;&nbsp;&nbsp; main(myCommand())  
