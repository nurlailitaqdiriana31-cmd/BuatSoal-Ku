# SMART AI QUESTION GENERATOR

Aplikasi web berbahasa Indonesia untuk menyusun, mengulas, menyimpan, dan membagikan soal berdasarkan materi guru.

## Menjalankan aplikasi

1. Pasang Node.js 18 atau lebih baru.
2. Buka PowerShell di folder `outputs`.
3. Jalankan `node server.js`.
4. Buka `http://localhost:4173`.
5. Buka **Pengaturan**, masukkan endpoint model yang kompatibel dengan format OpenAI, nama model, dan API key. Server menyimpan pengaturan ini di `work/smart-ai-settings.json`, di luar folder publik.

Server tidak membutuhkan paket Node tambahan. Data identitas, materi, hasil soal, dan bank soal tersimpan di penyimpanan browser perangkat. Asesmen yang diterbitkan dan hasil siswa juga disimpan oleh server lokal di `work/smart-ai-data.json` agar tautan dapat dibuka lewat server yang sama.

## Fitur yang tersedia

- Dashboard ringkas dan navigasi responsif.
- Form identitas asesmen dengan penyesuaian jenjang, fase, dan kelas.
- Unggah beberapa materi, drag-and-drop, ekstraksi TXT, DOCX, PPTX, dan PDF teks dasar.
- Generate soal lewat API AI dengan instruksi untuk menjadikan materi unggahan sebagai sumber, serta mempertahankan jawaban, pembahasan, indikator, tingkat kesulitan, dan referensi sumber.
- Editor soal, tambah/hapus/ganti soal, pengacakan, kisi-kisi, kunci jawaban, bank soal, cetak, dan ekspor data JSON atau Word.
- Tautan asesmen siswa, pengisian identitas, pemeriksaan jawaban objektif, dan ringkasan hasil.
- Analisis hasil kelas, ekspor CSV, serta cadangan dan pemulihan data JSON.

## Catatan format dan pemasangan

- PDF hasil scan mungkin tidak berisi teks yang dapat diekstrak. OCR belum disertakan.
- Berkas Word/PowerPoint lama (`.doc` / `.ppt`) diterima sebagai unggahan, tetapi pembacaan isinya memerlukan konversi ke `.docx` / `.pptx` atau `.txt`.
- Ekstraksi PDF teks memakai pembacaan operator teks sederhana; tata letak kompleks dan sebagian PDF terkompresi mungkin memerlukan konversi ke TXT.
- Penyimpanan aplikasi lokal menggunakan browser dan berkas JSON, tanpa autentikasi guru. Untuk pemakaian publik, tempatkan di hosting HTTPS dan tambahkan autentikasi, database, penyimpanan berkas privat, kontrol akses, serta kebijakan retensi data siswa.
- Tautan yang dibuat menggunakan server lokal hanya dapat diakses oleh perangkat yang dapat menjangkau server tersebut. Untuk siswa di luar jaringan lokal, aplikasi perlu dipasang pada hosting yang dapat diakses siswa.
- Ekspor PDF tersedia melalui **Cetak / PDF** lalu pilih “Save as PDF” pada dialog cetak browser. Ekspor Word memakai format `.doc` berbasis HTML yang dapat dibuka Word.

