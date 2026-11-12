Elemen                  LAB-UC03 - Ajukan KRS 
Tujuan                  Mengirimkan isian KRS untuk diproses oleh Dosen Wali
Aktor utama             Mahasiswa 
Sumber kebutuhan        SIA-R03, SIA-R04 dan SIA-R05
Pemicu                  Mahasiswa menekan tombol simpan/kirim pada halaman formulir KRS
Prasyarat               Mahasiswa telah terautentikasi dan dalam masa pengisian KRS
Pascakondisi berhasil   KRS tersimpan berstatus "Menunggu Persetujuan Dosen Wali" 
Pascakondisi gagal      Pengajuan KRS tidak tersimpan dalam sistem
Include                 SIA-R04 Validasi KRS 
Extension point         Bukti KRS tersedia pada langkah 5 
Extend                  SIA-R05 Butuh bukti pengajuan KRS [mahasiswa memilih unduh bukti] 

Langkah     Tindakan mahasiswa                                   Respons sistem 
1           Membuka menu pengisian KRS                           Menampilkan daftar mata kuliah yang ditawarkan 
2           Memilih daftar mata kuliah yang akan diambil         Menampilkan total SKS yang dipilih 
3           Mengirim pengajuan KRS                               Menjalankan validasi isian KRS 
4           —                                                    Menjalankan SIA-R04
5           —                                                    Jika validasi berhasil, menyimpan KRS dengan status "Menunggu Persetujuan" dan mencapai extension point "Bukti KRS Tersedia"
6           Melihat halaman konfirmasi pengajuan                 Menampilkan pesan sukses dan ringkasan KRS
7           Mengakhiri alur pengajuan                            Menutup halaman pengajuan

Validasi KRS Gagal:
1. Sistem menampilkan rincian pesan kesalahan.
2. Pengajuan tidak tersimpan.
3. Mahasiswa kembali ke Langkah 2 alur utama untuk memperbaiki pilihan matakuliah.
Mahasiswa mengunduh bukti pengajuan:
1. Mahasiswa memilih tombol unduh bukti pada langkah 6.
2. Sistem me-trigger SIA-UC05.
3. Kembali ke alur utama langkah 7.

Elemen                  LAB-UC03 - Validasi KRS
Tujuan                  Memastikan mata kuliah yang dipilih memenuhi aturan akademik
Aktor utama             System
Sumber kebutuhan        SIA-R04
Pemicu                  Di-invoke oleh use case SIA-R03 pada langkah 4
Prasyarat               Data mata kuliah pilihan diterima dari SIA-R03
Pascakondisi berhasil   Validasi terkonfirmasi sukses tanpa pelanggaran aturan akademik
Pascakondisi gagal      Validasi terdeteksi gagal, sistem menerbitkan data error

Langkah     Tindakan aktor         Respons sistem 
1           System                 Memeriksa kelengkapan batas maksimal SKS mahasiswa         
2           System                 Memeriksa prasyarat mata kuliah yang di ambil
3           System                 Memeriksa benturan jadwal antar mata kuliah pilihan
4           System                 Mengembalikan status "Validasi Berhasil" ke SIA-R03

Elemen                  SIA-R05 - Unduh bukti pengajuan KRS
Tujuan                  Mengunduh salinan berkas bukti pengajuan KRS dalam format PDF
Aktor Utama             Mahasiswa
Sumber Kebutuhan        SIA-R05
Pemicu                  Mahasiswa menekan opsi "Unduh Bukti" pada halaman konfirmasi
Prasyarat               Pengajuan KRS telah berhasil tersimpan
Pascakondisi Berhasil   Berkas bukti pengajuan KRS terunduh di perangkat mahasiswa
Pascakondisi Gagal      Berkas gagal diunduh; tidak mempengaruhi status KRS tersimpan

Langkah     Tindakan mahasiswa                          Respons sistem 
1           Memilih tombol unduh bukti pengajuan        Menyiapkan dokumen bukti pengajuan KRS
2           -                                           Menerbitkan dan mengunduh berkas bukti ke perangkat pengguna

Elemen                  SIA-R06 - Proses keputusan KRS
Tujuan                  Menetapkan status persetujuan atau penolakan KRS mahasiswa perwalian
Aktor Utama             Dosen Wali
Sumber Kebutuhan        SIA-R06
Pemicu                  Dosen wali memilih daftar pengajuan KRS mahasiswa bimbingan
Prasyarat               Terdapat pengajuan KRS mahasiswa berstatus "Menunggu Persetujuan"
Pascakondisi Berhasil   Status KRS berubah menjadi "Disetujui" atau "Ditolak" beserta catatan
Pascakondisi Gagal      Status KRS tidak berubah

Langkah     Tindakan dosen wali                                          Respons sistem 
1           Membuka daftar pengajuan KRS perwalian                       Menampilkan daftar mahasiswa yang mengajukan KRS
2           Memilih salah satu mahasiswa                                 Menampilkan rincian daftar mata kuliah pengajuan
3           Memilih aksi "Setujui" atau "Tolak" dan mengisikan catatan   Menyimpan keputusan dan catatan persetujuan
4           -                                                            Mengubah status pengajuan KRS dan mengirim notifikasi ke mahasiswa