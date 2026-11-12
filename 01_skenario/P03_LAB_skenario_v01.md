ID      |                     Kebutuhan                                 |
LAB-R01 | Mahasiswa dapat melihat ketersediaan peralatan                |
LAB-R02 | Petugas dapat mengelola data peralatan                        |
LAB-R03 | Mahasiswa dapat mengajukan peminjaman; sistem memeriksa       |
        | ketersediaan sebelum menyimpan pengajuan                      |
LAB-R04 | Mahasiswa dapat mencetak bukti pada konfirmasi pengajuan      |
        | jika memilihnya                                               |
LAB-R05 | Petugas dapat menetapkan persetujuan atau penolakan pengajuan |
LAB-R06 | Kepala laboratorium dapat melihat laporan peminjaman          | 

Aktor                   Tujuan terhadap sistem 
Mahasiswa               Melihat ketersediaan, mengajukan peminjaman, dan mencetak bukti 
Petugas laboratorium    Mengelola peralatan dan memproses keputusan 
Kepala laboratorium     Melihat laporan peminjaman

ID          Nama use case                    Peran dalam model
LAB-UC01    Lihat ketersediaan peralatan     Fungsi utama mahasiswa 
LAB-UC02    Kelola data peralatan            Fungsi utama petugas 
LAB-UC03    Ajukan peminjaman                Fungsi utama mahasiswa 
LAB-UC04    Periksa ketersediaan             Perilaku yang disertakan UC03 
LAB-UC05    Cetak bukti pengajuan            Tambahan bersyarat pada UC03 
LAB-UC06    Proses keputusan peminjaman      Fungsi utama petugas 
LAB-UC07    Lihat laporan peminjaman         Fungsi utama kepala laboratorium

LAB-UC03 «include» LAB-UC04 
Alasan: pemeriksaan menjadi bagian validasi pengajuan. 
LAB-UC05 «extend» LAB-UC03 
Extension point: Bukti pengajuan tersedia. 
Kondisi: [mahasiswa memilih cetak]. 
Alasan: pengajuan tetap berhasil tanpa pencetakan. 

