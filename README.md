# 🚘 Transport & Vehicle Management System (Java Swing MVC)

[![Java](https://img.shields.io/badge/Java-SE-ED8B00?style=for-the-badge&logo=java&logoColor=white)](https://www.oracle.com/java/)
[![IDE](https://img.shields.io/badge/NetBeans-IDE-1B6AC6?style=for-the-badge&logo=apache-netbeans-ide&logoColor=white)](https://netbeans.apache.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)
[![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)](#)

> Sistem manajemen operasional armada kendaraan dan pendataan sopir/pengemudi berbasis **Java Desktop (Swing)** menggunakan arsitektur pemisahan kode **Model-View-Controller (MVC)**.

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Key Features](#-key-features)
- [Tech Stack](#-tech-stack)
- [Class & Architecture Overview](#-class--architecture-overview)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
  - [Prerequisites](#prerequisites)
  - [Compilation & Execution](#compilation--execution)
- [Screenshots / Demo](#-screenshots--demo)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [Author & License](#-author--license)

---

## 📖 Overview

**TugasMVC** adalah aplikasi manajemen transportasi berbasis Java GUI yang dirancang untuk mengelola data master pengguna, sopir, dan armada kendaraan secara terpusat. Aplikasi ini dihubungkan dengan basis data melalui konektor JDBC.

Proyek ini dibangun secara penuh dengan menerapkan pola desain **Model-View-Controller (MVC)** untuk memisahkan antara logika bisnis (*Model*), antarmuka grafis (*View*), dan jembatan pemrosesan data (*Controller*).

---

## ✨ Key Features

- **Sistem Otentikasi (`LoginView` & `LoginController`)** — Verifikasi identitas pengguna sebelum mengakses menu utama.
- **Navigasi Menu Utama (`MenuView`)** — Dasbor pusat untuk mengakses antarmuka manajemen data.
- **Manajemen Armada (`KendaraanView` & `KendaraanController`)** — Pengelolaan data master armada kendaraan[cite: 5].
- **Manajemen Pengemudi (`SopirView` & `SupirController`)** — Pengelolaan data master sopir/pengemudi operasional[cite: 5].
- **Koneksi Database Terpusat (`Koneksi`)** — Modul pembuka dan penyedia jalur *connection* ke database relational[cite: 5].

---

## 🧰 Tech Stack

| Category | Technology / Library |
| :--- | :--- |
| **Language** | Java (JDK 8 / 11 / 17+)[cite: 5] |
| **Architecture** | Model-View-Controller (MVC) Pattern[cite: 5] |
| **GUI Framework** | Java Swing & AWT[cite: 5] |
| **Database Connector** | JDBC Driver[cite: 5] |
| **Build Tool / IDE** | Apache NetBeans IDE / Ant Build System[cite: 5] |

---

## 🧩 Class & Architecture Overview

Pembagian peran sesuai komponen MVC pada proyek[cite: 5]:

| Layer / Package | Class | Deskripsi / Peran |
| :--- | :--- | :--- |
| **`connection`**[cite: 5] | `Koneksi.java`[cite: 5] | Menangani establishing & manajemen koneksi JDBC[cite: 5]. |
| **`model`**[cite: 5] | `User.java`[cite: 5]<br>`Sopir.java`[cite: 5]<br>`Kendaraan.java`[cite: 5] | Entity/POJO yang merepresentasikan tabel database[cite: 5]. |
| **`view`**[cite: 5] | `LoginView.java`[cite: 5]<br>`MenuView.java`[cite: 5]<br>`SopirView.java`[cite: 5]<br>`KendaraanView.java`[cite: 5] | Antarmuka pengguna (GUI) berbantu komponen Swing[cite: 5]. |
| **`controller`**[cite: 5] | `LoginController.java`[cite: 5]<br>`SupirController.java`[cite: 5]<br>`KendaraanController.java`[cite: 5] | Menangani logika bisnis, aksi tombol, & pemrosesan database[cite: 5]. |
| **`main`**[cite: 5] | `Main.java`[cite: 5] | Entry point / kelas utama tempat program diawali[cite: 5]. |

---

## 📁 Project Structure

```text
TugasMVC/
├── build.xml                       # Script kompilasi Ant Build[cite: 5]
├── manifest.mf                     # File manifest JAR[cite: 5]
├── nbproject/                      # Konfigurasi proyek NetBeans[cite: 5]
│   ├── build-impl.xml[cite: 5]
│   ├── genfiles.properties[cite: 5]
│   ├── project.properties[cite: 5]
│   └── project.xml[cite: 5]
└── src/
    ├── connection/                 # Modul koneksi database[cite: 5]
    │   └── Koneksi.java[cite: 5]
    ├── controller/                 # Logika bisnis & pemroses aksi[cite: 5]
    │   ├── KendaraanController.java[cite: 5]
    │   ├── LoginController.java[cite: 5]
    │   └── SupirController.java[cite: 5]
    ├── main/                       # Kelas peluncur (Main Runner)[cite: 5]
    │   └── Main.java[cite: 5]
    ├── model/                      # Entitas data & POJO[cite: 5]
    │   ├── Kendaraan.java[cite: 5]
    │   ├── Sopir.java[cite: 5]
    │   └── User.java[cite: 5]
    └── view/                       # Antarmuka grafis Swing[cite: 5]
        ├── KendaraanView.java[cite: 5]
        ├── LoginView.java[cite: 5]
        ├── MenuView.java[cite: 5]
        └── SopirView.java[cite: 5]
