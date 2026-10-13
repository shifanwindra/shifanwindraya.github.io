# Dokumentasi Proyek — Infrastruktur Jaringan PT Teknolink (Jarkom 2)

**Mata Kuliah:** Jaringan Komputer 2  
**Nama Proyek:** Proposal Pengadaan dan Konfigurasi Infrastruktur Jaringan PT Teknolink  
**Kelompok:** 1  
**Anggota:**
1. Wadu, Luis Henry (24/543995/SV/25305)
2. **Shifan Windraya Prassasti** (24/541727/SV/24944)
3. Ahmad Wafiy Rosyid Alhaq (24/545723/SV/25743)
4. Figlio Pasha Sunni (24/542144/SV/25007)
5. Nestor Rawikara Sotarduga Hutasoit (24/537963/SV/24456)
6. Muhammad Fayyadh Muslih (24/544493/SV/25431)

**Video Presentasi:** [https://youtu.be/z2AiLEVerl0](https://youtu.be/z2AiLEVerl0)  
**Short Proposal + RAB:** [Google Drive](https://drive.google.com/drive/folders/1mtaRWF-8Z4lAUJzrA-Vp1BPd1TgPMPWu)

---

## 1. Latar Belakang

PT Teknolink membutuhkan infrastruktur jaringan yang andal, skalabel, dan aman untuk mendukung operasional kantor perusahaan. Proyek ini merupakan simulasi nyata pengadaan dan konfigurasi infrastruktur jaringan enterprise menggunakan perangkat Cisco Packet Tracer.

---

## 2. Tujuan Proyek

- Merancang dan mengimplementasikan topologi jaringan kantor perusahaan yang lengkap.
- Mengonfigurasi VLAN untuk segmentasi jaringan antar departemen.
- Menerapkan Inter-VLAN routing agar antar departemen dapat saling berkomunikasi sesuai kebijakan.
- Membuat proposal pengadaan beserta Rincian Anggaran Biaya (RAB).

---

## 3. Teknologi & Tools

| Komponen | Teknologi |
|----------|-----------|
| Simulator | Cisco Packet Tracer (.pkt) |
| Protokol Routing | Static/Dynamic Routing |
| Segmentasi | VLAN (Virtual LAN) |
| Inter-VLAN | Router-on-a-Stick / Layer 3 Switch |
| Keamanan | Access Control List (ACL) |

---

## 4. Penyelesaian / Rancangan Sistem

### Desain Topologi & Simulasi

![Topologi Jaringan Enterprise Cisco](images/teknolink_topology_sim.png)
*Gambar 1: Perancangan Topologi Jaringan Enterprise, VLAN, dan Trunking pada Simulator Cisco*

- Topologi jaringan kantor dengan beberapa lantai/departemen.
- Setiap departemen ditempatkan dalam VLAN terpisah untuk keamanan dan manajemen trafik.

### Konfigurasi Utama
1. **VLAN Setup** — pembuatan VLAN per departemen (IT, Finance, HR, dll.)
2. **Trunk Link** — port trunk antar switch untuk membawa multiple VLAN.
3. **Inter-VLAN Routing** — konfigurasi subinterface router atau L3 switch agar antar VLAN bisa berkomunikasi.
4. **IP Addressing** — skema subnetting untuk masing-masing VLAN.
5. **ACL** — kebijakan akses untuk membatasi komunikasi antar departemen sesuai kebutuhan keamanan.

### Dokumen Pendukung
- **Short Proposal:** Dokumen singkat berisi analisis kebutuhan jaringan PT Teknolink.
- **RAB (Rincian Anggaran Biaya):** Estimasi biaya perangkat keras dan instalasi.
- **File Simulasi:** `mini_project_selesai_fix.pkt` — topologi lengkap siap diuji di Cisco Packet Tracer.

---

## 5. Hasil Proyek

- Topologi jaringan PT Teknolink berhasil dirancang dan dikonfigurasi di Cisco Packet Tracer.
- Semua VLAN berhasil dibuat dan trunk link dikonfigurasi dengan benar.
- Inter-VLAN routing berfungsi — antar departemen dapat saling berkomunikasi sesuai kebijakan.
- Proposal pengadaan dan RAB berhasil disusun sebagai dokumen formal pengajuan infrastruktur.
- Presentasi dilakukan secara video ([YouTube](https://youtu.be/z2AiLEVerl0)).

---

## 6. Kesimpulan

Mini Proyek Jarkom 2 ini berhasil mensimulasikan pengadaan dan konfigurasi infrastruktur jaringan kantor perusahaan skala enterprise. Implementasi VLAN, trunk, dan Inter-VLAN routing terbukti efektif untuk segmentasi dan manajemen jaringan multi-departemen. Proyek ini memberikan pengalaman nyata dalam perencanaan jaringan profesional termasuk aspek anggaran.
