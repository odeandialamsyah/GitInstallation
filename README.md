# 💻 Instalasi Git & Koneksi ke Akun GitHub (Windows)

Panduan ini membantu kamu menginstal Git di Windows dan menghubungkannya langsung ke akun GitHub menggunakan **SSH Key**.

---

## 🧩 1. Instal Git

1. Kunjungi: https://git-scm.com/download/win
2. Download dan jalankan installer.
3. Ikuti langkah instalasi **(gunakan pengaturan default kecuali tahu yang kamu ubah)**.
4. Setelah selesai, buka **Git Bash**.

---

## 🛠️ 2. Cek Git Sudah Terinstal

```bash
git --version
```

Jika muncul versi Git, berarti berhasil.

---

## 👤 3. Konfigurasi Git dengan Identitas GitHub

```bash
git config --global user.name "Nama GitHub Kamu"
git config --global user.email "emailgithub@example.com"
```

> Gunakan **email yang sama dengan akun GitHub kamu.**

---

## 🔐 4. Buat SSH Key untuk GitHub

```bash
ssh-keygen -t ed25519 -C "emailgithub@example.com"
```

> Tekan ENTER terus sampai selesai (jangan isi passphrase jika tidak mau pakai).

Lokasi default: `C:\Users\NAMA_KAMU\.ssh\id_ed25519.pub`

---

## 📋 5. Salin Public Key

```bash
cat ~/.ssh/id_ed25519.pub
```

> Salin seluruh isi output yang muncul.

---

## 🌐 6. Tambahkan SSH Key ke GitHub

1. Masuk ke [GitHub](https://github.com)
2. Klik foto profil > **Settings**
3. Masuk ke **SSH and GPG keys**
4. Klik **New SSH key**
5. Tempelkan key yang tadi kamu salin
6. Simpan

---

## ✅ 7. Tes Koneksi ke GitHub

```bash
ssh -T git@github.com
```

Jika berhasil, akan muncul:

```
Hi username! You've successfully authenticated...
```

---

## 📦 8. Clone Repository dengan SSH

```bash
git clone git@github.com:username/nama-repo.git
```

---

## 🚀 Sekarang Kamu Siap Menggunakan Git & GitHub!

Setiap push/pull ke GitHub akan otomatis lewat koneksi SSH tanpa perlu login ulang.  
Gunakan `git status`, `git add`, `git commit`, dan `git push` untuk mengelola kode.

---

📌 **Catatan Tambahan**
- Pastikan SSH Agent berjalan: `eval $(ssh-agent -s)`
- Tambahkan key jika perlu: `ssh-add ~/.ssh/id_ed25519`
