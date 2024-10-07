Enkrip-mengenkrip / Wolseley Cipher

Writeup:

- Diberikan sebuah file encrypt.py, analisa kode tersebut.

- Jadi, kode tersebut adalah enkripsi menggunakan wolseley cipher.

- Terdapat 5 unsur
- alphabet = ABCDEFGHIKLMNOPQRSTUVWXYZ (tanpa j)

- berdasarkan logika kode tersebut.

- alphabet nantinya akan berubah menjadi plain_alphabet sesuai value dari key. Misal key = act, maka

```plain_alphabet = ACTBDEFGHIKLMNOPQRSUVWXYZ```

- ACT di depan dan plain_alphabet ditulis tanpa adanya duplikasi.

- Selanjutnya plain_alphabet akan berubah menjadi cipher_alphabet, yaitu dengan me-reverse value dari plain_alphabet, sehingga menjadi

```cipher_alphabet = ZYXWVUSRQPONMLKIHGFEDBTCA```

- Sehingga sejauh ini diperoleh

```
plain_text = haksorman
key = act
alphabet = ABCDEFGHIKLMNOPQRSTUVWXYZ
plain_alphabet = ACTBDEFGHIKLMNOPQRSUVWXYZ
cipher_alphabet = ZYXWVUSRQPONMLKIHGFEDBTCA
```

- Untuk mengenkripsi plain text menjadi cipher, kita hanya perlu menggunakan plain_alphabet dan cipher_alphabet.

```
ACTBDEFGHIKLMNOPQRSUVWXYZ
ZYXWVUSRQPONMLKIHGFEDBTCA
```

- Tinggal mencocokkan atas-bawah saja, jika "haksorman" maka akan menjadi "QZOFKGMZL"

- Dan untuk mendecrypt, bisa menggunakan script solver atau logika, ataupun bisa menggunakan tools dari https://www.dcode.fr/wolseley-cipher. Solved!
