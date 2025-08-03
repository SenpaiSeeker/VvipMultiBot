# VVIP Multi-Bot Manager

Sebuah platform bot Telegram canggih yang dirancang tidak hanya untuk mengelola satu grup VVIP, tetapi untuk **membuat dan mengelola seluruh armada bot VVIP**. Bot utama bertindak sebagai pusat kontrol, memungkinkan pemilik untuk memberikan akses kepada pengguna lain untuk meluncurkan bot VVIP mereka sendiri, lengkap dengan masa aktif, panel kontrol, dan sistem pembayaran yang terisolasi.

## ⭐ Fitur Unggulan

- **Sistem Multi-Bot Canggih**:
  - **Bot Induk (Main Bot)**: Berfungsi sebagai pusat manajemen untuk membuat bot-bot baru.
  - **Pembuatan Bot oleh Pengguna**: Owner utama dapat memberikan akses kepada pengguna terpercaya (`/akses`) untuk membuat bot VVIP mereka sendiri.
  - **Manajemen Bot Individual**: Setiap bot yang dibuat memiliki database, daftar VVIP, member, dan API Keys (Violet & Gemini) yang terpisah.
  - **Masa Aktif Bot**: Bot yang dibuat memiliki masa aktif 30 hari, yang dapat diperpanjang melalui permintaan kepada owner utama.
  - **Panel Kontrol Terpusat**: Owner utama dapat melihat semua bot yang aktif (`/allbots`) dan mengatur masa aktifnya secara manual (`/extend`).

- **Manajemen VVIP & Paket**:
  - **Panel Kontrol Intuitif**: Tambah, hapus, dan kelola paket VVIP dengan mudah melalui tombol interaktif di dalam "⚙️ Panel Pengaturan ⚙️".
  - **Harga Dinamis**: Atur harga normal dan harga promosi untuk setiap paket.
  - **Teks yang Dapat Disesuaikan**: Personalisasi teks deskripsi untuk setiap paket dan promo.

- **Pembayaran dan Akses Otomatis**:
  - **Integrasi QRIS**: Terhubung dengan VioletMediaPay untuk menghasilkan kode QRIS unik per transaksi.
  - **Verifikasi Otomatis**: Bot secara mandiri memverifikasi pembayaran dan memberikan akses instan.
  - **Konten Terlindungi**: Tautan grup dikirim sebagai pesan yang dilindungi untuk mencegah penerusan.
  - **Dukungan Donasi**: Terima dukungan dari pengguna melalui Telegram Stars (⭐), dengan notifikasi instan kepada pemilik bot.

- **Manajemen Anggota yang Komprehensif**:
  - **Daftar Member VVIP**: Lihat daftar semua anggota yang bergabung melalui bot, lengkap dengan detail dan tombol untuk menendang.
  - **Cek Member Aktif Real-time**: Periksa daftar anggota langsung dari grup/channel target untuk memastikan tidak ada penyusup.

- **Peralatan Admin yang Kuat**:
  - **Fitur Broadcast**: Kirim pesan massal ke semua pengguna yang pernah memulai bot Anda.
  - **Manajemen API per-Bot**: Setiap pemilik bot dapat mengatur API Key Violet (pembayaran) dan Gemini (AI) mereka sendiri, memastikan layanan tetap terisolasi.
  - **Pemulihan Database**: Pulihkan seluruh data bot dari backup `.zip` dengan perintah `/restore`.
  - **Eksekusi Kode**: Perintah `/eval` untuk debugging dan eksekusi kode tingkat lanjut (hanya untuk Owner Utama).

- **Kustomisasi & Personalisasi**:
  - **Multi-Bahasa**: Bot mendukung Bahasa Indonesia dan Inggris. Pengguna dapat memilih bahasa pilihan mereka melalui menu pengaturan.
  - **Kustomisasi Tampilan**: Pemilik bot dapat dengan mudah mengubah foto dan teks sambutan (`/start`) melalui panel pengaturan. Gunakan perintah `/empty` untuk kembali ke pengaturan default.
  - **Asisten AI**: Integrasi dengan Google Gemini untuk fitur hiburan "Cek Khodam" dan chatbot cerdas yang dapat menjawab pertanyaan pengguna seputar bot.

## 🚀 Pengaturan dan Instalasi

Ikuti langkah-langkah ini untuk menjalankan platform bot Anda.

### 1. Prasyarat

