### 1. Buka Terminal

Anda bisa membuka terminal dengan mencarinya di menu aplikasi atau dengan menekan kombinasi tombol:

```bash
Ctrl + Alt + T
```

### 2. Edit File Konfigurasi GRUB

Gunakan editor teks untuk membuka file konfigurasi GRUB dengan hak akses `root`:

```bash
sudo nano /etc/default/grub
```
### 3. Temukan Baris `GRUB_CMDLINE_LINUX_DEFAULT`

Di dalam file yang terbuka, cari baris yang dimulai dengan:

```
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"
```

### 4. Hapus `quiet splash`

Untuk menghilangkan logo dan menampilkan detail booting, **hapus** teks `"quiet splash"` dari baris tersebut. Barisnya akan menjadi seperti ini:

```
GRUB_CMDLINE_LINUX_DEFAULT=""
```

* Menghapus `quiet` akan menampilkan pesan kernel saat booting.
* Menghapus `splash` akan menghilangkan logo Ubuntu.

### 5. Simpan Perubahan

* **Jika menggunakan `nano`**:
    * Tekan `Ctrl + O` untuk menyimpan.
    * Tekan `Enter` untuk mengonfirmasi nama file.
    * Tekan `Ctrl + X` untuk keluar.

### 6. Perbarui GRUB

Setelah menyimpan perubahan pada file konfigurasi, Anda perlu memberitahu GRUB untuk menerapkan perubahan tersebut. Jalankan perintah berikut di terminal:

```bash
sudo update-grub
```

### 7. Restart Komputer

Terakhir, nyalakan ulang komputer Anda untuk melihat hasilnya:

```bash
sudo reboot
```

Setelah me-restart, Anda seharusnya tidak lagi melihat logo Ubuntu, melainkan teks yang menunjukkan proses booting secara detail.

---

## Mengembalikan Logo

Jika Anda ingin mengembalikan logo splash screen Ubuntu di kemudian hari, cukup ulangi langkah 1 sampai 6, tetapi ubah baris `GRUB_CMDLINE_LINUX_DEFAULT` kembali menjadi:

```
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"
```

Kemudian, 
```bash
sudo update-grub
```
---
