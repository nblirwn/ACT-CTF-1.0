Chunky / Image Repair

Writeup:

- Diberikan sebuah .zip, isinya adalah script encryptor dan 25 file gambar yang sudah dipecah.

- Singkatnya, encrypt.py membuat gambar akan terbagi menjadi 25 bagian kecil, 5 bagian horizontal dan 5 bagian vertikal, sehingga total bagian kecil yang dihasilkan adalah 25.

- 25 bagian kecil dari gambar disimpan sebagai file gambar terpisah (chunk_0.jpg hingga chunk_24.jpg). Jadi urut dari atas ke bawah, lalu pindah ke kanan, kemudian dari atas ke bawah, kemudian pindah ke kanan lagi, begitu seterusnya.

- Untuk menyatukan gambar-gambar tersebut seperti semula, bisa menggunakan script di bawah ini:

```from PIL import Image

def merge_chunks(chunks, num_chunks, original_size):

    merged_image = Image.new('RGB', original_size)

    for i, chunk in enumerate(chunks):
        x = (i // num_chunks) * chunk.size[0]
        y = (i % num_chunks) * chunk.size[1]
        merged_image.paste(chunk, (x, y))

    return merged_image

original_size = (500, 500)

chunks = []
num_chunks = 5
for i in range(num_chunks * num_chunks):
    chunk = Image.open(f"chunk_{i}.jpg")
    chunks.append(chunk)

chunks.sort(key=lambda x: int(x.filename.split("_")[1].split(".")[0]))

merged_image = merge_chunks(chunks, num_chunks, original_size)

merged_image.save("gambar_bener.jpg")```

- Maka akan diperoleh gambar utuh, selanjutnya tinggal mengedit sumbu y gambar supaya teks di gambar tersebut dapat dibaca. Solved!
