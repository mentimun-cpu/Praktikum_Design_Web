---
# 📘 Panduan Dasar Git & GitHub

Sefruit tutorial instalasi Git, alur kerja dasar Git, dan integrasi dengan GitHub.

---

## 🛠️ Pertama instalasi & Konfigurasi Awal Git

### Windows

1. Unduh installer di [git-scm.com](https://git-scm.com/downloads).
2. Jalankan file `.exe` yang diunduh.
3. Biarkan pengaturan default lalu klik **Next** hingga selesai.

**Verifikasi:**

```bash
git --version
```

---

### macOS

1. Install Homebrew:

   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```
2. Install Git:

   ```bash
   brew install git
   ```

**Verifikasi:**

```bash
git --version
```

---

### Ubuntu/Debian

```bash
sudo apt update
sudo apt install git
```

**Verifikasi:**

```bash
git --version
```

---

### Konfigurasi Awal

Atur nama dan email agar setiap commit tercatat dengan benar:

```bash
git config --global user.name "Nama Kamu"
git config --global user.email "email@kamu.com"
```

---

## 📂 Kedua alur Kerja Dasar Git (Lokal)

**1. Buat Folder & Inisialisasi Repo**

```bash
mkdir proyek-web
cd proyek-web
git init
```

**2. Buat File**

```bash
echo "<h1>Selamat Datang</h1>" > index.html
mkdir css
echo "body { font-family: sans-serif; }" > css/style.css
```

**3. Cek Status & Staging**

```bash
git status
git add .
```

**4. Commit**

```bash
git commit -m "feat: Inisialisasi proyek dengan file index dan css"
```

**5. Buat Branch Baru**

```bash
git checkout -b fitur-kontak
```

**6. Commit di Branch**

```bash
git add .
git commit -m "feat: Menambahkan halaman kontak"
```

**7. Gabungkan Branch ke Main**

```bash
git checkout main
git merge fitur-kontak
```

---

## 🌐 Ketiga integrasi dengan GitHub

**1. Buat Repository di GitHub**

* Masuk ke GitHub
* Klik **+ → New repository**
* Beri nama (misal: `proyek-web-pertama`)
* Jangan centang *Add a README file*
* Klik **Create repository**

**2. Hubungkan Repo Lokal ke GitHub**

```bash
git remote add origin https://github.com/NamaUserKamu/proyek-web-pertama.git
git branch -M main
git push -u origin main
```

---

## 👥 Keempat Workflow Kerja Kelompok (Feature Branch Workflow)

**1. Clone Repository (sekali di awal)**

```bash
git clone https://github.com/NamaUserKamu/proyek-web-pertama.git
```

**2. Selalu Mulai dari Main Terbaru**

```bash
git checkout main
git pull origin main
```

**3. Buat Branch Baru untuk Setiap Fitur**

```bash
git checkout -b nama-fitur-baru
```

**4. Kerjakan, Add, dan Commit di Branch**

```bash
git add .
git commit -m "pesan commit yang jelas"
```

**5. Push Branch ke GitHub**

```bash
git push origin nama-fitur-baru
```

**6. Buat Pull Request (PR)**

* Buka repo di GitHub
* Klik **Compare & pull request**
* Isi judul, deskripsi, tetapkan reviewer
* Klik **Create pull request**

**7. Review & Merge**

* Reviewer meninjau perubahan
* Setelah disetujui, merge PR ke `main`

**8. Sinkronisasi Ulang**

```bash
git checkout main
git pull origin main
```

---
