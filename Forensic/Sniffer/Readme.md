Sniffer / HTTP Sniffing

Writeup:

- Diberikan sebuah file log-hacker.pcap

- Pada soal telah dikatakan apabila hacker telah mengakses index.php dan berhasil logout, asumsinya logout.php.

- Jadi, buka dengan WireShark dan gunakan filter "http.request.method == GET"

- Maka akan muncul beberapa list, sesuai dengan soal, kita cari yang terdapat index.php, kemudian ada aktivitas logout.

- Yang paling mencurigakan adalah frame 11677, dimana terdapat get index.php, kemudian di bawahnya ada logout.php.

- Cek pada frame 11677, kemudian cek pada "Prev request in frame" yang menunjuk ke frame 11637.

- Pada HTML Form URL Encoded: application/x-www-form-urlencoded terdapat dua item form, yaitu username dan password. Gunakan password sebagai flag. Solved!

- Terdapat 9 fake flag (password yang salah, sehingga tidak redirect ke index.php)
