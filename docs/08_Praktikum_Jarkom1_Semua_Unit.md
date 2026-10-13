# Dokumentasi Praktikum — Jaringan Komputer 1 (PJK1) — MikroTik

**Mata Kuliah:** Jaringan Komputer 1  
**Penyusun:** Shifan Windraya Prassasti (24/541727/SV/24944) — Kelas B2  
**Dosen Pengampu:** Alif Subardono, S.T., M.Eng.  
**Asisten:** Dzaki Satrio Hakim, Naufal Sulaiman Arindrajs Putra  
**Program Studi:** D-IV Teknologi Rekayasa Internet — Sekolah Vokasi UGM, 2025  

> **Platform Utama:** Router MikroTik RB962UiGS — dikonfigurasi via **WinBox**

---

## Ringkasan Per Unit

---

### Unit 2 — Pengenalan MikroTik

**Tujuan:**
1. Memahami perintah konfigurasi CLI dan GUI pada router MikroTik.
2. Memahami fitur-fitur pada MikroTik.

**Penyelesaian:**
- Koneksi awal ke router menggunakan WinBox melalui MAC address.
- Konfigurasi identitas router: `/system identity set name=PCNetLabs`
- Pengaturan timezone dan waktu: `/system clock set time-zone-name=Asia/Jakarta`
- Eksplorasi fitur GUI WinBox: IP Address, Routes, DNS, Firewall.

**Hasil:**
Mahasiswa berhasil terhubung dan mengonfigurasi router MikroTik pertama kali, memahami antarmuka WinBox dan perintah CLI dasar RouterOS.

---

### Unit 3 — IP Address & Routing Dasar

**Tujuan:**
Memahami dan mengonfigurasi IP addressing serta routing statis pada MikroTik.

**Penyelesaian:**
Konfigurasi IP address pada interface ether1 (koneksi ke ISP) dan ether2 (koneksi ke PC/LAN). Penambahan default route dan NAT (masquerade) agar PC dapat mengakses internet.

**Hasil:**
Mahasiswa mampu mengonfigurasi IP address statis/dinamis dan routing dasar sehingga jaringan lokal dapat terhubung ke internet melalui MikroTik.

---

### Unit 4 — DHCP Server & DNS

**Tujuan:**
Memahami konfigurasi DHCP Server dan DNS pada MikroTik untuk distribusi IP otomatis.

**Penyelesaian:**
Konfigurasi DHCP Server pada interface LAN MikroTik sehingga perangkat klien mendapatkan IP secara otomatis. Konfigurasi DNS server untuk resolusi nama domain.

**Hasil:**
Jaringan berhasil mendistribusikan IP secara otomatis ke klien melalui DHCP, dan resolusi DNS berfungsi dengan baik.

---

### Unit 5 — Firewall & NAT

**Tujuan:**
Memahami konsep dan konfigurasi Firewall serta Network Address Translation (NAT) pada MikroTik.

**Penyelesaian:**
Konfigurasi NAT masquerade pada `IP > Firewall > NAT` dengan parameter:
- Chain: `srcnat`
- Out-interface: `ether1` (ke ISP)
- Action: `masquerade`

Penambahan aturan firewall filter untuk mengontrol trafik yang masuk/keluar/diteruskan.

**Hasil:**
IP private LAN berhasil dikenali di jaringan publik melalui NAT masquerade. Aturan firewall berhasil membatasi akses sesuai kebijakan keamanan.

---

### Unit 6 — Bandwidth Management / Queue

**Tujuan:**
Memahami manajemen bandwidth menggunakan Queue pada MikroTik.

**Penyelesaian:**
- **Lab 1 (Simple Queue / Source):** Konfigurasi limit bandwidth pada perangkat end device (misal: `192.168.7.2`) dengan limit upload 1 Mbps dan download 2 Mbps.
- **Lab 2 (Queue / Destination):** Konfigurasi limit download laptop maksimal 1 Mbps, sedangkan koneksi ke router dapat menggunakan bandwidth hingga 10 Mbps.
- Verifikasi hasil menggunakan speedtest.

**Hasil:**
Bandwidth berhasil dibatasi sesuai konfigurasi. Hasil speedtest membuktikan limit download dan upload berfungsi sesuai parameter yang diset.

---

![Konfigurasi DHCP Server](images/jarkom1_dhcp_server.png)
*Gambar: Konfigurasi DHCP Server pada MikroTik RouterOS*

### Unit 7 — Routing Lanjutan (Static & Dynamic)

**Tujuan:**
Memahami routing statis dan protokol routing dinamis pada MikroTik.

**Penyelesaian:**
Konfigurasi routing statis manual untuk jaringan multi-hop. Pengenalan routing dinamis (RIP/OSPF) sebagai alternatif manajemen rute otomatis pada jaringan kompleks.

**Hasil:**
Mahasiswa mampu mengonfigurasi routing statis untuk konektivitas antar jaringan yang berbeda.

---

### Unit 9 — Routing (OSPF/RIP)

**Tujuan:**
Memahami protokol routing dinamis OSPF dan RIP pada jaringan MikroTik.

**Penyelesaian:**
Konfigurasi protokol routing dinamis pada beberapa router yang saling terhubung. Router saling bertukar informasi routing tabel secara otomatis tanpa konfigurasi rute manual.

**Hasil:**
Routing dinamis berhasil dikonfigurasi — router dapat menentukan rute terbaik secara otomatis dan beradaptasi terhadap perubahan topologi jaringan.

---

![Konfigurasi Routing OSPF MikroTik](images/jarkom1_ospf_routing.png)
*Gambar: Routing Dinamis OSPF pada Jarkom 1*

