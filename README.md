**Nama : Nabilla Tsani Ayasi**

**NIM : H1D022058**

**Shift : F**

## CRUD Data Mahasiswa

### 1. Create (Tambah Data Mahasiswa)
![Screenshot 2024-11-13 204911](https://github.com/user-attachments/assets/f463e871-b809-4f6f-bae6-3dd17bba005f)
![Screenshot 2024-11-13 204936](https://github.com/user-attachments/assets/b3c4b9cb-8fbf-4017-9699-f8942e08e640)

![Screenshot 2024-11-13 205004](https://github.com/user-attachments/assets/7530f23f-017a-4414-b136-d2c072e42a00)
![Screenshot 2024-11-13 205020](https://github.com/user-attachments/assets/4df4d891-97ed-438e-bbdc-2d022916ca33)

   - Fungsi yang digunakan: `tambahMahasiswa()`.
   - Proses yang dilakukan Pengguna:
     1. Menekan tombol 'Tambah Mahasiswa'.
     2. Mengisi formulir tambah data yang berisi kolom Nama Mahasiswa dan Jurusan Mahasiswa.
     3. Menekan tombol 'Tambah Mahasiswa'.
   - Proses yang dilakukan Sistem:
     1. Memeriksa apakah `nama` dan `jurusan` telah diisi.
     2. Jika semua data ada, data mahasiswa disimpan dalam objek `data` yang berisi properti `nama` dan `jurusan`.
     3. Fungsi `api.tambah()` dipanggil untuk mengirim data ke server melalui endpoint `tambah.php`.
     4. Setelah berhasil menambahkan data, fungsi `getMahasiswa()` dipanggil untuk memperbarui daftar mahasiswa.
     5. Modal tambah mahasiswa ditutup dengan `this.modal.dismiss()`.

### 2. Read (Tampil Data Mahasiswa)
![Screenshot 2024-11-13 205020](https://github.com/user-attachments/assets/4df4d891-97ed-438e-bbdc-2d022916ca33)
   - Fungsi yang digunakan: `getMahasiswa()`.
   - Proses yang dilakukan Pengguna:
     1. Masuk ke sistem dan otomatis menampilkan halaman Data Mahasiswa
   - Proses yang dilakukan Sistem:
     1. Fungsi ini dipanggil saat halaman dimuat (`ngOnInit()`).
     2. Menggunakan `api.tampil()` untuk mengambil data dari endpoint `tampil.php`.
     3. Jika pengambilan data berhasil, data disimpan dalam variabel `dataMahasiswa`.
     4. Data mahasiswa ini kemudian dapat ditampilkan pada halaman.

### 3. Update (Edit Data Mahasiswa)
![Screenshot 2024-11-13 205020](https://github.com/user-attachments/assets/4df4d891-97ed-438e-bbdc-2d022916ca33)
![Screenshot 2024-11-13 205037](https://github.com/user-attachments/assets/1d21bb30-3f0d-4f14-9830-f24bf8c0dfa1)

![Screenshot 2024-11-13 205057](https://github.com/user-attachments/assets/9e799af8-3746-43b7-ab0d-c0f7028dd7ca)
![Screenshot 2024-11-13 205111](https://github.com/user-attachments/assets/f3f5a0b1-59d1-4074-83b1-f26c89c1f1c3)
   - Fungsi yang digunakan: `editMahasiswa()`.
   - Proses yang dilakukan Pengguna:
     1. Menekan tombol 'Edit' pada data mahasiswa yang ingin di edit.
     2. Mengisi formulir update data yang berisi kolom Nama Mahasiswa dan Jurusan Mahasiswa, kolom yang di isi adalah kolom yang ingin diubah atau di update.
     3. Menekan tombol 'Edit Mahasiswa'.
   - Proses yang dilakukan Sistem:
     1. Fungsi `openModalEdit()` memanggil `ambilMahasiswa()` untuk mengambil data mahasiswa tertentu berdasarkan `id` yang diterima.
     2. Data mahasiswa ditampilkan di modal edit.
     3. Setelah pengguna melakukan perubahan, fungsi `editMahasiswa()` dipanggil untuk menyimpan perubahan.
     4. Objek `data` yang berisi `id`, `nama`, dan `jurusan` dikirim ke server melalui fungsi `api.edit()` dengan endpoint `edit.php`.
     5. Jika berhasil, fungsi `getMahasiswa()` dipanggil kembali untuk memuat ulang data yang diperbarui, dan modal edit ditutup.

### 4. Delete (Hapus Data Mahasiswa)
![Screenshot 2024-11-13 205543](https://github.com/user-attachments/assets/e02753f8-3683-4a11-9ef4-7db308bc67d9)
![Screenshot 2024-11-13 205604](https://github.com/user-attachments/assets/d4074b1f-8469-4b3f-8b7d-ae811da3e78f)
   - Fungsi yang digunakan: `hapusMahasiswa(id: any)`.
   - Proses yang dilakukan Pengguna:
     1. Menekan tombol 'Hapus' pada data mahasiswa yang ingin di hapus.
     2. Memilih pilihan yang ada pada alert Konfirmasi Hapus, ada 2 pilihan yaitu 'Hapus' dan 'Batal'.
     3. Jika memilih 'Batal', maka proses delete dibatalkan.
     4. Jika memilih 'Hapus', maka proses delete akan dilanjutkan, dan data akan dihapus dari database.
   - Proses yang dilakukan Sistem:
     1. Saat pengguna memilih opsi hapus, sebuah **AlertController** muncul sebagai konfirmasi.
     2. Jika pengguna menekan "Hapus", fungsi `api.hapus()` dipanggil dengan mengirim `id` ke endpoint `hapus.php?id=`.
     3. Jika penghapusan berhasil, `getMahasiswa()` dipanggil untuk memperbarui daftar mahasiswa.
     4. Jika gagal, pesan error akan muncul di console.

### Penjelasan Lainnya
- **Modal Controller** digunakan untuk mengelola pembukaan dan penutupan modal tambah dan edit mahasiswa.
- **resetModal()** membersihkan data `id`, `nama`, dan `jurusan` untuk memastikan data lama tidak terbawa saat membuka modal baru.


