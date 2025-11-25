
---

# **Linked List **

---

## **Pengertian Linked List**

Linked List adalah struktur data yang tersusun dari node-node.
Setiap node menyimpan **data** dan **pointer** (alamat) ke node berikutnya.
Struktur ini fleksibel karena ukurannya dapat berubah secara dinamis, memudahkan proses **insert** dan **remove** dibanding array.

---

# **Kode Lengkap Linked List**

```python
class Node:
    def __init__(self, data=None, pointer=None):
        self.data = data
        self.next = pointer


class LinkedList:
    def __init__(self):
        self.head = None

    def insert_at_first(self, data):
        node = Node(data, self.head)
        self.head = node

    def insert_at_last(self, data):
        if self.head is None:
            self.head = Node(data)
        else:
            node_sekarang = self.head
            while node_sekarang.next:
                node_sekarang = node_sekarang.next

            node = Node(data)
            node_sekarang.next = node

    def insert_at(self, index, data):
        if index < 0 or index > self.length() - 1:
            print("index tidak valid")
        elif index == 0:
            self.insert_at_first(data)
        else:
            urutan = 0
            node_sekarang = self.head

            while urutan < index - 1:
                urutan += 1
                node_sekarang = node_sekarang.next

            node = Node(data, node_sekarang.next)
            node_sekarang.next = node

    def remove_first(self):
        if self.head is None:
            print("tidak ada data yang bisa dihapus")
        else:
            self.head = self.head.next

    def remove_last(self):
        if self.head is None:
            print("tidak ada data yang bisa dihapus")
        elif self.head.next is None:
            self.head = None
        else:
            node_sebelumnya = None
            node_sekarang = self.head

            while node_sekarang.next:
                node_sebelumnya = node_sekarang
                node_sekarang = node_sekarang.next

            node_sebelumnya.next = None

    def remove_at(self, index):
        if index < 0 or index >= self.length():
            print("index invalid")
        elif index == 0:
            self.remove_first()
        else:
            urutan = 0
            node_sekarang = self.head

            while urutan < index - 1:
                node_sekarang = node_sekarang.next
                urutan += 1

            node_sekarang.next = node_sekarang.next.next

    def print(self):
        if self.head is None:
            print("data kosong")
        else:
            text_print = ''
            node_sekarang = self.head

            while node_sekarang:
                text_print += str(node_sekarang.data) + " ==> "
                node_sekarang = node_sekarang.next

            print(text_print)

    def length(self):
        urutan = 0
        data_sekarang = self.head

        while data_sekarang:
            data_sekarang = data_sekarang.next
            urutan += 1

        return urutan


LL = LinkedList()

# insert
LL.insert_at_first("jeruk")
LL.insert_at_first("mangga")
LL.insert_at_first("manggis")
LL.insert_at_last("apel")
LL.insert_at(2, "anggur")

# remove
LL.remove_first()
LL.remove_last()
LL.remove_at(1)
LL.remove_at(1)

# print
LL.print()
print(LL.length())
```

---

# **Penjelasan Lengkap Per Baris**

---

## **1. Membuat Class Node**

```python
class Node:
    def __init__(self, data=None, pointer=None):
        self.data = data
        self.next = pointer
```

**Penjelasan:**

* `class Node:`
  Membuat blueprint untuk node yang akan menjadi elemen LinkedList.

* `def __init__(self, data=None, pointer=None):`
  Konstruktor untuk mengisi data awal dan pointer.

* `self.data = data`
  Menyimpan isi data pada node.

* `self.next = pointer`
  Menyimpan alamat node selanjutnya (default = None).

---

## **2. Membuat Class LinkedList**

```python
class LinkedList:
    def __init__(self):
        self.head = None
```

**Penjelasan:**

* Membuat kelas LinkedList.
* `self.head = None` artinya LinkedList masih kosong (belum ada node).

---

# **FUNGSI INSERT**

---

## **3. Insert di Awal**

```python
def insert_at_first(self, data):
    node = Node(data, self.head)
    self.head = node
```

**Penjelasan:**

* Membuat node baru yang menunjuk head lama.
* Node baru menjadi head yang baru.

---

## **4. Insert di Akhir**

