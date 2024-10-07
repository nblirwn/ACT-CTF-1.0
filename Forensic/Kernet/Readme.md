Kernet / Fernet Decrypt

Writeup:

- Diberikan sebuah encrypt.py

- Jika dianalisa, encrypt.py mengenkripsi sebuah gambar bernama image.jpg menggunakan fernet dengan key acak yang disimpan pada encryption_key.key

- Maka untuk mendekripsi gambar tersebut, bisa menggunakan script di bawah ini:

```
from cryptography.fernet import Fernet

def load_key(filename):
    with open(filename, 'rb') as f:
        return f.read()

def decrypt_image(encrypted_image_path, key):
    with open(encrypted_image_path, 'rb') as f:
        encrypted_data = f.read()
    fernet = Fernet(key)
    decrypted_data = fernet.decrypt(encrypted_data)
    return decrypted_data

key = load_key('encryption_key.key')

decrypted_data = decrypt_image('gambar_encrypted.jpg', key)

with open('gambar_decrypted.jpg', 'wb') as f:
    f.write(decrypted_data)
```
    
- Maka akan menghasilkan sebuah gambar, belum selesai. Di gambar ini kita perlu mengedit rgb supaya teks yang hilang muncul, simplenya bisa menggunakan aperisolve.com. Solved!
