# Deteksi Serangan Siber dengan Honeypot Cowrie (Docker Based)

Proyek ini mendokumentasikan simulasi keamanan jaringan yang menggunakan **Honeypot Cowrie** untuk mendeteksi berbagai jenis serangan pada port SSH. Seluruh infrastruktur dijalankan di atas **Docker** untuk memastikan isolasi sistem utama dari serangan.
## 👥 Anggota Kelompok
- **UMMUL MU'MININ** - 105841117323
- **RIRIN YULANDARI** - 105841117923

---

## 🛠️ Infrastruktur & Tools
* **Target:** Kali Linux (Honeypot Cowrie) - IP: `10.206.206.124`
* **Attacker:** Kali Linux - IP: `10.206.206.39`
* **Platform:** Docker & Docker-Compose
* **Attack Tools:** Nmap (Scanning), Hydra (Bruteforce), LOIC (DDoS)

## 🚀 Langkah Instalasi
1. Update dan Install Docker:
   `sudo apt update && sudo apt install docker.io docker-compose -y`
2. Jalankan Honeypot Cowrie:
   `sudo docker run -p 22:2222 cowrie/cowrie`

## 📊 Skenario Pengujian & Hasil
Berdasarkan hasil pengujian, sistem berhasil mendeteksi 100% serangan yang dilancarkan:

| No | Pola Serangan | Tool | Status Deteksi | Bukti Log |
|---|---|---|---|---|
| 1 | Port Scanning | Nmap | **Terdeteksi** | `Bad protocol version identification` |
| 2 | Bruteforce | Hydra | **Terdeteksi** | Login attempts for user `root` recorded |
| 3 | DDoS | LOIC | **Terdeteksi** | High volume of `New connection` logs |

## 🛡️ Kesimpulan
Honeypot Cowrie terbukti efektif sebagai sistem pertahanan aktif yang mampu mengelabui penyerang dengan layanan SSH palsu (OpenSSH 9.2p1) dan merekam jejak forensik secara mendetail.
