# README: Penjelasan Per Baris Kode Linked List

---

## **`class Node:`**

Mendefinisikan sebuah class bernama **Node**, yaitu struktur dasar pada Linked List. Setiap Node menyimpan data dan alamat (pointer) menuju Node berikutnya.

---

## **`def __init__(self, data=None, pointer=None):`**

Ini adalah **constructor** yang otomatis dijalankan saat membuat Node baru.

* `data` → nilai/isi yang disimpan dalam node.
* `pointer` → referensi ke node berikutnya.

---

## **`self.data = data`**

Menyimpan nilai yang diterima ke atribut `data` milik node.
Atribut ini dapat berupa string, angka, atau tipe data lain.

---

## **`self.next = pointer`**

Menyimpan alamat node berikutnya.
Dalam Linked List, pointer ini menentukan ke mana node tersebut terhubung.

---

#  CLASS LINKEDLIST

## **`class LinkedList:`**

Membuat struktur besar Linked List yang berisi banyak Node.
Semua operasi seperti insert, remove, dan print berada di dalam class ini.

---

## **`def __init__(self):`**

Constructor LinkedList.

---

## **`self.head = None`**

`head` adalah node pertama dalam Linked List.
Nilainya `None` karena list baru dibuat dan belum ada data.

---

#  insert_at_first()

## **`def insert_at_first(self, data):`**

Fungsi untuk menambah elemen di bagian paling depan Linked List.

---

## **`node = Node(data, self.head)`**

Membuat node baru dengan:

* `data` → nilai baru
* `self.head` → menjadi pointer node tersebut sehingga mengarah ke head lama

Ini membuat node baru otomatis berada di depan.

---

## **`self.head = node`**

Mengubah head menjadi node baru.
Artinya node baru resmi menjadi elemen pertama.

---

#  insert_at_last()

## **`def insert_at_last(self, data):`**

Fungsi untuk menambah elemen pada bagian akhir Linked List.

---

## **`if self.head is None:`**

Jika head kosong → list masih kosong.

---

## **`self.head = Node(data)`**

Karena list kosong, node yang pertama ditambahkan otomatis menjadi head.

---

## **`else:`**

Jika head tidak kosong → cari node paling akhir.

---

## **`node_sekarang = self.head`**

Mulai pencarian dari node pertama.

---

## **`while node_sekarang.next:`**

Loop berjalan selama masih ada node berikutnya.
Digunakan untuk menemukan node paling akhir.

---

## **`node_sekarang = node_sekarang.next`**

Pindah ke node berikutnya sampai pointer berikutnya kosong.

---

## **`node = Node(data)`**

Membuat node baru tanpa pointer.

---

## **`node_sekarang.next = node`**

Menghubungkan node terakhir dengan node baru.
Node baru menjadi elemen paling akhir.

---

#  insert_at(index)

## **`def insert_at(self, index, data):`**

Menambahkan node baru pada posisi tertentu.

---

## **`if index < 0 or index > self.length() - 1:`**

Memastikan index valid, tidak boleh negatif atau melebihi panjang list.

---

## **`print("index tidak valid")`**

Menampilkan pesan jika index salah.

---

## **`elif index == 0:`**

Jika index 0 → berarti sisipkan di awal.

---

## **`self.insert_at_first(data)`**

Memanggil fungsi khusus untuk insert di depan.

---

## **`urutan = 0`**

Variabel penghitung posisi saat traversal.

---

## **`node_sekarang = self.head`**

Mulai dari node paling depan.

---

## **`while urutan < index - 1:`**

Loop untuk menuju node sebelum posisi tempat data ingin dimasukkan.

---

## **`urutan += 1`**

Meningkatkan hitungan posisi.

---

## **`node_sekarang = node_sekarang.next`**

Pindah ke node selanjutnya.

---

## **`node = Node(data, node_sekarang.next)`**

Node baru dibuat dan menunjuk ke node setelahnya.
Ini menjaga struktur list tetap benar.

---

## **`node_sekarang.next = node`**

Menghubungkan node sebelumnya ke node baru.
Node berhasil disisipkan pada posisi yang diinginkan.

---

#  remove_first()

## **`def remove_first(self):`**

