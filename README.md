<h1>
  Reflection
</h1>

<h2>
  Experiment 2.1: Original code, and how it run
</h2>

![image](https://github.com/DaWanAnOnli/DaWanAnOnli-advprog-modul10-broadcast-chat/assets/124868777/ed2c2c9b-bc37-4913-b9f5-c0622bc2b3c8)


Penjelasan:
Saat beberapa client dan server dijalankan bersama-sama, kita dapat mengetikkan suatu pesan pada console salah satu client. Saat kita tekan Enter, pesan tersebut dikirimkan ke server dan ditampilkan di console server. Setelah itu, server melakukan broadcast message yang sama ke semua client yang ada. Ini adalah dasar dari bagaimana aplikasi chatting dapat bekerja. Secara khusus aplikasi ini mensimulasikan fitur posting. Message dikirimkan ke server, lalu server mem-broadcastnya ke semua client lain. 

<h2>
  Experiment 2.2: Modifying Port
</h2>

![image](https://github.com/DaWanAnOnli/DaWanAnOnli-advprog-modul10-broadcast-chat/assets/124868777/38553e77-b903-42e4-9215-ec1ca2023b59)

Modul menginstruksikan agar kita mengubah port di client menjadi 8080. Hal ini berarti client akan mencoba membuat koneksi ke port 8080. Namun kita tahu server menunggu koneksi di port 2000. Maka jika hanya port client saja yang diubah, akan terjadi error. Oleh karena itu, kita perlu mengubah port di server juga menjadi 8080. Dengan ini, server akan menunggu di port yang tepat, yaitu port yang menjadi tujuan client saat mengirimkan pesan.



<h2>
  Experiment 2.3: Small changes, add IP and Port
</h2>

![image](https://github.com/DaWanAnOnli/DaWanAnOnli-advprog-modul10-broadcast-chat/assets/124868777/728d6d95-8fcc-433f-bcac-7db4edb4ee2d)

Agar informasi IP dan Port sender bisa muncul di semua client saat server melakukan broadcast, perlu dilakukan beberapa perubahan. Pertama, definisi ```bcast_tx``` di ```server.rs``` perlu diganti. Kita buat agar ```bcast_text``` menerima value pair String (message), dan SocketAddr (informasi sender). Lalu saat kita melakukan receive (di ```bcast_rx```), kita menerima value pair dari sender, yaitu message dan informasi sender. Kita perlu format ini ke dalam satu message untuk bisa dikirim. Terakhir, saat kita broadcast, kita mengirimkan kedua informasi tersebut ke semua client.