- Python 3.8 atau lebih tinggi.
- Token Bot Telegram untuk **Bot Utama**.
- API ID dan API Hash dari [my.telegram.org](https://my.telegram.org).

### 2. Kloning Repositori

Pertama, kloning repositori ini ke mesin lokal atau server Anda.
```bash
git clone https://github.com/your-username/vvip-git
cd vvip
```

### 3. Instalasi Dependensi

Instal semua pustaka Python yang diperlukan menggunakan file `requirements.txt`.
```bash
pip3 install -r requirements.txt
```

### 4. Konfigurasi Menggunakan Skrip

Bot ini memerlukan file konfigurasi yang berisi kunci API Anda. Gunakan skrip `config.sh` yang telah disediakan untuk mempermudah proses ini.

1.  Jalankan skrip di terminal Anda:
    ```bash
    bash config.sh
    ```

2.  Skrip akan meminta Anda untuk memasukkan informasi berikut secara berurutan:
    - **API_ID**: API ID Telegram Anda.
    - **API_HASH**: API Hash Telegram Anda.
    - **BOT_TOKEN**: Token Bot Telegram Anda (ini akan menjadi **Bot Utama/Induk**).
    - **OWNER_ID**: ID Pengguna Telegram numerik Anda. Anda bisa mendapatkannya dari bot seperti `@userinfobot`.
    - **Filename**: Nama yang ingin Anda berikan pada file environment Anda. Cukup tekan **Enter** untuk menggunakan nama default (`.env`) atau ketik nama lain (contoh: `mybot.env`).

    Setelah selesai, skrip akan membuat file environment (misalnya, `.env`) yang berisi semua kredensial Anda.

### 5. Menjalankan Bot

Setelah file konfigurasi dibuat, Anda dapat memulai bot.

Gunakan perintah berikut, ganti `nama_file.env` dengan nama file yang Anda buat pada langkah sebelumnya.

```bash
python3 main.py nama_file.env
```

**Contoh Skenario:**

-   Jika saat menjalankan `config.sh` Anda menekan **Enter** untuk nama file (default `.env`):
    ```bash
    python3 main.py .env
    ```
    Atau lebih singkat lagi (karena `.env` adalah default):
    ```bash
    python3 main.py
    ```

-   Jika saat menjalankan `config.sh` Anda mengetik `mybot.env` sebagai nama file:
    ```bash
    python3 main.py mybot.env
    ```

Bot sekarang akan dimulai, dan Anda akan melihat pesan konfirmasi di terminal.

## 📖 Panduan Penggunaan

### Untuk Owner Utama (Super Admin)

Anda adalah administrator tertinggi dengan kontrol penuh atas sistem.

1.  **Mulai Bot**: Kirim `/start` ke bot utama Anda.
2.  **Memberikan Akses**: Untuk mengizinkan pengguna lain membuat bot, gunakan perintah:
    ```
    /akses <user_id atau @username>
    ```
    Ini akan membuka panel untuk memberi atau mencabut hak "Create Bot".
3.  **Melihat Semua Bot**: Gunakan perintah `/allbots` untuk melihat daftar semua bot yang telah dibuat oleh pengguna, lengkap dengan ID, pemilik, dan sisa masa aktif. Panel ini memiliki navigasi halaman.
4.  **Mengatur Durasi Bot**: Gunakan perintah `/extend` untuk menambah atau mengurangi masa aktif bot manapun secara manual.
    ```
    /extend <bot_id> <jumlah_hari>
    # Contoh: /extend 123456789 30 (menambah 30 hari)
    # Contoh: /extend 123456789 -10 (mengurangi 10 hari)
    ```
5.  **Menyetujui Perpanjangan**: Ketika seorang pemilik bot meminta perpanjangan, Anda akan menerima pesan di chat pribadi dengan tombol untuk menyetujui atau menolak.
6.  **Backup & Restore**: Bot akan secara otomatis mengirimkan file backup `database.zip` secara berkala. Untuk memulihkan, balas file tersebut dengan perintah `/restore`. **PENTING: Restart bot setelah restore berhasil.**

### Untuk Pemilik Bot (Pengguna)

Setelah mendapatkan akses dari Owner Utama, Anda dapat membuat dan mengelola bot VVIP Anda sendiri.

1.  **Membuat Bot**: Tekan tombol **"🤖 Buat Bot"** di bot utama dan ikuti instruksi untuk memasukkan `API_ID`, `API_HASH`, dan `BOT_TOKEN` Anda. Setelah berhasil, bot Anda akan langsung aktif selama 30 hari.
2.  **Mengelola Bot**:
    - Mulai bot **pribadi Anda** dengan perintah `/start`.
    - Anda akan melihat menu **"⚙️ Panel Pengaturan ⚙️"**. Di sinilah Anda mengelola semua aspek bot Anda: menambah/menghapus paket VVIP, mengecek anggota, mengatur API keys, mengubah foto/teks start, dan melakukan broadcast **hanya untuk pengguna bot Anda**.
3.  **Meminta Perpanjangan**:
    - Di bot **utama**, tekan tombol **"📦 Bot Saya"**.
    - Pilih bot Anda dari daftar, lalu klik **"➕ Minta Perpanjangan"**. Permintaan akan dikirimkan ke Owner Utama untuk disetujui.

### Untuk Pengguna Akhir (Pelanggan)

Pelanggan akan berinteraksi dengan bot-bot yang telah dibuat.

1.  **Mulai Bot**: Pengguna mengirim `/start`.
2.  **Pilih Bahasa**: Pengguna dapat memilih bahasa melalui tombol "🌐 Bahasa".
3.  **Lihat Paket**: Klik **"📚 Lihat Daftar VVIP 📚"**.
4.  **Pembayaran**: Setelah memilih paket, pengguna klik "Bayar", menerima QRIS, dan melakukan pembayaran.
5.  **Akses Grup**: Setelah pembayaran terkonfirmasi, bot akan otomatis mengirimkan link undangan grup.

#### ⭐️ Dibuat oleh: [@NorSodikin](https://t.me/NorSodikin)