### Unit 10 — Tunneling (EoIP)

**Tujuan:**
1. Memahami pengertian Tunneling.
2. Memahami konfigurasi Tunneling pada router MikroTik.

**Penyelesaian:**
- **EoIP (Ethernet over Internet Protocol):** Membuat terowongan virtual yang menghubungkan dua jaringan berbeda melalui internet.
- Topologi: Router saya (IP Publik `10.33.108.7/24`) ↔ Router lawan (`10.33.108.8/24`).
- Konfigurasi: tambah IP interface, default route via `10.33.108.254`, konfigurasi NAT, lalu buat EoIP tunnel ke router tujuan.
- Melalui EoIP, dua jaringan private dapat terhubung seolah berada dalam satu jaringan lokal.

**Hasil:**
Tunneling EoIP berhasil dikonfigurasi. Dua jaringan yang secara fisik terpisah berhasil dihubungkan melalui internet seolah-olah berada dalam satu jaringan LAN.

---

### Unit 11 — Wireless dan Hotspot

**Tujuan:**
1. Memahami pengertian Wireless dan Hotspot pada Router.
2. Memahami konfigurasi Wireless dan Hotspot pada MikroTik.

**Penyelesaian:**
- Konfigurasi koneksi router ke internet: IP ether1 `10.33.108.19`, ether2 `192.168.19.1`, default gateway `10.33.108.254`.
- NAT masquerade untuk akses internet.
- DNS: server `10.13.10.13`, secondary `10.18.10.18`.
- **Hotspot:** Konfigurasi melalui `IP > Hotspot` — membuat portal login untuk pengguna WiFi.

**Hasil:**
Hotspot MikroTik berhasil dikonfigurasi dengan portal login. Pengguna harus autentikasi sebelum dapat mengakses internet melalui jaringan wireless.

---

### Unit 12 — VLAN dan Inter-VLAN

**Tujuan:**
1. Memahami VLAN dan Inter-VLAN pada jaringan.
2. Memahami konfigurasi VLAN dan Inter-VLAN pada MikroTik.

**Penyelesaian:**
- **Lab 1: VLAN**
  - Konfigurasi R5-1: Buat VLAN 10 dan VLAN 20 di `IP > Interfaces > VLAN`, lewat interface `ether1`.
  - Gateway VLAN 10: `192.168.10.1`, VLAN 20: `192.168.20.1`.
  - Bridge port: ether2 → VLAN10, ether3 → VLAN20.
  - Konfigurasi R6-1 serupa untuk sisi lain.
- **Inter-VLAN:** Routing antar VLAN agar perangkat di VLAN berbeda dapat berkomunikasi.

**Hasil:**
VLAN berhasil dibuat dan dikonfigurasi. Inter-VLAN routing berfungsi — perangkat di VLAN 10 dan VLAN 20 dapat berkomunikasi sesuai aturan yang ditetapkan.

---

### Unit 13 — Wireless Lanjutan (AP & Station)

**Tujuan:**
1. Memahami pengertian Wireless pada jaringan.
2. Memahami konfigurasi Wireless pada MikroTik.

**Penyelesaian:**
- **Lab 38 (Wireless AP & Station):**
  - **Router AP:** Aktifkan port wireless, konfigurasi `wlan1` sebagai `ap bridge`. Set band `2GHz-B/G/N`, channel width `20MHz`, pilih frekuensi dengan interferensi minimal (cek via "Freq. Usage"). Tulis SSID.
  - **Router Station:** Konfigurasi `wlan1` sebagai `station`, scan dan connect ke SSID dari AP.

**Hasil:**
Koneksi wireless antar router berhasil terbentuk dengan konfigurasi AP (Access Point) dan Station. Jaringan wireless berfungsi dengan baik.

---

### Unit 14 — Fail Over

**Tujuan:**
1. Memahami pengertian Fail Over pada jaringan.
2. Memahami konfigurasi Fail Over pada MikroTik.

**Penyelesaian:**
- **Studi Kasus 1 (LAB 1):**
  - Router terhubung ke **dua sumber internet**: kabel (cloud1/ether1) dan wireless (WiFi UGM Hotspot).
  - Internet utama: ether1 (`10.33.108.8/24`), ether2 ke PC (`192.168.8.1/24`), default route ke `10.33.108.254`.
  - Internet cadangan: wlan1 terhubung ke `wifiugmhotspot`.
  - Konfigurasi Fail Over: jika internet utama (ether1) terputus, traffic otomatis berpindah ke internet cadangan (wireless).

**Hasil:**
Fail Over berhasil dikonfigurasi. Ketika koneksi internet utama terputus, koneksi secara otomatis berpindah ke internet cadangan tanpa intervensi manual.

---

## Ringkasan Topik PJK1

| Unit | Topik | Teknologi/Protokol |
|------|-------|-------------------|
| 2 | Pengenalan MikroTik | WinBox, RouterOS CLI |
| 3 | IP Address & Routing Dasar | Static Route, NAT |
| 4 | DHCP & DNS | DHCP Server, DNS |
| 5 | Firewall & NAT | Firewall Filter, Masquerade |
| 6 | Bandwidth Management | Simple Queue |
| 7 | Routing Lanjutan | Static Routing |
| 9 | Routing Dinamis | OSPF, RIP |
| 10 | Tunneling | EoIP (Ethernet over IP) |
| 11 | Wireless & Hotspot | WiFi, Hotspot Portal |
| 12 | VLAN & Inter-VLAN | VLAN, Bridge, Routing |
| 13 | Wireless AP & Station | AP Bridge, Station Mode |
| 14 | Fail Over | Dual ISP, Route Monitoring |
