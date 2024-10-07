Python Pass

- Diberikan sebuah file .pyc 3.11 dan sebuah layanan nc, player perlu melakukan decompile terlebih dahulu terhadap file tersebut. Decompile menggunakan pycdc, maka akan didapatkan source code program python tersebut.

- Singkatnya, isi program tersebut hanyalah untuk membuat password berdasarkan kriteria:
1. Karakter harus 16
2. Terdapat minimal 1 karakter spesial
3. Terdapat minimal 1 kapital
4. Terdapat minimal 1 angka

- Jika benar, maka akan muncul flag, namun pada file yang diberikan ke player adalah fake flag. Flag yang asli terdapat pada layanan nc yang ada pada deskripsi soal, selanjutnya tinggal memasukkan password yang sama dengan sebelumnya ke layanan netcat, solved!
