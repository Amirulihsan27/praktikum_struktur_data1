#  Implementasi Stack dan Queue di Python


#  1. Implementasi **Stack** di Python

Stack adalah struktur data yang bekerja dengan aturan **LIFO (Last In, First Out)**. Artinya, **data yang dimasukkan terakhir akan keluar duluan**.



---

##  Kode Program Stack

```python
# stack and stack operations
stack = []

# Push
stack.append('A')
stack.append('B')
stack.append('C')
print("Stack: ", stack)

# Pop
element = stack.pop()
print("Pop: ", element)

# Peek
topElement = stack[-1]
print("Peek: ", topElement)

# isEmpty
isEmpty = not bool(stack)
print("isEmpty: ", isEmpty)

# Size
print("Size: ", len(stack))
```

---

##  Penjelasan  Stack

###  1. **Inisialisasi Stack**

```python
stack = []
```

Artinya kita membuat tempat kosong untuk menampung data stack.

---

###  2. **Push (Menambah Data)**

```python
stack.append('A')
```

`append()` memasukkan data ke **atas** tumpukan.

Urutan data masuk:

* Masuk 'A' → `['A']`
* Masuk 'B' → `['A', 'B']`
* Masuk 'C' → `['A', 'B', 'C']`

---

###  3. **Pop (Menghapus Data Teratas)**

```python
stack.pop()
```

`pop()` **menghapus dan mengambil** elemen paling atas.

Dalam contoh, elemen paling atas adalah `'C'`, maka `C` yang keluar.

---

###  4. **Peek (Melihat Elemen Teratas)**

```python
stack[-1]
```

`[-1]` berarti melihat elemen paling atas **tanpa menghapusnya**.

Setelah `C` keluar, data teratas adalah `'B'`.

---

###  5. **isEmpty**

```python
not bool(stack)
```

Digunakan untuk mengecek apakah stack kosong.

* `True` → kosong
* `False` → ada isinya

---

###  6. **Size (Jumlah Elemen)**

```python
len(stack)
```

Menghitung berapa banyak elemen dalam stack.

---

##  Contoh Output Stack

```
Stack:  ['A', 'B', 'C']
Pop:  C
Peek:  B
isEmpty:  False
Size:  2
```

---

#  2. Implementasi **Queue** di Python

Queue adalah struktur data yang bekerja dengan aturan **FIFO (First In, First Out)**. Artinya **data yang masuk pertama akan keluar pertama**.



---

##  Kode Program Queue

```python
queue = []

# Enqueue
queue.append('A')
queue.append('B')
queue.append('C')
print("Queue: ", queue)

# Dequeue
element = queue.pop(0)
print("Dequeue: ", element)

# Peek
frontElement = queue[0]
print("Peek: ", frontElement)

# isEmpty
isEmpty = not bool(queue)
print("isEmpty: ", isEmpty)

# Size
print("Size: ", len(queue))
```

---

##  Penjelasan  Queue

###  1. **Inisialisasi Queue**

```python
queue = []
```

Membuat tempat untuk menampung data antrian.

---

###  2. **Enqueue (Menambah Data)**

```python
queue.append('A')
```

`append()` menambah data ke **belakang antrian**.

Urutannya:

* `'A'` → `['A']`
* `'B'` → `['A', 'B']`
* `'C'` → `['A', 'B', 'C']`

---

###  3. **Dequeue (Menghapus Data Depan)**

```python
queue.pop(0)
```

`pop(0)` menghapus elemen index 0 (paling depan).

Yang keluar pertama adalah `'A'`.

---

###  4. **Peek (Melihat Elemen Depan)**

```python
queue[0]
```

Melihat elemen terdepan tanpa menghapusnya.
Setelah `'A'` keluar, elemen depannya adalah `'B'`.

---

###  5. **isEmpty**

```python
not bool(queue)
```

Mengecek apakah queue kosong.

---

###  6. **Size**

```python
len(queue)
```

Menghitung jumlah elemen dalam antrian.

---

##  Contoh Output Queue

```
Queue:  ['A', 'B', 'C']
Dequeue:  A
Peek:  B
isEmpty:  False
Size:  2
```



---

##  Kesimpulan Queue

* Queue adalah struktur data antrian yang bekerja dengan prinsip **FIFO (First In, First Out)**.
* Elemen yang **pertama masuk akan menjadi elemen pertama yang keluar**, seperti antrian di dunia nyata.
* Implementasi queue di Python dapat dilakukan menggunakan **list**.
* Operasi utama queue:
  * **Enqueue** → menambah data ke belakang antrian.
  * **Dequeue** → menghapus data dari depan antrian.
  * **Peek** → melihat data terdepan tanpa menghapus.
  * **isEmpty** → mengecek apakah antrian kosong.
  * **Size** → menghitung jumlah elemen yang ada di dalam antrian.


##  Kesimpulan Stack

* Stack adalah struktur data tumpukan yang bekerja dengan prinsip **LIFO (Last In, First Out)**.
* Elemen yang **terakhir dimasukkan adalah elemen pertama yang keluar**.
* Implementasi stack di Python bisa menggunakan list.
* Operasi dasar pada stack:
  * **Push** → menambahkan elemen ke atas tumpukan.
  * **Pop** → menghapus elemen paling atas.
  * **Peek / Top** → melihat elemen paling atas tanpa menghapus.
  * **isEmpty** → mengecek apakah stack kosong.
  * **Size** → menghitung jumlah elemen dalam stack.