Menghapus elemen pertama dalam list.

---

## **`if self.head is None:`**

Jika kosong → tidak ada yang bisa dihapus.

---

## **`print("tidak ada data yang bisa dihapus")`**

Memberi tahu bahwa list kosong.

---

## **`self.head = self.head.next`**

Jika ada data → cukup geser head ke node berikutnya.
Node pertama otomatis terhapus.

---

#  remove_last()

## **`def remove_last(self):`**

Menghapus elemen paling akhir.

---

## **`if self.head is None:`**

List kosong → tidak bisa hapus.

---

## **`elif self.head.next is None:`**

Jika hanya ada 1 node → hapus dengan menjadikan head = None.

---

## **`node_sebelumnya = None`**

Menyimpan node sebelum node sekarang.

---

## **`node_sekarang = self.head`**

Mulai dari awal list.

---

## **`while node_sekarang.next:`**

Loop mencari node terakhir.

---

## **`node_sebelumnya = node_sekarang`**

Node sebelumnya dipindahkan.

---

## **`node_sekarang = node_sekarang.next`**

Bergerak maju ke node selanjutnya.

---

## **`node_sebelumnya.next = None`**

Menghapus node terakhir dengan memutus pointer.

---

#  remove_at(index)

## **`def remove_at(self, index):`**

Menghapus node pada posisi tertentu.

---

## **`if index < 0 or index >= self.length():`**

Validasi index.

---

## **`print("index invalid")`**

Memberitahu jika index salah.

---

## **`elif index == 0:`**

Jika index 0 → gunakan remove_first().

---

## **`node_sekarang = self.head`**

Mulai traversal.

---

## **`urutan = 0`**

Penghitung posisi.

---

## **`while urutan < index - 1:`**

Mencari node sebelum node yang akan dihapus.

---

## **`node_sekarang = node_sekarang.next`**

Bergerak ke kanan.

---

## **`urutan += 1`**

Menambah hitungan posisi.

---

## **`node_sekarang.next = node_sekarang.next.next`**

Memotong node target sehingga terhapus dari rantai.

---

#  print()

## **`def print(self):`**

Menampilkan semua data dalam Linked List.

---

## **`if self.head is None:`**

Jika list kosong → tampilkan informasi.

---

## **`text_print = ''`**

Variabel untuk menyimpan teks hasil.

---

## **`node_sekarang = self.head`**

Mulai dari head.

---

## **`while node_sekarang:`**

Loop menelusuri setiap node.

---

## **`text_print += str(node_sekarang.data) + " → "`**

Tambahkan data node ke teks.

---

## **`node_sekarang = node_sekarang.next`**

Pindah ke node selanjutnya.

---

## **`print(text_print)`**

Cetak seluruh isi Linked List.

---

#  length()

## **`def length(self):`**

Menghitung jumlah node.

---

## **`urutan = 0`**

Penghitung banyaknya node.

---

## **`data_sekarang = self.head`**

Mulai dari node pertama.

---

## **`while data_sekarang:`**

Selama masih ada node.

---

## **`data_sekarang = data_sekarang.next`**

Bergerak ke node selanjutnya.

---

## **`urutan += 1`**

Menambah hitungan node.

---

## **`return urutan`**

Mengembalikan total jumlah node.

---

#  Bagian MAIN PROGRAM

## **`LL = LinkedList()`**

Membuat objek Linked List.

---

## Insert data

* `insert_at_first("jeruk")` → jeruk jadi head
* `insert_at_first("mangga")` → mangga di depan jeruk
* `insert_at_first("manggis")` → manggis paling depan
* `insert_at_last("apel")` → apel di belakang
* `insert_at(2, "anggur")` → anggur masuk posisi index 2

---

## Remove data

* `remove_first()` → hapus elemen pertama
* `remove_last()` → hapus elemen terakhir
* `remove_at(1)` → hapus index 1
* `remove_at(1)` → hapus index 1 lagi

---

## Print final list

`LL.print()` → mencetak isi list.

---

## Print panjang list

`print(LL.length())` → menampilkan jumlah node saat ini.

---



Penjelasan sudah disusun **kode → penjelasan rinci per baris**, lengkap dalam satu README.
