# Review Struktur Kontrol (Control Structures Review)

## Review Struktur Kontrol
Topik ini membahas hal-hal penting terkait pembelajaran di MK sebelumnya (**runtunan, percabangan, perulangan**) yang merupakan prerequisite MK Algoritma dan Pemrograman 2.

## Materi
1. **Runtunan dan Perulangan** (tanpa percabangan)
2. **Percabangan dan Perulangan**


## Diagram Alur
Berikut adalah representasi diagram alur untuk masing-masing struktur kontrol:
- **Sequence**: Instruksi dijalankan secara berurutan
- **Selection**: Program bercabang berdasarkan kondisi (True/False)
- **Iteration**: Eksekusi berulang berdasarkan kondisi

![alt text](https://github.com/khosyikafikirdiat/Algoritma-Pemrograman/blob/main/diagram%20review%20control.png?raw=true)

## Pemaparan Materi
### 1. Runtunan (Sequence)
Runtunan adalah eksekusi perintah secara berurutan dari atas ke bawah tanpa adanya percabangan atau perulangan.

**Contoh dalam Python:**
```python
print("Mulai")
print("Langkah 1")
print("Langkah 2")
print("Selesai")
```

### 2. Percabangan (Selection)
Percabangan adalah struktur kontrol yang memungkinkan eksekusi program bercabang berdasarkan kondisi tertentu. Contoh yang umum digunakan:
- **if-else statement**
- **switch-case statement** (di Python menggunakan dictionary)

**Contoh dalam Python:**
```python
x = 10
if x > 5:
    print("x lebih besar dari 5")
else:
    print("x kurang dari atau sama dengan 5")
```

### 3. Perulangan (Iteration)
Perulangan digunakan untuk mengeksekusi suatu blok kode secara berulang berdasarkan kondisi tertentu. Terdapat dua jenis utama perulangan:
- **Perulangan dengan jumlah tertentu (for loop)**
- **Perulangan berdasarkan kondisi (while dan do-while loop)**

**Contoh For Loop dalam Python:**
```python
for i in range(5):
    print(f"Iterasi ke-{i}")
```

**Contoh While Loop dalam Python:**
```python
count = 0
while count < 5:
    print(f"Count: {count}")
    count += 1
```