```python
def insert_at_last(self, data):
    if self.head is None:
        self.head = Node(data)
    else:
        node_sekarang = self.head
        while node_sekarang.next:
            node_sekarang = node_sekarang.next

        node = Node(data)
        node_sekarang.next = node
```

**Penjelasan:**

* Jika list kosong → data langsung jadi head.
* Jika tidak kosong → loop sampai node terakhir.
* Tambahkan node baru di akhir.

---

## **5. Insert di Posisi Tertentu**

```python
def insert_at(self, index, data):
    if index < 0 or index > self.length() - 1:
        print("index tidak valid")
    elif index == 0:
        self.insert_at_first(data)
    else:
        urutan = 0
        node_sekarang = self.head

        while urutan < index - 1:
            urutan += 1
            node_sekarang = node_sekarang.next

        node = Node(data, node_sekarang.next)
        node_sekarang.next = node
```

**Penjelasan:**

* Cek apakah index valid.
* Jika index = 0 → langsung panggil insert_first.
* Loop hingga posisi sebelum index.
* Buat node baru dan sisipkan di tengah.

---

# **FUNGSI REMOVE**

---

## **6. Remove Awal**

```python
def remove_first(self):
    if self.head is None:
        print("tidak ada data yang bisa dihapus")
    else:
        self.head = self.head.next
```

**Penjelasan:**

* Jika tidak ada data → tidak bisa hapus.
* Jika ada → head langsung digeser ke node berikutnya.

---

## **7. Remove Akhir**

```python
def remove_last(self):
    if self.head is None:
        print("tidak ada data yang bisa dihapus")
    elif self.head.next is None:
        self.head = None
    else:
        node_sebelumnya = None
        node_sekarang = self.head

        while node_sekarang.next:
            node_sebelumnya = node_sekarang
            node_sekarang = node_sekarang.next

        node_sebelumnya.next = None
```

**Penjelasan:**

* Jika kosong → tidak bisa hapus.
* Jika hanya satu data → head = None.
* Jika banyak → loop ke node terakhir.
* Putuskan pointer node terakhir.

---

## **8. Remove Posisi Tertentu**

```python
def remove_at(self, index):
    if index < 0 or index >= self.length():
        print("index invalid")
    elif index == 0:
        self.remove_first()
    else:
        urutan = 0
        node_sekarang = self.head

        while urutan < index - 1:
            node_sekarang = node_sekarang.next
            urutan += 1

        node_sekarang.next = node_sekarang.next.next
```

**Penjelasan:**

* Validasi index.
* Jika index 0 → gunakan remove_first.
* Loop sampai sebelum index.
* Hapus node dengan memutus pointer.

---

# **FUNGSI CETAK**

```python
def print(self):
    if self.head is None:
        print("data kosong")
    else:
        text_print = ''
        node_sekarang = self.head

        while node_sekarang:
            text_print += str(node_sekarang.data) + " ==> "
            node_sekarang = node_sekarang.next

        print(text_print)
```

**Penjelasan:**

* Jika kosong → tampilkan "data kosong".
* Loop semua node dan gabungkan text.
* Cetak hasil linked list.

---

# **FUNGSI LENGTH**

```python
def length(self):
    urutan = 0
    data_sekarang = self.head

    while data_sekarang:
        data_sekarang = data_sekarang.next
        urutan += 1

    return urutan
```

**Penjelasan:**

* Menghitung jumlah node dari head sampai akhir.

---

# **BAGIAN PENGUJIAN**

---

## **Membuat LinkedList**

```python
LL = LinkedList()
```

---

## **Insert Data**

```python
LL.insert_at_first("jeruk")
LL.insert_at_first("mangga")
LL.insert_at_first("manggis")
LL.insert_at_last("apel")
LL.insert_at(2, "anggur")
```

**Penjelasan:**

* Tambah 3 data di awal.
* Tambah data di akhir.
* Tambah data pada index 2.

---

## **Remove Data**

```python
LL.remove_first()
LL.remove_last()
LL.remove_at(1)
LL.remove_at(1)
```

**Penjelasan:**

* Hapus data pertama.
* Hapus data terakhir.
* Hapus index 1 → dua kali berturut-turut.

---

## **Cetak Output**

```python
LL.print()
print(LL.length())
```

**Penjelasan:**

* Cetak isi linked list.
* Cetak jumlah data.

---


