ID          Nama use case               Aktor               Catatan pemetaan
SIA-UC07    Lihat kalender akademik     Civitas akademik    Ditulis satu kali atas nama Civitas akademika; berlaku untuk mahasiswa dan dosen
SIA-UC08    Input nilai mata kuliah     Dosen               Prasyarat: dosen pengampu mata kuliah; alternatif: nilai di luar rentang yang sah ditolak; direalisasikan SIA-CO01
SIA-UC09    Lihat KHS                   Mahasiswa           Hanya nilai yang sudah dipublikasikan yang ditampilkan; direalisasikan SIA-CO02
SIA-UC10    Kelola data mahasiswa       Admin akademik      Skenario umum pengelolaan; langkah bersama yang dirujuk UC11, UC12, dan UC13
SIA-UC11    Tambah data mahasiswa       Admin akademik      Khusus dari UC10; perilaku pembeda: data mahasiswa baru tersimpan
SIA-UC12    Ubah data mahasiswa         Admin akademik      Khusus dari UC10; perilaku pembeda: data mahasiswa berubah
SIA-UC13    Hapus data mahasiswa        Admin akademik      Khusus dari UC10; perilaku pembeda: data mahasiswa terhapus; syarat: tidak ada data akademik aktif