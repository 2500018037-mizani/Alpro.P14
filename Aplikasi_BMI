#include <iostream>
#include <iomanip>
#include <fstream>
#include <string>
#include <limits>
#include <cctype>
#include <algorithm>

using namespace std;

class AplikasiBMI {
private:
    static const int MAKS_DATA = 100;

    int id[MAKS_DATA];
    string nama[MAKS_DATA];
    string jenisKelamin[MAKS_DATA];
    int umur[MAKS_DATA]; 
    float berat[MAKS_DATA];
    float tinggi[MAKS_DATA];
    float bmi[MAKS_DATA];
    string kategori[MAKS_DATA];
    string tanggalCatat[MAKS_DATA];
    string aktivitas[MAKS_DATA];
    string tujuan[MAKS_DATA];
    string catatan[MAKS_DATA];
    int jumlahData;
    int nomorIdTerakhir;


    // Fungsi constructor untuk menyiapkan nilai awal aplikasi BMI.
public:
    AplikasiBMI() {
        jumlahData = 0;
        nomorIdTerakhir = 1000;
    }

    // Fungsi utama untuk menjalankan seluruh menu aplikasi BMI.
    void jalankanAplikasi() {
        int pilihan;
        do {
            tampilkanHeaderAplikasi();
            tampilkanMenuUtama();
            pilihan = inputAngka("Pilih menu: ", 1, 25);
            prosesMenuUtama(pilihan);
        } while (pilihan != 25);
    }

private:
    // Fungsi untuk menampilkan judul utama aplikasi.
    void tampilkanHeaderAplikasi() {
        cout << "\n";
        cetakGarisPanjang();
        cout << "              APLIKASI PENCATATAN BMI SEDERHANA\n";
        cetakGarisPanjang();
    }

    // Fungsi untuk menampilkan garis panjang sebagai pembatas tampilan.
    void cetakGarisPanjang() {
        cout << "============================================================\n";
    }

    // Fungsi untuk menampilkan garis pendek sebagai pembatas bagian kecil.
    void cetakGarisPendek() {
        cout << "------------------------------\n";
    }

    // Fungsi untuk menampilkan menu utama aplikasi.
    void tampilkanMenuUtama() {
        cout << "1.  Input data baru\n";
        cout << "2.  Tambah satu data\n";
        cout << "3.  Tampilkan semua data\n";
        cout << "4.  Tampilkan detail berdasarkan ID\n";
        cout << "5.  Edit data berdasarkan ID\n";
        cout << "6.  Hapus data berdasarkan ID\n";
        cout << "7.  Cari data berdasarkan nama\n";
        cout << "8.  Cari data berdasarkan kategori BMI\n";
        cout << "9.  Sorting BMI kecil ke besar\n";
        cout << "10. Sorting BMI besar ke kecil\n";
        cout << "11. Sorting nama A-Z\n";
        cout << "12. Sorting nama Z-A\n";
        cout << "13. Sorting berat badan kecil ke besar\n";
        cout << "14. Sorting tinggi badan kecil ke besar\n";
        cout << "15. Statistik data BMI\n";
        cout << "16. Rekap jumlah kategori\n";
        cout << "17. Simpan data ke file\n";
        cout << "18. Load data dari file\n";
        cout << "19. Export laporan sederhana\n";
        cout << "20. Tampilkan tips sehat\n";
        cout << "21. Tampilkan motivasi sehat\n";
        cout << "22. Tampilkan contoh menu makan sehat\n";
        cout << "23. Tampilkan panduan kategori BMI\n";
        cout << "24. Reset semua data\n";
        cout << "25. Keluar\n";
    }

    // Fungsi untuk mengatur aksi berdasarkan pilihan menu utama.
    void prosesMenuUtama(int pilihan) {
        switch (pilihan) {
            case 1:
                inputBanyakData();
                break;
            case 2:
                tambahSatuData();
                break;
            case 3:
                tampilkanSemuaData();
                break;
            case 4:
                tampilkanDetailBerdasarkanId();
                break;
            case 5:
                editDataBerdasarkanId();
                break;
            case 6:
                hapusDataBerdasarkanId();
                break;
            case 7:
                cariDataBerdasarkanNama();
                break;
            case 8:
                cariDataBerdasarkanKategori();
                break;
            case 9:
                sortingBmiKecilKeBesar();
                break;
            case 10:
                sortingBmiBesarKeKecil();
                break;
            case 11:
                sortingNamaAZ();
                break;
            case 12:
                sortingNamaZA();
                break;
            case 13:
                sortingBeratKecilKeBesar();
                break;
            case 14:
                sortingTinggiKecilKeBesar();
                break;
            case 15:
                tampilkanStatistikBMI();
                break;
            case 16:
                tampilkanRekapKategori();
                break;
            case 17:
                simpanDataKeFile();
                break;
            case 18:
                loadDataDariFile();
                break;
            case 19:
                exportLaporanSederhana();
                break;
            case 20:
                menuTipsSehat();
                break;
            case 21:
                menuMotivasiSehat();
                break;
            case 22:
                menuMakanSehat();
                break;
            case 23:
                tampilkanPanduanKategoriBMI();
                break;
            case 24:
                resetSemuaData();
                break;
            case 25:
                cout << "\nTerima kasih sudah menggunakan aplikasi BMI.\n";
                break;
            default:
                cout << "\nPilihan tidak tersedia.\n";
                break;
        }

        if (pilihan != 25) {
            tahanLayar();
        }
    }

    // Fungsi untuk membersihkan input jika user memasukkan tipe data yang salah.
    void bersihkanInput() {
        cin.clear();
        cin.ignore(numeric_limits<streamsize>::max(), '\n');
    }

    // Fungsi untuk menahan layar agar user sempat membaca hasil.
    void tahanLayar() {
        cout << "\nTekan ENTER untuk kembali ke menu...";
        cin.ignore(numeric_limits<streamsize>::max(), '\n');
        cin.get();
    }

    // Fungsi untuk meminta input string agar nama atau catatan dapat memakai spasi.
    string inputTeks(string pesan) {
        string teks;
        cout << pesan;
        getline(cin >> ws, teks);
        return teks;
    }

    // Fungsi untuk meminta input angka integer dengan batas minimum dan maksimum.
    int inputAngka(string pesan, int minimal, int maksimal) {
        int angka;
        while (true) {
            cout << pesan;
            if (cin >> angka) {
                if (angka >= minimal && angka <= maksimal) {
                    return angka;
                } else {
                    cout << "Input harus antara " << minimal << " sampai " << maksimal << ".\n";
                }
            } else {
                cout << "Input harus berupa angka.\n";
                bersihkanInput();
            }
        }
    }

    // Fungsi untuk meminta input angka pecahan dengan batas minimum dan maksimum.
    float inputFloat(string pesan, float minimal, float maksimal) {
        float angka;
        while (true) {
            cout << pesan;
            if (cin >> angka) {
                if (angka >= minimal && angka <= maksimal) {
                    return angka;
                } else {
                    cout << "Input harus antara " << minimal << " sampai " << maksimal << ".\n";
                }
            } else {
                cout << "Input harus berupa angka.\n";
                bersihkanInput();
            }
        }
    }

    // Fungsi untuk membuat ID otomatis agar setiap data mudah dicari.
    int buatIdBaru() {
        nomorIdTerakhir = nomorIdTerakhir + 1;
        return nomorIdTerakhir;
    }

    // Fungsi untuk mengecek apakah aplikasi sudah memiliki data.
    bool dataMasihKosong() {
        if (jumlahData == 0) {
            cout << "\nData masih kosong. Silakan input data terlebih dahulu.\n";
            return true;
        }
        return false;
    }

    // Fungsi untuk menghitung BMI dari berat dan tinggi badan.
    float hitungBMI(float beratBadan, float tinggiBadan) {
        if (tinggiBadan <= 0) {
            return 0;
        }
        return beratBadan / (tinggiBadan * tinggiBadan);
    }

    // Fungsi untuk menentukan kategori berdasarkan nilai BMI.
    string tentukanKategoriBMI(float nilaiBMI) {
        if (nilaiBMI < 18.5) {
            return "Kurus";
        } else if (nilaiBMI >= 18.5 && nilaiBMI <= 24.9) {
            return "Normal";
        } else if (nilaiBMI >= 25.0 && nilaiBMI <= 29.9) {
            return "Gemuk";
        } else {
            return "Obesitas";
        }
    }

    // Fungsi untuk membuat saran singkat berdasarkan kategori BMI.
    string buatSaranBerdasarkanKategori(string dataKategori) {
        if (dataKategori == "Kurus") {
            return "Perbanyak asupan bergizi dan latihan kekuatan secara bertahap.";
        } else if (dataKategori == "Normal") {
            return "Pertahankan pola makan seimbang dan aktivitas rutin.";
        } else if (dataKategori == "Gemuk") {
            return "Kurangi makanan tinggi gula dan mulai olahraga ringan.";
        } else {
            return "Atur pola makan dan konsultasi dengan tenaga kesehatan jika perlu.";
        }
    }

    // Fungsi untuk menghitung batas berat ideal minimum berdasarkan tinggi badan.
    float hitungBeratIdealMinimum(float tinggiBadan) {
        return 18.5f * tinggiBadan * tinggiBadan;
    }

    // Fungsi untuk menghitung batas berat ideal maksimum berdasarkan tinggi badan.
    float hitungBeratIdealMaksimum(float tinggiBadan) {
        return 24.9f * tinggiBadan * tinggiBadan;
    }

    // Fungsi untuk mengubah huruf menjadi kecil agar pencarian tidak sensitif huruf besar kecil.
    string ubahKeHurufKecil(string teks) {
        string hasil = teks;
        int panjang = hasil.length();
        for (int i = 0; i < panjang; i++) {
            hasil[i] = tolower(hasil[i]);
        }
        return hasil;
    }

    // Fungsi untuk mengecek apakah satu teks mengandung teks lain.
    bool teksMengandung(string sumber, string dicari) {
        string sumberKecil = ubahKeHurufKecil(sumber);
        string dicariKecil = ubahKeHurufKecil(dicari);
        if (sumberKecil.find(dicariKecil) != string::npos) {
            return true;
        }
        return false;
    }

    // Fungsi untuk mengisi satu data BMI pada index tertentu.
    void isiDataPadaIndex(int index) {
        id[index] = buatIdBaru();
        cout << "\nData ke-" << index + 1 << "\n";
        nama[index] = inputTeks("Masukkan nama: ");
        jenisKelamin[index] = inputJenisKelamin();
        umur[index] = inputAngka("Masukkan umur: ", 1, 120);
        berat[index] = inputFloat("Masukkan berat badan kg: ", 1, 300);
        tinggi[index] = inputFloat("Masukkan tinggi badan meter: ", 0.3f, 2.5f);
        tanggalCatat[index] = inputTeks("Masukkan tanggal catat contoh 06-07-2026: ");
        aktivitas[index] = inputTeks("Masukkan aktivitas harian: ");
        tujuan[index] = inputTeks("Masukkan tujuan kesehatan: ");
        catatan[index] = inputTeks("Masukkan catatan tambahan: ");
        hitungUlangDataPadaIndex(index);
    }

    // Fungsi untuk meminta input jenis kelamin dengan pilihan sederhana.
    string inputJenisKelamin() {
        int pilih;
        cout << "Jenis kelamin:\n";
        cout << "1. Laki-laki\n";
        cout << "2. Perempuan\n";
        pilih = inputAngka("Pilih jenis kelamin: ", 1, 2);
        if (pilih == 1) {
            return "Laki-laki";
        }
        return "Perempuan";
    }

    // Fungsi untuk menghitung ulang BMI dan kategori pada index tertentu.
    void hitungUlangDataPadaIndex(int index) {
        bmi[index] = hitungBMI(berat[index], tinggi[index]);
        kategori[index] = tentukanKategoriBMI(bmi[index]);
    }

    // Fungsi untuk input banyak data dari awal dan mengganti data lama.
    void inputBanyakData() {
        int banyak;
        banyak = inputAngka("\nMasukkan jumlah data yang ingin diinput: ", 1, MAKS_DATA);
        jumlahData = 0;
        nomorIdTerakhir = 1000;

        for (int i = 0; i < banyak; i++) {
            isiDataPadaIndex(i);
            jumlahData++;
        }

        cout << "\nInput data selesai. Total data: " << jumlahData << "\n";
    }

    // Fungsi untuk menambahkan satu data baru tanpa menghapus data lama.
    void tambahSatuData() {
        if (jumlahData >= MAKS_DATA) {
            cout << "\nData sudah penuh. Maksimal hanya " << MAKS_DATA << " data.\n";
            return;
        }

        isiDataPadaIndex(jumlahData);
        jumlahData++;

        cout << "\nData baru berhasil ditambahkan.\n";
    }

    // Fungsi untuk mencetak judul tabel data BMI.
    void cetakJudulTabel() {
        cetakGarisPanjang();
        cout << left
             << setw(6) << "ID"
             << setw(18) << "Nama"
             << setw(8) << "Umur"
             << setw(12) << "Berat"
             << setw(12) << "Tinggi"
             << setw(12) << "BMI"
             << setw(12) << "Kategori"
             << "\n";
        cetakGarisPanjang();
    }

    // Fungsi untuk mencetak satu baris data BMI dalam bentuk tabel.
    void cetakBarisData(int index) {
        cout << left
             << setw(6) << id[index]
             << setw(18) << potongTeks(nama[index], 16)
             << setw(8) << umur[index]
             << setw(12) << fixed << setprecision(1) << berat[index]
             << setw(12) << fixed << setprecision(2) << tinggi[index]
             << setw(12) << fixed << setprecision(2) << bmi[index]
             << setw(12) << kategori[index]
             << "\n";
    }

    // Fungsi untuk memotong teks panjang agar tampilan tabel tetap rapi.
    string potongTeks(string teks, int batas) {
        int panjang = teks.length();
        if (panjang <= batas) {
            return teks;
        }
        return teks.substr(0, batas - 3) + "...";
    }

    // Fungsi untuk menampilkan semua data BMI dalam bentuk tabel.
    void tampilkanSemuaData() {
        if (dataMasihKosong()) {
            return;
        }

        cout << "\n=== SEMUA DATA BMI ===\n";
        cetakJudulTabel();

        for (int i = 0; i < jumlahData; i++) {
            cetakBarisData(i);
        }

        cetakGarisPanjang();
        cout << "Total data: " << jumlahData << "\n";
    }

    // Fungsi untuk mencari index data berdasarkan ID.
    int cariIndexBerdasarkanId(int idDicari) {
        for (int i = 0; i < jumlahData; i++) {
            if (id[i] == idDicari) {
                return i;
            }
        }
        return -1;
    }

    // Fungsi untuk menampilkan detail data berdasarkan ID yang dimasukkan user.
    void tampilkanDetailBerdasarkanId() {
        if (dataMasihKosong()) {
            return;
        }

        int idCari = inputAngka("\nMasukkan ID yang ingin dilihat: ", 1, 999999);
        int index = cariIndexBerdasarkanId(idCari);

        if (index == -1) {
            cout << "\nData dengan ID tersebut tidak ditemukan.\n";
        } else {
            cetakDetailData(index);
        }
    }

    // Fungsi untuk mencetak detail lengkap satu data BMI.
    void cetakDetailData(int index) {
        cout << "\n=== DETAIL DATA BMI ===\n";
        cout << "ID              : " << id[index] << "\n";
        cout << "Nama            : " << nama[index] << "\n";
        cout << "Jenis Kelamin   : " << jenisKelamin[index] << "\n";
        cout << "Umur            : " << umur[index] << " tahun\n";
        cout << "Berat Badan     : " << fixed << setprecision(1) << berat[index] << " kg\n";
        cout << "Tinggi Badan    : " << fixed << setprecision(2) << tinggi[index] << " m\n";
        cout << "Nilai BMI       : " << fixed << setprecision(2) << bmi[index] << "\n";
        cout << "Kategori BMI    : " << kategori[index] << "\n";
        cout << "Tanggal Catat   : " << tanggalCatat[index] << "\n";
        cout << "Aktivitas       : " << aktivitas[index] << "\n";
        cout << "Tujuan          : " << tujuan[index] << "\n";
        cout << "Catatan         : " << catatan[index] << "\n";
        cout << "Berat ideal min : " << fixed << setprecision(1) << hitungBeratIdealMinimum(tinggi[index]) << " kg\n";
        cout << "Berat ideal maks: " << fixed << setprecision(1) << hitungBeratIdealMaksimum(tinggi[index]) << " kg\n";
        cout << "Saran           : " << buatSaranBerdasarkanKategori(kategori[index]) << "\n";
    }

    // Fungsi untuk mengedit data berdasarkan ID.
    void editDataBerdasarkanId() {
        if (dataMasihKosong()) {
            return;
        }

        int idCari = inputAngka("\nMasukkan ID yang ingin diedit: ", 1, 999999);
        int index = cariIndexBerdasarkanId(idCari);

        if (index == -1) {
            cout << "\nData dengan ID tersebut tidak ditemukan.\n";
            return;
        }

        menuEditData(index);
    }

    // Fungsi untuk menampilkan pilihan edit data.
    void menuEditData(int index) {
        int pilihan;
        do {
            cout << "\n=== MENU EDIT DATA ===\n";
            cout << "1. Edit nama\n";
            cout << "2. Edit jenis kelamin\n";
            cout << "3. Edit umur\n";
            cout << "4. Edit berat\n";
            cout << "5. Edit tinggi\n";
            cout << "6. Edit tanggal catat\n";
            cout << "7. Edit aktivitas\n";
            cout << "8. Edit tujuan\n";
            cout << "9. Edit catatan\n";
            cout << "10. Selesai edit\n";
            pilihan = inputAngka("Pilih edit: ", 1, 10);

            prosesEditData(index, pilihan);
        } while (pilihan != 10);
    }

    // Fungsi untuk menjalankan proses edit sesuai pilihan user.
    void prosesEditData(int index, int pilihan) {
        switch (pilihan) {
            case 1:
                nama[index] = inputTeks("Nama baru: ");
                break;
            case 2:
                jenisKelamin[index] = inputJenisKelamin();
                break;
            case 3:
                umur[index] = inputAngka("Umur baru: ", 1, 120);
                break;
            case 4:
                berat[index] = inputFloat("Berat baru kg: ", 1, 300);
                hitungUlangDataPadaIndex(index);
                break;
            case 5:
                tinggi[index] = inputFloat("Tinggi baru meter: ", 0.3f, 2.5f);
                hitungUlangDataPadaIndex(index);
                break;
            case 6:
                tanggalCatat[index] = inputTeks("Tanggal catat baru: ");
                break;
            case 7:
                aktivitas[index] = inputTeks("Aktivitas baru: ");
                break;
            case 8:
                tujuan[index] = inputTeks("Tujuan baru: ");
                break;
            case 9:
                catatan[index] = inputTeks("Catatan baru: ");
                break;
            case 10:
                cout << "\nEdit data selesai.\n";
                break;
            default:
                cout << "\nPilihan edit tidak valid.\n";
                break;
        }
    }

    // Fungsi untuk menghapus data berdasarkan ID.
    void hapusDataBerdasarkanId() {
        if (dataMasihKosong()) {
            return;
        }

        int idCari = inputAngka("\nMasukkan ID yang ingin dihapus: ", 1, 999999);
        int index = cariIndexBerdasarkanId(idCari);

        if (index == -1) {
            cout << "\nData dengan ID tersebut tidak ditemukan.\n";
            return;
        }

        geserDataKeKiri(index);
        jumlahData--;

        cout << "\nData berhasil dihapus.\n";
    }

    // Fungsi untuk menggeser data ke kiri setelah ada data yang dihapus.
    void geserDataKeKiri(int mulaiIndex) {
        for (int i = mulaiIndex; i < jumlahData - 1; i++) {
            id[i] = id[i + 1];
            nama[i] = nama[i + 1];
            jenisKelamin[i] = jenisKelamin[i + 1];
            umur[i] = umur[i + 1];
            berat[i] = berat[i + 1];
            tinggi[i] = tinggi[i + 1];
            bmi[i] = bmi[i + 1];
            kategori[i] = kategori[i + 1];
            tanggalCatat[i] = tanggalCatat[i + 1];
            aktivitas[i] = aktivitas[i + 1];
            tujuan[i] = tujuan[i + 1];
            catatan[i] = catatan[i + 1];
        }
    }

    // Fungsi untuk mencari data berdasarkan sebagian atau seluruh nama.
    void cariDataBerdasarkanNama() {
        if (dataMasihKosong()) {
            return;
        }

        string kataKunci = inputTeks("\nMasukkan nama yang dicari: ");
        bool ditemukan = false;

        cout << "\n=== HASIL PENCARIAN NAMA ===\n";
        cetakJudulTabel();

        for (int i = 0; i < jumlahData; i++) {
            if (teksMengandung(nama[i], kataKunci)) {
                cetakBarisData(i);
                ditemukan = true;
            }
        }

        if (!ditemukan) {
            cout << "Data tidak ditemukan.\n";
        }
    }

    // Fungsi untuk mencari data berdasarkan kategori BMI.
    void cariDataBerdasarkanKategori() {
        if (dataMasihKosong()) {
            return;
        }

        tampilkanPilihanKategori();
        int pilihan = inputAngka("Pilih kategori: ", 1, 4);
        string kategoriCari = kategoriDariPilihan(pilihan);
        bool ditemukan = false;

        cout << "\n=== HASIL PENCARIAN KATEGORI " << kategoriCari << " ===\n";
        cetakJudulTabel();

        for (int i = 0; i < jumlahData; i++) {
            if (kategori[i] == kategoriCari) {
                cetakBarisData(i);
                ditemukan = true;
            }
        }

        if (!ditemukan) {
            cout << "Data tidak ditemukan.\n";
        }
    }

    // Fungsi untuk menampilkan daftar pilihan kategori BMI.
    void tampilkanPilihanKategori() {
        cout << "\nKategori BMI:\n";
        cout << "1. Kurus\n";
        cout << "2. Normal\n";
        cout << "3. Gemuk\n";
        cout << "4. Obesitas\n";
    }

    // Fungsi untuk mengubah pilihan angka menjadi teks kategori BMI.
    string kategoriDariPilihan(int pilihan) {
        if (pilihan == 1) {
            return "Kurus";
        } else if (pilihan == 2) {
            return "Normal";
        } else if (pilihan == 3) {
            return "Gemuk";
        }
        return "Obesitas";
    }

    // Fungsi untuk menukar dua data berdasarkan index.
    void tukarData(int a, int b) {
        swap(id[a], id[b]);
        swap(nama[a], nama[b]);
        swap(jenisKelamin[a], jenisKelamin[b]);
        swap(umur[a], umur[b]);
        swap(berat[a], berat[b]);
        swap(tinggi[a], tinggi[b]);
        swap(bmi[a], bmi[b]);
        swap(kategori[a], kategori[b]);
        swap(tanggalCatat[a], tanggalCatat[b]);
        swap(aktivitas[a], aktivitas[b]);
        swap(tujuan[a], tujuan[b]);
        swap(catatan[a], catatan[b]);
    }

    // Fungsi untuk mengurutkan data berdasarkan BMI dari kecil ke besar.
    void sortingBmiKecilKeBesar() {
        if (dataMasihKosong()) {
            return;
        }

        for (int i = 0; i < jumlahData - 1; i++) {
            for (int j = 0; j < jumlahData - i - 1; j++) {
                if (bmi[j] > bmi[j + 1]) {
                    tukarData(j, j + 1);
                }
            }
        }

        cout << "\nData berhasil diurutkan berdasarkan BMI kecil ke besar.\n";
        tampilkanSemuaData();
    }

    // Fungsi untuk mengurutkan data berdasarkan BMI dari besar ke kecil.
    void sortingBmiBesarKeKecil() {
        if (dataMasihKosong()) {
            return;
        }

        for (int i = 0; i < jumlahData - 1; i++) {
            for (int j = 0; j < jumlahData - i - 1; j++) {
                if (bmi[j] < bmi[j + 1]) {
                    tukarData(j, j + 1);
                }
            }
        }

        cout << "\nData berhasil diurutkan berdasarkan BMI besar ke kecil.\n";
        tampilkanSemuaData();
    }

    // Fungsi untuk mengurutkan data berdasarkan nama dari A sampai Z.
    void sortingNamaAZ() {
        if (dataMasihKosong()) {
            return;
        }

        for (int i = 0; i < jumlahData - 1; i++) {
            for (int j = 0; j < jumlahData - i - 1; j++) {
                if (ubahKeHurufKecil(nama[j]) > ubahKeHurufKecil(nama[j + 1])) {
                    tukarData(j, j + 1);
                }
            }
        }

        cout << "\nData berhasil diurutkan berdasarkan nama A-Z.\n";
        tampilkanSemuaData();
    }

    // Fungsi untuk mengurutkan data berdasarkan nama dari Z sampai A.
    void sortingNamaZA() {
        if (dataMasihKosong()) {
            return;
        }

        for (int i = 0; i < jumlahData - 1; i++) {
            for (int j = 0; j < jumlahData - i - 1; j++) {
                if (ubahKeHurufKecil(nama[j]) < ubahKeHurufKecil(nama[j + 1])) {
                    tukarData(j, j + 1);
                }
            }
        }

        cout << "\nData berhasil diurutkan berdasarkan nama Z-A.\n";
        tampilkanSemuaData();
    }

    // Fungsi untuk mengurutkan data berdasarkan berat badan dari kecil ke besar.
    void sortingBeratKecilKeBesar() {
        if (dataMasihKosong()) {
            return;
        }

        for (int i = 0; i < jumlahData - 1; i++) {
            for (int j = 0; j < jumlahData - i - 1; j++) {
                if (berat[j] > berat[j + 1]) {
                    tukarData(j, j + 1);
                }
            }
        }

        cout << "\nData berhasil diurutkan berdasarkan berat badan kecil ke besar.\n";
        tampilkanSemuaData();
    }

    // Fungsi untuk mengurutkan data berdasarkan tinggi badan dari kecil ke besar.
    void sortingTinggiKecilKeBesar() {
        if (dataMasihKosong()) {
            return;
        }

        for (int i = 0; i < jumlahData - 1; i++) {
            for (int j = 0; j < jumlahData - i - 1; j++) {
                if (tinggi[j] > tinggi[j + 1]) {
                    tukarData(j, j + 1);
                }
            }
        }

        cout << "\nData berhasil diurutkan berdasarkan tinggi badan kecil ke besar.\n";
        tampilkanSemuaData();
    }

    // Fungsi untuk menghitung rata-rata BMI dari semua data.
    float hitungRataRataBMI() {
        if (jumlahData == 0) {
            return 0;
        }

        float total = 0;
        for (int i = 0; i < jumlahData; i++) {
            total = total + bmi[i];
        }

        return total / jumlahData;
    }

    // Fungsi untuk mencari nilai BMI paling kecil.
    float cariBmiTerkecil() {
        if (jumlahData == 0) {
            return 0;
        }

        float terkecil = bmi[0];
        for (int i = 1; i < jumlahData; i++) {
            if (bmi[i] < terkecil) {
                terkecil = bmi[i];
            }
        }

        return terkecil;
    }

    // Fungsi untuk mencari nilai BMI paling besar.
    float cariBmiTerbesar() {
        if (jumlahData == 0) {
            return 0;
        }

        float terbesar = bmi[0];
        for (int i = 1; i < jumlahData; i++) {
            if (bmi[i] > terbesar) {
                terbesar = bmi[i];
            }
        }

        return terbesar;
    }

    // Fungsi untuk mencari index data dengan BMI terkecil.
    int cariIndexBmiTerkecil() {
        if (jumlahData == 0) {
            return -1;
        }

        int indexTerkecil = 0;
        for (int i = 1; i < jumlahData; i++) {
            if (bmi[i] < bmi[indexTerkecil]) {
                indexTerkecil = i;
            }
        }

        return indexTerkecil;
    }

    // Fungsi untuk mencari index data dengan BMI terbesar.
    int cariIndexBmiTerbesar() {
        if (jumlahData == 0) {
            return -1;
        }

        int indexTerbesar = 0;
        for (int i = 1; i < jumlahData; i++) {
            if (bmi[i] > bmi[indexTerbesar]) {
                indexTerbesar = i;
            }
        }

        return indexTerbesar;
    }

    // Fungsi untuk menampilkan statistik umum dari data BMI.
    void tampilkanStatistikBMI() {
        if (dataMasihKosong()) {
            return;
        }

        int indexMin = cariIndexBmiTerkecil();
        int indexMax = cariIndexBmiTerbesar();

        cout << "\n=== STATISTIK BMI ===\n";
        cout << "Jumlah data       : " << jumlahData << "\n";
        cout << "Rata-rata BMI     : " << fixed << setprecision(2) << hitungRataRataBMI() << "\n";
        cout << "BMI terkecil      : " << fixed << setprecision(2) << cariBmiTerkecil() << " oleh " << nama[indexMin] << "\n";
        cout << "BMI terbesar      : " << fixed << setprecision(2) << cariBmiTerbesar() << " oleh " << nama[indexMax] << "\n";
        cout << "Kategori rata-rata: " << tentukanKategoriBMI(hitungRataRataBMI()) << "\n";
    }

    // Fungsi untuk menghitung jumlah data pada kategori tertentu.
    int hitungJumlahKategori(string kategoriDicari) {
        int total = 0;
        for (int i = 0; i < jumlahData; i++) {
            if (kategori[i] == kategoriDicari) {
                total++;
            }
        }
        return total;
    }

    // Fungsi untuk menampilkan rekap jumlah kategori BMI.
    void tampilkanRekapKategori() {
        if (dataMasihKosong()) {
            return;
        }

        int jumlahKurus = hitungJumlahKategori("Kurus");
        int jumlahNormal = hitungJumlahKategori("Normal");
        int jumlahGemuk = hitungJumlahKategori("Gemuk");
        int jumlahObesitas = hitungJumlahKategori("Obesitas");

        cout << "\n=== REKAP KATEGORI BMI ===\n";
        cout << "Kurus    : " << jumlahKurus << " orang\n";
        cout << "Normal   : " << jumlahNormal << " orang\n";
        cout << "Gemuk    : " << jumlahGemuk << " orang\n";
        cout << "Obesitas : " << jumlahObesitas << " orang\n";
    }

    // Fungsi untuk menyimpan data BMI ke file teks.
    void simpanDataKeFile() {
        if (dataMasihKosong()) {
            return;
        }

        ofstream file("data_bmi.txt");

        if (!file.is_open()) {
            cout << "\nFile gagal dibuka untuk menyimpan data.\n";
            return;
        }

        file << jumlahData << "\n";
        file << nomorIdTerakhir << "\n";

        for (int i = 0; i < jumlahData; i++) {
            file << id[i] << "|"
                 << nama[i] << "|"
                 << jenisKelamin[i] << "|"
                 << umur[i] << "|"
                 << berat[i] << "|"
                 << tinggi[i] << "|"
                 << bmi[i] << "|"
                 << kategori[i] << "|"
                 << tanggalCatat[i] << "|"
                 << aktivitas[i] << "|"
                 << tujuan[i] << "|"
                 << catatan[i] << "\n";
        }

        file.close();
        cout << "\nData berhasil disimpan ke file data_bmi.txt.\n";
    }

    // Fungsi untuk mengambil kolom tertentu dari baris file yang dipisahkan tanda garis tegak.
    string ambilKolom(string baris, int nomorKolom) {
        string hasil = "";
        int kolomSekarang = 1;

        int panjangBaris = baris.length();
        for (int i = 0; i < panjangBaris; i++) {
            if (baris[i] == '|') {
                kolomSekarang++;
            } else if (kolomSekarang == nomorKolom) {
                hasil = hasil + baris[i];
            }
        }

        return hasil;
    }

    // Fungsi untuk mengubah teks angka menjadi integer sederhana.
    int teksKeInteger(string teks) {
        int angka = 0;
        bool negatif = false;
        int mulai = 0;

        if (teks.length() > 0 && teks[0] == '-') {
            negatif = true;
            mulai = 1;
        }

        int panjangTeks = teks.length();
        for (int i = mulai; i < panjangTeks; i++) {
            if (teks[i] >= '0' && teks[i] <= '9') {
                angka = angka * 10 + (teks[i] - '0');
            }
        }

        if (negatif) {
            angka = angka * -1;
        }

        return angka;
    }

    // Fungsi untuk mengubah teks angka menjadi float sederhana.
    float teksKeFloat(string teks) {
        float angka = 0;
        float pembagi = 10;
        bool setelahKoma = false;
        bool negatif = false;
        int mulai = 0;

        if (teks.length() > 0 && teks[0] == '-') {
            negatif = true;
            mulai = 1;
        }

        int panjangTeks = teks.length();
        for (int i = mulai; i < panjangTeks; i++) {
            if (teks[i] == '.') {
                setelahKoma = true;
            } else if (teks[i] >= '0' && teks[i] <= '9') {
                if (!setelahKoma) {
                    angka = angka * 10 + (teks[i] - '0');
                } else {
                    angka = angka + ((teks[i] - '0') / pembagi);
                    pembagi = pembagi * 10;
                }
            }
        }

        if (negatif) {
            angka = angka * -1;
        }

        return angka;
    }

    // Fungsi untuk membaca data BMI dari file teks.
    void loadDataDariFile() {
        ifstream file("data_bmi.txt");

        if (!file.is_open()) {
            cout << "\nFile data_bmi.txt tidak ditemukan.\n";
            return;
        }

        string baris;
        getline(file, baris);
        jumlahData = teksKeInteger(baris);

        getline(file, baris);
        nomorIdTerakhir = teksKeInteger(baris);

        if (jumlahData > MAKS_DATA) {
            jumlahData = MAKS_DATA;
        }

        for (int i = 0; i < jumlahData; i++) {
            getline(file, baris);
            id[i] = teksKeInteger(ambilKolom(baris, 1));
            nama[i] = ambilKolom(baris, 2);
            jenisKelamin[i] = ambilKolom(baris, 3);
            umur[i] = teksKeInteger(ambilKolom(baris, 4));
            berat[i] = teksKeFloat(ambilKolom(baris, 5));
            tinggi[i] = teksKeFloat(ambilKolom(baris, 6));
            bmi[i] = teksKeFloat(ambilKolom(baris, 7));
            kategori[i] = ambilKolom(baris, 8);
            tanggalCatat[i] = ambilKolom(baris, 9);
            aktivitas[i] = ambilKolom(baris, 10);
            tujuan[i] = ambilKolom(baris, 11);
            catatan[i] = ambilKolom(baris, 12);
        }

        file.close();
        cout << "\nData berhasil dibaca dari file data_bmi.txt.\n";
    }

    // Fungsi untuk mengekspor laporan sederhana ke file teks.
    void exportLaporanSederhana() {
        if (dataMasihKosong()) {
            return;
        }

        ofstream file("laporan_bmi.txt");

        if (!file.is_open()) {
            cout << "\nFile gagal dibuat.\n";
            return;
        }

        file << "LAPORAN DATA BMI\n";
        file << "================\n\n";
        file << "Jumlah data       : " << jumlahData << "\n";
        file << "Rata-rata BMI     : " << fixed << setprecision(2) << hitungRataRataBMI() << "\n";
        file << "BMI terkecil      : " << fixed << setprecision(2) << cariBmiTerkecil() << "\n";
        file << "BMI terbesar      : " << fixed << setprecision(2) << cariBmiTerbesar() << "\n\n";
        file << "REKAP KATEGORI\n";
        file << "Kurus    : " << hitungJumlahKategori("Kurus") << "\n";
        file << "Normal   : " << hitungJumlahKategori("Normal") << "\n";
        file << "Gemuk    : " << hitungJumlahKategori("Gemuk") << "\n";
        file << "Obesitas : " << hitungJumlahKategori("Obesitas") << "\n\n";
        file << "DAFTAR DATA\n";

        for (int i = 0; i < jumlahData; i++) {
            file << id[i] << " - "
                 << nama[i] << " - "
                 << fixed << setprecision(2) << bmi[i] << " - "
                 << kategori[i] << "\n";
        }

        file.close();
        cout << "\nLaporan berhasil dibuat di file laporan_bmi.txt.\n";
    }

    // Fungsi untuk menampilkan menu tips sehat.
    void menuTipsSehat() {
        int nomor;
        cout << "\nAda 180 tips sehat di dalam aplikasi.\n";
        nomor = inputAngka("Masukkan nomor tips 1-180: ", 1, 180);
        cout << ambilTipsSehat(nomor) << "\n";
    }

    // Fungsi untuk mengambil tips sehat berdasarkan nomor.
    string ambilTipsSehat(int nomor) {
        switch (nomor) {

            case 1:
                return tipsSehat001();
            case 2:
                return tipsSehat002();
            case 3:
                return tipsSehat003();
            case 4:
                return tipsSehat004();
            case 5:
                return tipsSehat005();
            case 6:
                return tipsSehat006();
            case 7:
                return tipsSehat007();
            case 8:
                return tipsSehat008();
            case 9:
                return tipsSehat009();
            case 10:
                return tipsSehat010();
            case 11:
                return tipsSehat011();
            case 12:
                return tipsSehat012();
            case 13:
                return tipsSehat013();
            case 14:
                return tipsSehat014();
            case 15:
                return tipsSehat015();
            case 16:
                return tipsSehat016();
            case 17:
                return tipsSehat017();
            case 18:
                return tipsSehat018();
            case 19:
                return tipsSehat019();
            case 20:
                return tipsSehat020();
            case 21:
                return tipsSehat021();
            case 22:
                return tipsSehat022();
            case 23:
                return tipsSehat023();
            case 24:
                return tipsSehat024();
            case 25:
                return tipsSehat025();
            case 26:
                return tipsSehat026();
            case 27:
                return tipsSehat027();
            case 28:
                return tipsSehat028();
            case 29:
                return tipsSehat029();
            case 30:
                return tipsSehat030();
            case 31:
                return tipsSehat031();
            case 32:
                return tipsSehat032();
            case 33:
                return tipsSehat033();
            case 34:
                return tipsSehat034();
            case 35:
                return tipsSehat035();
            case 36:
                return tipsSehat036();
            case 37:
                return tipsSehat037();
            case 38:
                return tipsSehat038();
            case 39:
                return tipsSehat039();
            case 40:
                return tipsSehat040();
            case 41:
                return tipsSehat041();
            case 42:
                return tipsSehat042();
            case 43:
                return tipsSehat043();
            case 44:
                return tipsSehat044();
            case 45:
                return tipsSehat045();
            case 46:
                return tipsSehat046();
            case 47:
                return tipsSehat047();
            case 48:
                return tipsSehat048();
            case 49:
                return tipsSehat049();
            case 50:
                return tipsSehat050();
            case 51:
                return tipsSehat051();
            case 52:
                return tipsSehat052();
            case 53:
                return tipsSehat053();
            case 54:
                return tipsSehat054();
            case 55:
                return tipsSehat055();
            case 56:
                return tipsSehat056();
            case 57:
                return tipsSehat057();
            case 58:
                return tipsSehat058();
            case 59:
                return tipsSehat059();
            case 60:
                return tipsSehat060();
            case 61:
                return tipsSehat061();
            case 62:
                return tipsSehat062();
            case 63:
                return tipsSehat063();
            case 64:
                return tipsSehat064();
            case 65:
                return tipsSehat065();
            case 66:
                return tipsSehat066();
            case 67:
                return tipsSehat067();
            case 68:
                return tipsSehat068();
            case 69:
                return tipsSehat069();
            case 70:
                return tipsSehat070();
            case 71:
                return tipsSehat071();
            case 72:
                return tipsSehat072();
            case 73:
                return tipsSehat073();
            case 74:
                return tipsSehat074();
            case 75:
                return tipsSehat075();
            case 76:
                return tipsSehat076();
            case 77:
                return tipsSehat077();
            case 78:
                return tipsSehat078();
            case 79:
                return tipsSehat079();
            case 80:
                return tipsSehat080();
            case 81:
                return tipsSehat081();
            case 82:
                return tipsSehat082();
            case 83:
                return tipsSehat083();
            case 84:
                return tipsSehat084();
            case 85:
                return tipsSehat085();
            case 86:
                return tipsSehat086();
            case 87:
                return tipsSehat087();
            case 88:
                return tipsSehat088();
            case 89:
                return tipsSehat089();
            case 90:
                return tipsSehat090();
            case 91:
                return tipsSehat091();
            case 92:
                return tipsSehat092();
            case 93:
                return tipsSehat093();
            case 94:
                return tipsSehat094();
            case 95:
                return tipsSehat095();
            case 96:
                return tipsSehat096();
            case 97:
                return tipsSehat097();
            case 98:
                return tipsSehat098();
            case 99:
                return tipsSehat099();
            case 100:
                return tipsSehat100();
            case 101:
                return tipsSehat101();
            case 102:
                return tipsSehat102();
            case 103:
                return tipsSehat103();
            case 104:
                return tipsSehat104();
            case 105:
                return tipsSehat105();
            case 106:
                return tipsSehat106();
            case 107:
                return tipsSehat107();
            case 108:
                return tipsSehat108();
            case 109:
                return tipsSehat109();
            case 110:
                return tipsSehat110();
            case 111:
                return tipsSehat111();
            case 112:
                return tipsSehat112();
            case 113:
                return tipsSehat113();
            case 114:
                return tipsSehat114();
            case 115:
                return tipsSehat115();
            case 116:
                return tipsSehat116();
            case 117:
                return tipsSehat117();
            case 118:
                return tipsSehat118();
            case 119:
                return tipsSehat119();
            case 120:
                return tipsSehat120();
            case 121:
                return tipsSehat121();
            case 122:
                return tipsSehat122();
            case 123:
                return tipsSehat123();
            case 124:
                return tipsSehat124();
            case 125:
                return tipsSehat125();
            case 126:
                return tipsSehat126();
            case 127:
                return tipsSehat127();
            case 128:
                return tipsSehat128();
            case 129:
                return tipsSehat129();
            case 130:
                return tipsSehat130();
            case 131:
                return tipsSehat131();
            case 132:
                return tipsSehat132();
            case 133:
                return tipsSehat133();
            case 134:
                return tipsSehat134();
            case 135:
                return tipsSehat135();
            case 136:
                return tipsSehat136();
            case 137:
                return tipsSehat137();
            case 138:
                return tipsSehat138();
            case 139:
                return tipsSehat139();
            case 140:
                return tipsSehat140();
            case 141:
                return tipsSehat141();
            case 142:
                return tipsSehat142();
            case 143:
                return tipsSehat143();
            case 144:
                return tipsSehat144();
            case 145:
                return tipsSehat145();
            case 146:
                return tipsSehat146();
            case 147:
                return tipsSehat147();
            case 148:
                return tipsSehat148();
            case 149:
                return tipsSehat149();
            case 150:
                return tipsSehat150();
            case 151:
                return tipsSehat151();
            case 152:
                return tipsSehat152();
            case 153:
                return tipsSehat153();
            case 154:
                return tipsSehat154();
            case 155:
                return tipsSehat155();
            case 156:
                return tipsSehat156();
            case 157:
                return tipsSehat157();
            case 158:
                return tipsSehat158();
            case 159:
                return tipsSehat159();
            case 160:
                return tipsSehat160();
            case 161:
                return tipsSehat161();
            case 162:
                return tipsSehat162();
            case 163:
                return tipsSehat163();
            case 164:
                return tipsSehat164();
            case 165:
                return tipsSehat165();
            case 166:
                return tipsSehat166();
            case 167:
                return tipsSehat167();
            case 168:
                return tipsSehat168();
            case 169:
                return tipsSehat169();
            case 170:
                return tipsSehat170();
            case 171:
                return tipsSehat171();
            case 172:
                return tipsSehat172();
            case 173:
                return tipsSehat173();
            case 174:
                return tipsSehat174();
            case 175:
                return tipsSehat175();
            case 176:
                return tipsSehat176();
            case 177:
                return tipsSehat177();
            case 178:
                return tipsSehat178();
            case 179:
                return tipsSehat179();
            case 180:
                return tipsSehat180();
            default:
                return "Tips tidak ditemukan.";
        }
    }


    // Fungsi untuk menyediakan tips sehat nomor 001.
    string tipsSehat001() {
        string teks;
        teks = "Tips 001: minum air putih yang cukup agar tubuh tidak mudah lemas.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 002.
    string tipsSehat002() {
        string teks;
        teks = "Tips 002: atur porsi makan dengan seimbang antara karbohidrat, protein, sayur, dan buah.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 003.
    string tipsSehat003() {
        string teks;
        teks = "Tips 003: kurangi minuman manis karena gula berlebih dapat menaikkan berat badan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 004.
    string tipsSehat004() {
        string teks;
        teks = "Tips 004: jalan kaki ringan selama beberapa menit agar tubuh tetap aktif.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 005.
    string tipsSehat005() {
        string teks;
        teks = "Tips 005: tidur cukup supaya proses pemulihan tubuh berjalan baik.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 006.
    string tipsSehat006() {
        string teks;
        teks = "Tips 006: jangan melewatkan sarapan jika tubuh terasa membutuhkan energi.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 007.
    string tipsSehat007() {
        string teks;
        teks = "Tips 007: pilih camilan yang lebih sehat seperti buah atau kacang secukupnya.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 008.
    string tipsSehat008() {
        string teks;
        teks = "Tips 008: catat berat badan secara berkala agar perubahan tubuh dapat dipantau.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 009.
    string tipsSehat009() {
        string teks;
        teks = "Tips 009: hindari makan terlalu larut malam secara berlebihan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 010.
    string tipsSehat010() {
        string teks;
        teks = "Tips 010: lakukan peregangan ringan saat terlalu lama duduk.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 011.
    string tipsSehat011() {
        string teks;
        teks = "Tips 011: minum air putih yang cukup agar tubuh tidak mudah lemas.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 012.
    string tipsSehat012() {
        string teks;
        teks = "Tips 012: atur porsi makan dengan seimbang antara karbohidrat, protein, sayur, dan buah.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 013.
    string tipsSehat013() {
        string teks;
        teks = "Tips 013: kurangi minuman manis karena gula berlebih dapat menaikkan berat badan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 014.
    string tipsSehat014() {
        string teks;
        teks = "Tips 014: jalan kaki ringan selama beberapa menit agar tubuh tetap aktif.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 015.
    string tipsSehat015() {
        string teks;
        teks = "Tips 015: tidur cukup supaya proses pemulihan tubuh berjalan baik.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 016.
    string tipsSehat016() {
        string teks;
        teks = "Tips 016: jangan melewatkan sarapan jika tubuh terasa membutuhkan energi.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 017.
    string tipsSehat017() {
        string teks;
        teks = "Tips 017: pilih camilan yang lebih sehat seperti buah atau kacang secukupnya.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 018.
    string tipsSehat018() {
        string teks;
        teks = "Tips 018: catat berat badan secara berkala agar perubahan tubuh dapat dipantau.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 019.
    string tipsSehat019() {
        string teks;
        teks = "Tips 019: hindari makan terlalu larut malam secara berlebihan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 020.
    string tipsSehat020() {
        string teks;
        teks = "Tips 020: lakukan peregangan ringan saat terlalu lama duduk.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 021.
    string tipsSehat021() {
        string teks;
        teks = "Tips 021: minum air putih yang cukup agar tubuh tidak mudah lemas.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 022.
    string tipsSehat022() {
        string teks;
        teks = "Tips 022: atur porsi makan dengan seimbang antara karbohidrat, protein, sayur, dan buah.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 023.
    string tipsSehat023() {
        string teks;
        teks = "Tips 023: kurangi minuman manis karena gula berlebih dapat menaikkan berat badan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 024.
    string tipsSehat024() {
        string teks;
        teks = "Tips 024: jalan kaki ringan selama beberapa menit agar tubuh tetap aktif.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 025.
    string tipsSehat025() {
        string teks;
        teks = "Tips 025: tidur cukup supaya proses pemulihan tubuh berjalan baik.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 026.
    string tipsSehat026() {
        string teks;
        teks = "Tips 026: jangan melewatkan sarapan jika tubuh terasa membutuhkan energi.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 027.
    string tipsSehat027() {
        string teks;
        teks = "Tips 027: pilih camilan yang lebih sehat seperti buah atau kacang secukupnya.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 028.
    string tipsSehat028() {
        string teks;
        teks = "Tips 028: catat berat badan secara berkala agar perubahan tubuh dapat dipantau.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 029.
    string tipsSehat029() {
        string teks;
        teks = "Tips 029: hindari makan terlalu larut malam secara berlebihan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 030.
    string tipsSehat030() {
        string teks;
        teks = "Tips 030: lakukan peregangan ringan saat terlalu lama duduk.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 031.
    string tipsSehat031() {
        string teks;
        teks = "Tips 031: minum air putih yang cukup agar tubuh tidak mudah lemas.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 032.
    string tipsSehat032() {
        string teks;
        teks = "Tips 032: atur porsi makan dengan seimbang antara karbohidrat, protein, sayur, dan buah.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 033.
    string tipsSehat033() {
        string teks;
        teks = "Tips 033: kurangi minuman manis karena gula berlebih dapat menaikkan berat badan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 034.
    string tipsSehat034() {
        string teks;
        teks = "Tips 034: jalan kaki ringan selama beberapa menit agar tubuh tetap aktif.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 035.
    string tipsSehat035() {
        string teks;
        teks = "Tips 035: tidur cukup supaya proses pemulihan tubuh berjalan baik.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 036.
    string tipsSehat036() {
        string teks;
        teks = "Tips 036: jangan melewatkan sarapan jika tubuh terasa membutuhkan energi.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 037.
    string tipsSehat037() {
        string teks;
        teks = "Tips 037: pilih camilan yang lebih sehat seperti buah atau kacang secukupnya.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 038.
    string tipsSehat038() {
        string teks;
        teks = "Tips 038: catat berat badan secara berkala agar perubahan tubuh dapat dipantau.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 039.
    string tipsSehat039() {
        string teks;
        teks = "Tips 039: hindari makan terlalu larut malam secara berlebihan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 040.
    string tipsSehat040() {
        string teks;
        teks = "Tips 040: lakukan peregangan ringan saat terlalu lama duduk.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 041.
    string tipsSehat041() {
        string teks;
        teks = "Tips 041: minum air putih yang cukup agar tubuh tidak mudah lemas.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 042.
    string tipsSehat042() {
        string teks;
        teks = "Tips 042: atur porsi makan dengan seimbang antara karbohidrat, protein, sayur, dan buah.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 043.
    string tipsSehat043() {
        string teks;
        teks = "Tips 043: kurangi minuman manis karena gula berlebih dapat menaikkan berat badan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 044.
    string tipsSehat044() {
        string teks;
        teks = "Tips 044: jalan kaki ringan selama beberapa menit agar tubuh tetap aktif.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 045.
    string tipsSehat045() {
        string teks;
        teks = "Tips 045: tidur cukup supaya proses pemulihan tubuh berjalan baik.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 046.
    string tipsSehat046() {
        string teks;
        teks = "Tips 046: jangan melewatkan sarapan jika tubuh terasa membutuhkan energi.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 047.
    string tipsSehat047() {
        string teks;
        teks = "Tips 047: pilih camilan yang lebih sehat seperti buah atau kacang secukupnya.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 048.
    string tipsSehat048() {
        string teks;
        teks = "Tips 048: catat berat badan secara berkala agar perubahan tubuh dapat dipantau.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 049.
    string tipsSehat049() {
        string teks;
        teks = "Tips 049: hindari makan terlalu larut malam secara berlebihan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 050.
    string tipsSehat050() {
        string teks;
        teks = "Tips 050: lakukan peregangan ringan saat terlalu lama duduk.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 051.
    string tipsSehat051() {
        string teks;
        teks = "Tips 051: minum air putih yang cukup agar tubuh tidak mudah lemas.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 052.
    string tipsSehat052() {
        string teks;
        teks = "Tips 052: atur porsi makan dengan seimbang antara karbohidrat, protein, sayur, dan buah.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 053.
    string tipsSehat053() {
        string teks;
        teks = "Tips 053: kurangi minuman manis karena gula berlebih dapat menaikkan berat badan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 054.
    string tipsSehat054() {
        string teks;
        teks = "Tips 054: jalan kaki ringan selama beberapa menit agar tubuh tetap aktif.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 055.
    string tipsSehat055() {
        string teks;
        teks = "Tips 055: tidur cukup supaya proses pemulihan tubuh berjalan baik.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 056.
    string tipsSehat056() {
        string teks;
        teks = "Tips 056: jangan melewatkan sarapan jika tubuh terasa membutuhkan energi.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 057.
    string tipsSehat057() {
        string teks;
        teks = "Tips 057: pilih camilan yang lebih sehat seperti buah atau kacang secukupnya.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 058.
    string tipsSehat058() {
        string teks;
        teks = "Tips 058: catat berat badan secara berkala agar perubahan tubuh dapat dipantau.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 059.
    string tipsSehat059() {
        string teks;
        teks = "Tips 059: hindari makan terlalu larut malam secara berlebihan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 060.
    string tipsSehat060() {
        string teks;
        teks = "Tips 060: lakukan peregangan ringan saat terlalu lama duduk.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 061.
    string tipsSehat061() {
        string teks;
        teks = "Tips 061: minum air putih yang cukup agar tubuh tidak mudah lemas.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 062.
    string tipsSehat062() {
        string teks;
        teks = "Tips 062: atur porsi makan dengan seimbang antara karbohidrat, protein, sayur, dan buah.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 063.
    string tipsSehat063() {
        string teks;
        teks = "Tips 063: kurangi minuman manis karena gula berlebih dapat menaikkan berat badan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 064.
    string tipsSehat064() {
        string teks;
        teks = "Tips 064: jalan kaki ringan selama beberapa menit agar tubuh tetap aktif.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 065.
    string tipsSehat065() {
        string teks;
        teks = "Tips 065: tidur cukup supaya proses pemulihan tubuh berjalan baik.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 066.
    string tipsSehat066() {
        string teks;
        teks = "Tips 066: jangan melewatkan sarapan jika tubuh terasa membutuhkan energi.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 067.
    string tipsSehat067() {
        string teks;
        teks = "Tips 067: pilih camilan yang lebih sehat seperti buah atau kacang secukupnya.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 068.
    string tipsSehat068() {
        string teks;
        teks = "Tips 068: catat berat badan secara berkala agar perubahan tubuh dapat dipantau.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 069.
    string tipsSehat069() {
        string teks;
        teks = "Tips 069: hindari makan terlalu larut malam secara berlebihan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 070.
    string tipsSehat070() {
        string teks;
        teks = "Tips 070: lakukan peregangan ringan saat terlalu lama duduk.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 071.
    string tipsSehat071() {
        string teks;
        teks = "Tips 071: minum air putih yang cukup agar tubuh tidak mudah lemas.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 072.
    string tipsSehat072() {
        string teks;
        teks = "Tips 072: atur porsi makan dengan seimbang antara karbohidrat, protein, sayur, dan buah.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 073.
    string tipsSehat073() {
        string teks;
        teks = "Tips 073: kurangi minuman manis karena gula berlebih dapat menaikkan berat badan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 074.
    string tipsSehat074() {
        string teks;
        teks = "Tips 074: jalan kaki ringan selama beberapa menit agar tubuh tetap aktif.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 075.
    string tipsSehat075() {
        string teks;
        teks = "Tips 075: tidur cukup supaya proses pemulihan tubuh berjalan baik.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 076.
    string tipsSehat076() {
        string teks;
        teks = "Tips 076: jangan melewatkan sarapan jika tubuh terasa membutuhkan energi.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 077.
    string tipsSehat077() {
        string teks;
        teks = "Tips 077: pilih camilan yang lebih sehat seperti buah atau kacang secukupnya.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 078.
    string tipsSehat078() {
        string teks;
        teks = "Tips 078: catat berat badan secara berkala agar perubahan tubuh dapat dipantau.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 079.
    string tipsSehat079() {
        string teks;
        teks = "Tips 079: hindari makan terlalu larut malam secara berlebihan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 080.
    string tipsSehat080() {
        string teks;
        teks = "Tips 080: lakukan peregangan ringan saat terlalu lama duduk.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 081.
    string tipsSehat081() {
        string teks;
        teks = "Tips 081: minum air putih yang cukup agar tubuh tidak mudah lemas.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 082.
    string tipsSehat082() {
        string teks;
        teks = "Tips 082: atur porsi makan dengan seimbang antara karbohidrat, protein, sayur, dan buah.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 083.
    string tipsSehat083() {
        string teks;
        teks = "Tips 083: kurangi minuman manis karena gula berlebih dapat menaikkan berat badan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 084.
    string tipsSehat084() {
        string teks;
        teks = "Tips 084: jalan kaki ringan selama beberapa menit agar tubuh tetap aktif.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 085.
    string tipsSehat085() {
        string teks;
        teks = "Tips 085: tidur cukup supaya proses pemulihan tubuh berjalan baik.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 086.
    string tipsSehat086() {
        string teks;
        teks = "Tips 086: jangan melewatkan sarapan jika tubuh terasa membutuhkan energi.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 087.
    string tipsSehat087() {
        string teks;
        teks = "Tips 087: pilih camilan yang lebih sehat seperti buah atau kacang secukupnya.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 088.
    string tipsSehat088() {
        string teks;
        teks = "Tips 088: catat berat badan secara berkala agar perubahan tubuh dapat dipantau.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 089.
    string tipsSehat089() {
        string teks;
        teks = "Tips 089: hindari makan terlalu larut malam secara berlebihan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 090.
    string tipsSehat090() {
        string teks;
        teks = "Tips 090: lakukan peregangan ringan saat terlalu lama duduk.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 091.
    string tipsSehat091() {
        string teks;
        teks = "Tips 091: minum air putih yang cukup agar tubuh tidak mudah lemas.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 092.
    string tipsSehat092() {
        string teks;
        teks = "Tips 092: atur porsi makan dengan seimbang antara karbohidrat, protein, sayur, dan buah.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 093.
    string tipsSehat093() {
        string teks;
        teks = "Tips 093: kurangi minuman manis karena gula berlebih dapat menaikkan berat badan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 094.
    string tipsSehat094() {
        string teks;
        teks = "Tips 094: jalan kaki ringan selama beberapa menit agar tubuh tetap aktif.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 095.
    string tipsSehat095() {
        string teks;
        teks = "Tips 095: tidur cukup supaya proses pemulihan tubuh berjalan baik.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 096.
    string tipsSehat096() {
        string teks;
        teks = "Tips 096: jangan melewatkan sarapan jika tubuh terasa membutuhkan energi.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 097.
    string tipsSehat097() {
        string teks;
        teks = "Tips 097: pilih camilan yang lebih sehat seperti buah atau kacang secukupnya.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 098.
    string tipsSehat098() {
        string teks;
        teks = "Tips 098: catat berat badan secara berkala agar perubahan tubuh dapat dipantau.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 099.
    string tipsSehat099() {
        string teks;
        teks = "Tips 099: hindari makan terlalu larut malam secara berlebihan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 100.
    string tipsSehat100() {
        string teks;
        teks = "Tips 100: lakukan peregangan ringan saat terlalu lama duduk.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 101.
    string tipsSehat101() {
        string teks;
        teks = "Tips 101: minum air putih yang cukup agar tubuh tidak mudah lemas.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 102.
    string tipsSehat102() {
        string teks;
        teks = "Tips 102: atur porsi makan dengan seimbang antara karbohidrat, protein, sayur, dan buah.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 103.
    string tipsSehat103() {
        string teks;
        teks = "Tips 103: kurangi minuman manis karena gula berlebih dapat menaikkan berat badan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 104.
    string tipsSehat104() {
        string teks;
        teks = "Tips 104: jalan kaki ringan selama beberapa menit agar tubuh tetap aktif.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 105.
    string tipsSehat105() {
        string teks;
        teks = "Tips 105: tidur cukup supaya proses pemulihan tubuh berjalan baik.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 106.
    string tipsSehat106() {
        string teks;
        teks = "Tips 106: jangan melewatkan sarapan jika tubuh terasa membutuhkan energi.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 107.
    string tipsSehat107() {
        string teks;
        teks = "Tips 107: pilih camilan yang lebih sehat seperti buah atau kacang secukupnya.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 108.
    string tipsSehat108() {
        string teks;
        teks = "Tips 108: catat berat badan secara berkala agar perubahan tubuh dapat dipantau.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 109.
    string tipsSehat109() {
        string teks;
        teks = "Tips 109: hindari makan terlalu larut malam secara berlebihan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 110.
    string tipsSehat110() {
        string teks;
        teks = "Tips 110: lakukan peregangan ringan saat terlalu lama duduk.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 111.
    string tipsSehat111() {
        string teks;
        teks = "Tips 111: minum air putih yang cukup agar tubuh tidak mudah lemas.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 112.
    string tipsSehat112() {
        string teks;
        teks = "Tips 112: atur porsi makan dengan seimbang antara karbohidrat, protein, sayur, dan buah.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 113.
    string tipsSehat113() {
        string teks;
        teks = "Tips 113: kurangi minuman manis karena gula berlebih dapat menaikkan berat badan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 114.
    string tipsSehat114() {
        string teks;
        teks = "Tips 114: jalan kaki ringan selama beberapa menit agar tubuh tetap aktif.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 115.
    string tipsSehat115() {
        string teks;
        teks = "Tips 115: tidur cukup supaya proses pemulihan tubuh berjalan baik.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 116.
    string tipsSehat116() {
        string teks;
        teks = "Tips 116: jangan melewatkan sarapan jika tubuh terasa membutuhkan energi.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 117.
    string tipsSehat117() {
        string teks;
        teks = "Tips 117: pilih camilan yang lebih sehat seperti buah atau kacang secukupnya.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 118.
    string tipsSehat118() {
        string teks;
        teks = "Tips 118: catat berat badan secara berkala agar perubahan tubuh dapat dipantau.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 119.
    string tipsSehat119() {
        string teks;
        teks = "Tips 119: hindari makan terlalu larut malam secara berlebihan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 120.
    string tipsSehat120() {
        string teks;
        teks = "Tips 120: lakukan peregangan ringan saat terlalu lama duduk.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 121.
    string tipsSehat121() {
        string teks;
        teks = "Tips 121: minum air putih yang cukup agar tubuh tidak mudah lemas.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 122.
    string tipsSehat122() {
        string teks;
        teks = "Tips 122: atur porsi makan dengan seimbang antara karbohidrat, protein, sayur, dan buah.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 123.
    string tipsSehat123() {
        string teks;
        teks = "Tips 123: kurangi minuman manis karena gula berlebih dapat menaikkan berat badan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 124.
    string tipsSehat124() {
        string teks;
        teks = "Tips 124: jalan kaki ringan selama beberapa menit agar tubuh tetap aktif.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 125.
    string tipsSehat125() {
        string teks;
        teks = "Tips 125: tidur cukup supaya proses pemulihan tubuh berjalan baik.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 126.
    string tipsSehat126() {
        string teks;
        teks = "Tips 126: jangan melewatkan sarapan jika tubuh terasa membutuhkan energi.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 127.
    string tipsSehat127() {
        string teks;
        teks = "Tips 127: pilih camilan yang lebih sehat seperti buah atau kacang secukupnya.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 128.
    string tipsSehat128() {
        string teks;
        teks = "Tips 128: catat berat badan secara berkala agar perubahan tubuh dapat dipantau.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 129.
    string tipsSehat129() {
        string teks;
        teks = "Tips 129: hindari makan terlalu larut malam secara berlebihan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 130.
    string tipsSehat130() {
        string teks;
        teks = "Tips 130: lakukan peregangan ringan saat terlalu lama duduk.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 131.
    string tipsSehat131() {
        string teks;
        teks = "Tips 131: minum air putih yang cukup agar tubuh tidak mudah lemas.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 132.
    string tipsSehat132() {
        string teks;
        teks = "Tips 132: atur porsi makan dengan seimbang antara karbohidrat, protein, sayur, dan buah.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 133.
    string tipsSehat133() {
        string teks;
        teks = "Tips 133: kurangi minuman manis karena gula berlebih dapat menaikkan berat badan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 134.
    string tipsSehat134() {
        string teks;
        teks = "Tips 134: jalan kaki ringan selama beberapa menit agar tubuh tetap aktif.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 135.
    string tipsSehat135() {
        string teks;
        teks = "Tips 135: tidur cukup supaya proses pemulihan tubuh berjalan baik.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 136.
    string tipsSehat136() {
        string teks;
        teks = "Tips 136: jangan melewatkan sarapan jika tubuh terasa membutuhkan energi.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 137.
    string tipsSehat137() {
        string teks;
        teks = "Tips 137: pilih camilan yang lebih sehat seperti buah atau kacang secukupnya.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 138.
    string tipsSehat138() {
        string teks;
        teks = "Tips 138: catat berat badan secara berkala agar perubahan tubuh dapat dipantau.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 139.
    string tipsSehat139() {
        string teks;
        teks = "Tips 139: hindari makan terlalu larut malam secara berlebihan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 140.
    string tipsSehat140() {
        string teks;
        teks = "Tips 140: lakukan peregangan ringan saat terlalu lama duduk.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 141.
    string tipsSehat141() {
        string teks;
        teks = "Tips 141: minum air putih yang cukup agar tubuh tidak mudah lemas.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 142.
    string tipsSehat142() {
        string teks;
        teks = "Tips 142: atur porsi makan dengan seimbang antara karbohidrat, protein, sayur, dan buah.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 143.
    string tipsSehat143() {
        string teks;
        teks = "Tips 143: kurangi minuman manis karena gula berlebih dapat menaikkan berat badan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 144.
    string tipsSehat144() {
        string teks;
        teks = "Tips 144: jalan kaki ringan selama beberapa menit agar tubuh tetap aktif.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 145.
    string tipsSehat145() {
        string teks;
        teks = "Tips 145: tidur cukup supaya proses pemulihan tubuh berjalan baik.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 146.
    string tipsSehat146() {
        string teks;
        teks = "Tips 146: jangan melewatkan sarapan jika tubuh terasa membutuhkan energi.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 147.
    string tipsSehat147() {
        string teks;
        teks = "Tips 147: pilih camilan yang lebih sehat seperti buah atau kacang secukupnya.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 148.
    string tipsSehat148() {
        string teks;
        teks = "Tips 148: catat berat badan secara berkala agar perubahan tubuh dapat dipantau.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 149.
    string tipsSehat149() {
        string teks;
        teks = "Tips 149: hindari makan terlalu larut malam secara berlebihan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 150.
    string tipsSehat150() {
        string teks;
        teks = "Tips 150: lakukan peregangan ringan saat terlalu lama duduk.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 151.
    string tipsSehat151() {
        string teks;
        teks = "Tips 151: minum air putih yang cukup agar tubuh tidak mudah lemas.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 152.
    string tipsSehat152() {
        string teks;
        teks = "Tips 152: atur porsi makan dengan seimbang antara karbohidrat, protein, sayur, dan buah.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 153.
    string tipsSehat153() {
        string teks;
        teks = "Tips 153: kurangi minuman manis karena gula berlebih dapat menaikkan berat badan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 154.
    string tipsSehat154() {
        string teks;
        teks = "Tips 154: jalan kaki ringan selama beberapa menit agar tubuh tetap aktif.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 155.
    string tipsSehat155() {
        string teks;
        teks = "Tips 155: tidur cukup supaya proses pemulihan tubuh berjalan baik.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 156.
    string tipsSehat156() {
        string teks;
        teks = "Tips 156: jangan melewatkan sarapan jika tubuh terasa membutuhkan energi.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 157.
    string tipsSehat157() {
        string teks;
        teks = "Tips 157: pilih camilan yang lebih sehat seperti buah atau kacang secukupnya.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 158.
    string tipsSehat158() {
        string teks;
        teks = "Tips 158: catat berat badan secara berkala agar perubahan tubuh dapat dipantau.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 159.
    string tipsSehat159() {
        string teks;
        teks = "Tips 159: hindari makan terlalu larut malam secara berlebihan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 160.
    string tipsSehat160() {
        string teks;
        teks = "Tips 160: lakukan peregangan ringan saat terlalu lama duduk.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 161.
    string tipsSehat161() {
        string teks;
        teks = "Tips 161: minum air putih yang cukup agar tubuh tidak mudah lemas.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 162.
    string tipsSehat162() {
        string teks;
        teks = "Tips 162: atur porsi makan dengan seimbang antara karbohidrat, protein, sayur, dan buah.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 163.
    string tipsSehat163() {
        string teks;
        teks = "Tips 163: kurangi minuman manis karena gula berlebih dapat menaikkan berat badan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 164.
    string tipsSehat164() {
        string teks;
        teks = "Tips 164: jalan kaki ringan selama beberapa menit agar tubuh tetap aktif.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 165.
    string tipsSehat165() {
        string teks;
        teks = "Tips 165: tidur cukup supaya proses pemulihan tubuh berjalan baik.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 166.
    string tipsSehat166() {
        string teks;
        teks = "Tips 166: jangan melewatkan sarapan jika tubuh terasa membutuhkan energi.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 167.
    string tipsSehat167() {
        string teks;
        teks = "Tips 167: pilih camilan yang lebih sehat seperti buah atau kacang secukupnya.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 168.
    string tipsSehat168() {
        string teks;
        teks = "Tips 168: catat berat badan secara berkala agar perubahan tubuh dapat dipantau.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 169.
    string tipsSehat169() {
        string teks;
        teks = "Tips 169: hindari makan terlalu larut malam secara berlebihan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 170.
    string tipsSehat170() {
        string teks;
        teks = "Tips 170: lakukan peregangan ringan saat terlalu lama duduk.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 171.
    string tipsSehat171() {
        string teks;
        teks = "Tips 171: minum air putih yang cukup agar tubuh tidak mudah lemas.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 172.
    string tipsSehat172() {
        string teks;
        teks = "Tips 172: atur porsi makan dengan seimbang antara karbohidrat, protein, sayur, dan buah.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 173.
    string tipsSehat173() {
        string teks;
        teks = "Tips 173: kurangi minuman manis karena gula berlebih dapat menaikkan berat badan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 174.
    string tipsSehat174() {
        string teks;
        teks = "Tips 174: jalan kaki ringan selama beberapa menit agar tubuh tetap aktif.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 175.
    string tipsSehat175() {
        string teks;
        teks = "Tips 175: tidur cukup supaya proses pemulihan tubuh berjalan baik.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 176.
    string tipsSehat176() {
        string teks;
        teks = "Tips 176: jangan melewatkan sarapan jika tubuh terasa membutuhkan energi.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 177.
    string tipsSehat177() {
        string teks;
        teks = "Tips 177: pilih camilan yang lebih sehat seperti buah atau kacang secukupnya.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 178.
    string tipsSehat178() {
        string teks;
        teks = "Tips 178: catat berat badan secara berkala agar perubahan tubuh dapat dipantau.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 179.
    string tipsSehat179() {
        string teks;
        teks = "Tips 179: hindari makan terlalu larut malam secara berlebihan.";
        return teks;
    }

    // Fungsi untuk menyediakan tips sehat nomor 180.
    string tipsSehat180() {
        string teks;
        teks = "Tips 180: lakukan peregangan ringan saat terlalu lama duduk.";
        return teks;
    }


    // Fungsi untuk menampilkan menu motivasi sehat.
    void menuMotivasiSehat() {
        int nomor;
        cout << "\nAda 160 motivasi sehat di dalam aplikasi.\n";
        nomor = inputAngka("Masukkan nomor motivasi 1-160: ", 1, 160);
        cout << ambilMotivasiSehat(nomor) << "\n";
    }

    // Fungsi untuk mengambil motivasi sehat berdasarkan nomor.
    string ambilMotivasiSehat(int nomor) {
        switch (nomor) {

            case 1:
                return motivasiSehat001();
            case 2:
                return motivasiSehat002();
            case 3:
                return motivasiSehat003();
            case 4:
                return motivasiSehat004();
            case 5:
                return motivasiSehat005();
            case 6:
                return motivasiSehat006();
            case 7:
                return motivasiSehat007();
            case 8:
                return motivasiSehat008();
            case 9:
                return motivasiSehat009();
            case 10:
                return motivasiSehat010();
            case 11:
                return motivasiSehat011();
            case 12:
                return motivasiSehat012();
            case 13:
                return motivasiSehat013();
            case 14:
                return motivasiSehat014();
            case 15:
                return motivasiSehat015();
            case 16:
                return motivasiSehat016();
            case 17:
                return motivasiSehat017();
            case 18:
                return motivasiSehat018();
            case 19:
                return motivasiSehat019();
            case 20:
                return motivasiSehat020();
            case 21:
                return motivasiSehat021();
            case 22:
                return motivasiSehat022();
            case 23:
                return motivasiSehat023();
            case 24:
                return motivasiSehat024();
            case 25:
                return motivasiSehat025();
            case 26:
                return motivasiSehat026();
            case 27:
                return motivasiSehat027();
            case 28:
                return motivasiSehat028();
            case 29:
                return motivasiSehat029();
            case 30:
                return motivasiSehat030();
            case 31:
                return motivasiSehat031();
            case 32:
                return motivasiSehat032();
            case 33:
                return motivasiSehat033();
            case 34:
                return motivasiSehat034();
            case 35:
                return motivasiSehat035();
            case 36:
                return motivasiSehat036();
            case 37:
                return motivasiSehat037();
            case 38:
                return motivasiSehat038();
            case 39:
                return motivasiSehat039();
            case 40:
                return motivasiSehat040();
            case 41:
                return motivasiSehat041();
            case 42:
                return motivasiSehat042();
            case 43:
                return motivasiSehat043();
            case 44:
                return motivasiSehat044();
            case 45:
                return motivasiSehat045();
            case 46:
                return motivasiSehat046();
            case 47:
                return motivasiSehat047();
            case 48:
                return motivasiSehat048();
            case 49:
                return motivasiSehat049();
            case 50:
                return motivasiSehat050();
            case 51:
                return motivasiSehat051();
            case 52:
                return motivasiSehat052();
            case 53:
                return motivasiSehat053();
            case 54:
                return motivasiSehat054();
            case 55:
                return motivasiSehat055();
            case 56:
                return motivasiSehat056();
            case 57:
                return motivasiSehat057();
            case 58:
                return motivasiSehat058();
            case 59:
                return motivasiSehat059();
            case 60:
                return motivasiSehat060();
            case 61:
                return motivasiSehat061();
            case 62:
                return motivasiSehat062();
            case 63:
                return motivasiSehat063();
            case 64:
                return motivasiSehat064();
            case 65:
                return motivasiSehat065();
            case 66:
                return motivasiSehat066();
            case 67:
                return motivasiSehat067();
            case 68:
                return motivasiSehat068();
            case 69:
                return motivasiSehat069();
            case 70:
                return motivasiSehat070();
            case 71:
                return motivasiSehat071();
            case 72:
                return motivasiSehat072();
            case 73:
                return motivasiSehat073();
            case 74:
                return motivasiSehat074();
            case 75:
                return motivasiSehat075();
            case 76:
                return motivasiSehat076();
            case 77:
                return motivasiSehat077();
            case 78:
                return motivasiSehat078();
            case 79:
                return motivasiSehat079();
            case 80:
                return motivasiSehat080();
            case 81:
                return motivasiSehat081();
            case 82:
                return motivasiSehat082();
            case 83:
                return motivasiSehat083();
            case 84:
                return motivasiSehat084();
            case 85:
                return motivasiSehat085();
            case 86:
                return motivasiSehat086();
            case 87:
                return motivasiSehat087();
            case 88:
                return motivasiSehat088();
            case 89:
                return motivasiSehat089();
            case 90:
                return motivasiSehat090();
            case 91:
                return motivasiSehat091();
            case 92:
                return motivasiSehat092();
            case 93:
                return motivasiSehat093();
            case 94:
                return motivasiSehat094();
            case 95:
                return motivasiSehat095();
            case 96:
                return motivasiSehat096();
            case 97:
                return motivasiSehat097();
            case 98:
                return motivasiSehat098();
            case 99:
                return motivasiSehat099();
            case 100:
                return motivasiSehat100();
            case 101:
                return motivasiSehat101();
            case 102:
                return motivasiSehat102();
            case 103:
                return motivasiSehat103();
            case 104:
                return motivasiSehat104();
            case 105:
                return motivasiSehat105();
            case 106:
                return motivasiSehat106();
            case 107:
                return motivasiSehat107();
            case 108:
                return motivasiSehat108();
            case 109:
                return motivasiSehat109();
            case 110:
                return motivasiSehat110();
            case 111:
                return motivasiSehat111();
            case 112:
                return motivasiSehat112();
            case 113:
                return motivasiSehat113();
            case 114:
                return motivasiSehat114();
            case 115:
                return motivasiSehat115();
            case 116:
                return motivasiSehat116();
            case 117:
                return motivasiSehat117();
            case 118:
                return motivasiSehat118();
            case 119:
                return motivasiSehat119();
            case 120:
                return motivasiSehat120();
            case 121:
                return motivasiSehat121();
            case 122:
                return motivasiSehat122();
            case 123:
                return motivasiSehat123();
            case 124:
                return motivasiSehat124();
            case 125:
                return motivasiSehat125();
            case 126:
                return motivasiSehat126();
            case 127:
                return motivasiSehat127();
            case 128:
                return motivasiSehat128();
            case 129:
                return motivasiSehat129();
            case 130:
                return motivasiSehat130();
            case 131:
                return motivasiSehat131();
            case 132:
                return motivasiSehat132();
            case 133:
                return motivasiSehat133();
            case 134:
                return motivasiSehat134();
            case 135:
                return motivasiSehat135();
            case 136:
                return motivasiSehat136();
            case 137:
                return motivasiSehat137();
            case 138:
                return motivasiSehat138();
            case 139:
                return motivasiSehat139();
            case 140:
                return motivasiSehat140();
            case 141:
                return motivasiSehat141();
            case 142:
                return motivasiSehat142();
            case 143:
                return motivasiSehat143();
            case 144:
                return motivasiSehat144();
            case 145:
                return motivasiSehat145();
            case 146:
                return motivasiSehat146();
            case 147:
                return motivasiSehat147();
            case 148:
                return motivasiSehat148();
            case 149:
                return motivasiSehat149();
            case 150:
                return motivasiSehat150();
            case 151:
                return motivasiSehat151();
            case 152:
                return motivasiSehat152();
            case 153:
                return motivasiSehat153();
            case 154:
                return motivasiSehat154();
            case 155:
                return motivasiSehat155();
            case 156:
                return motivasiSehat156();
            case 157:
                return motivasiSehat157();
            case 158:
                return motivasiSehat158();
            case 159:
                return motivasiSehat159();
            case 160:
                return motivasiSehat160();
            default:
                return "Motivasi tidak ditemukan.";
        }
    }


    // Fungsi untuk menyediakan motivasi sehat nomor 001.
    string motivasiSehat001() {
        string teks;
        teks = "Motivasi 001: perubahan kecil yang dilakukan rutin lebih baik daripada rencana besar yang tidak dimulai.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 002.
    string motivasiSehat002() {
        string teks;
        teks = "Motivasi 002: tubuh sehat membantu belajar, bekerja, dan beraktivitas dengan lebih nyaman.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 003.
    string motivasiSehat003() {
        string teks;
        teks = "Motivasi 003: tidak perlu sempurna, yang penting mulai dan konsisten.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 004.
    string motivasiSehat004() {
        string teks;
        teks = "Motivasi 004: setiap langkah kecil hari ini bisa menjadi hasil besar di masa depan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 005.
    string motivasiSehat005() {
        string teks;
        teks = "Motivasi 005: menjaga kesehatan adalah bentuk menghargai diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 006.
    string motivasiSehat006() {
        string teks;
        teks = "Motivasi 006: makan seimbang bukan berarti menyiksa diri, tetapi mengatur pilihan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 007.
    string motivasiSehat007() {
        string teks;
        teks = "Motivasi 007: olahraga ringan tetap lebih baik daripada tidak bergerak sama sekali.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 008.
    string motivasiSehat008() {
        string teks;
        teks = "Motivasi 008: progres setiap orang berbeda, jadi fokus pada diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 009.
    string motivasiSehat009() {
        string teks;
        teks = "Motivasi 009: catatan BMI membantu melihat perkembangan secara lebih objektif.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 010.
    string motivasiSehat010() {
        string teks;
        teks = "Motivasi 010: kesehatan adalah investasi yang manfaatnya terasa jangka panjang.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 011.
    string motivasiSehat011() {
        string teks;
        teks = "Motivasi 011: perubahan kecil yang dilakukan rutin lebih baik daripada rencana besar yang tidak dimulai.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 012.
    string motivasiSehat012() {
        string teks;
        teks = "Motivasi 012: tubuh sehat membantu belajar, bekerja, dan beraktivitas dengan lebih nyaman.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 013.
    string motivasiSehat013() {
        string teks;
        teks = "Motivasi 013: tidak perlu sempurna, yang penting mulai dan konsisten.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 014.
    string motivasiSehat014() {
        string teks;
        teks = "Motivasi 014: setiap langkah kecil hari ini bisa menjadi hasil besar di masa depan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 015.
    string motivasiSehat015() {
        string teks;
        teks = "Motivasi 015: menjaga kesehatan adalah bentuk menghargai diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 016.
    string motivasiSehat016() {
        string teks;
        teks = "Motivasi 016: makan seimbang bukan berarti menyiksa diri, tetapi mengatur pilihan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 017.
    string motivasiSehat017() {
        string teks;
        teks = "Motivasi 017: olahraga ringan tetap lebih baik daripada tidak bergerak sama sekali.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 018.
    string motivasiSehat018() {
        string teks;
        teks = "Motivasi 018: progres setiap orang berbeda, jadi fokus pada diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 019.
    string motivasiSehat019() {
        string teks;
        teks = "Motivasi 019: catatan BMI membantu melihat perkembangan secara lebih objektif.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 020.
    string motivasiSehat020() {
        string teks;
        teks = "Motivasi 020: kesehatan adalah investasi yang manfaatnya terasa jangka panjang.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 021.
    string motivasiSehat021() {
        string teks;
        teks = "Motivasi 021: perubahan kecil yang dilakukan rutin lebih baik daripada rencana besar yang tidak dimulai.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 022.
    string motivasiSehat022() {
        string teks;
        teks = "Motivasi 022: tubuh sehat membantu belajar, bekerja, dan beraktivitas dengan lebih nyaman.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 023.
    string motivasiSehat023() {
        string teks;
        teks = "Motivasi 023: tidak perlu sempurna, yang penting mulai dan konsisten.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 024.
    string motivasiSehat024() {
        string teks;
        teks = "Motivasi 024: setiap langkah kecil hari ini bisa menjadi hasil besar di masa depan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 025.
    string motivasiSehat025() {
        string teks;
        teks = "Motivasi 025: menjaga kesehatan adalah bentuk menghargai diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 026.
    string motivasiSehat026() {
        string teks;
        teks = "Motivasi 026: makan seimbang bukan berarti menyiksa diri, tetapi mengatur pilihan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 027.
    string motivasiSehat027() {
        string teks;
        teks = "Motivasi 027: olahraga ringan tetap lebih baik daripada tidak bergerak sama sekali.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 028.
    string motivasiSehat028() {
        string teks;
        teks = "Motivasi 028: progres setiap orang berbeda, jadi fokus pada diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 029.
    string motivasiSehat029() {
        string teks;
        teks = "Motivasi 029: catatan BMI membantu melihat perkembangan secara lebih objektif.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 030.
    string motivasiSehat030() {
        string teks;
        teks = "Motivasi 030: kesehatan adalah investasi yang manfaatnya terasa jangka panjang.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 031.
    string motivasiSehat031() {
        string teks;
        teks = "Motivasi 031: perubahan kecil yang dilakukan rutin lebih baik daripada rencana besar yang tidak dimulai.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 032.
    string motivasiSehat032() {
        string teks;
        teks = "Motivasi 032: tubuh sehat membantu belajar, bekerja, dan beraktivitas dengan lebih nyaman.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 033.
    string motivasiSehat033() {
        string teks;
        teks = "Motivasi 033: tidak perlu sempurna, yang penting mulai dan konsisten.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 034.
    string motivasiSehat034() {
        string teks;
        teks = "Motivasi 034: setiap langkah kecil hari ini bisa menjadi hasil besar di masa depan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 035.
    string motivasiSehat035() {
        string teks;
        teks = "Motivasi 035: menjaga kesehatan adalah bentuk menghargai diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 036.
    string motivasiSehat036() {
        string teks;
        teks = "Motivasi 036: makan seimbang bukan berarti menyiksa diri, tetapi mengatur pilihan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 037.
    string motivasiSehat037() {
        string teks;
        teks = "Motivasi 037: olahraga ringan tetap lebih baik daripada tidak bergerak sama sekali.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 038.
    string motivasiSehat038() {
        string teks;
        teks = "Motivasi 038: progres setiap orang berbeda, jadi fokus pada diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 039.
    string motivasiSehat039() {
        string teks;
        teks = "Motivasi 039: catatan BMI membantu melihat perkembangan secara lebih objektif.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 040.
    string motivasiSehat040() {
        string teks;
        teks = "Motivasi 040: kesehatan adalah investasi yang manfaatnya terasa jangka panjang.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 041.
    string motivasiSehat041() {
        string teks;
        teks = "Motivasi 041: perubahan kecil yang dilakukan rutin lebih baik daripada rencana besar yang tidak dimulai.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 042.
    string motivasiSehat042() {
        string teks;
        teks = "Motivasi 042: tubuh sehat membantu belajar, bekerja, dan beraktivitas dengan lebih nyaman.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 043.
    string motivasiSehat043() {
        string teks;
        teks = "Motivasi 043: tidak perlu sempurna, yang penting mulai dan konsisten.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 044.
    string motivasiSehat044() {
        string teks;
        teks = "Motivasi 044: setiap langkah kecil hari ini bisa menjadi hasil besar di masa depan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 045.
    string motivasiSehat045() {
        string teks;
        teks = "Motivasi 045: menjaga kesehatan adalah bentuk menghargai diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 046.
    string motivasiSehat046() {
        string teks;
        teks = "Motivasi 046: makan seimbang bukan berarti menyiksa diri, tetapi mengatur pilihan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 047.
    string motivasiSehat047() {
        string teks;
        teks = "Motivasi 047: olahraga ringan tetap lebih baik daripada tidak bergerak sama sekali.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 048.
    string motivasiSehat048() {
        string teks;
        teks = "Motivasi 048: progres setiap orang berbeda, jadi fokus pada diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 049.
    string motivasiSehat049() {
        string teks;
        teks = "Motivasi 049: catatan BMI membantu melihat perkembangan secara lebih objektif.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 050.
    string motivasiSehat050() {
        string teks;
        teks = "Motivasi 050: kesehatan adalah investasi yang manfaatnya terasa jangka panjang.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 051.
    string motivasiSehat051() {
        string teks;
        teks = "Motivasi 051: perubahan kecil yang dilakukan rutin lebih baik daripada rencana besar yang tidak dimulai.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 052.
    string motivasiSehat052() {
        string teks;
        teks = "Motivasi 052: tubuh sehat membantu belajar, bekerja, dan beraktivitas dengan lebih nyaman.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 053.
    string motivasiSehat053() {
        string teks;
        teks = "Motivasi 053: tidak perlu sempurna, yang penting mulai dan konsisten.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 054.
    string motivasiSehat054() {
        string teks;
        teks = "Motivasi 054: setiap langkah kecil hari ini bisa menjadi hasil besar di masa depan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 055.
    string motivasiSehat055() {
        string teks;
        teks = "Motivasi 055: menjaga kesehatan adalah bentuk menghargai diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 056.
    string motivasiSehat056() {
        string teks;
        teks = "Motivasi 056: makan seimbang bukan berarti menyiksa diri, tetapi mengatur pilihan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 057.
    string motivasiSehat057() {
        string teks;
        teks = "Motivasi 057: olahraga ringan tetap lebih baik daripada tidak bergerak sama sekali.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 058.
    string motivasiSehat058() {
        string teks;
        teks = "Motivasi 058: progres setiap orang berbeda, jadi fokus pada diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 059.
    string motivasiSehat059() {
        string teks;
        teks = "Motivasi 059: catatan BMI membantu melihat perkembangan secara lebih objektif.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 060.
    string motivasiSehat060() {
        string teks;
        teks = "Motivasi 060: kesehatan adalah investasi yang manfaatnya terasa jangka panjang.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 061.
    string motivasiSehat061() {
        string teks;
        teks = "Motivasi 061: perubahan kecil yang dilakukan rutin lebih baik daripada rencana besar yang tidak dimulai.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 062.
    string motivasiSehat062() {
        string teks;
        teks = "Motivasi 062: tubuh sehat membantu belajar, bekerja, dan beraktivitas dengan lebih nyaman.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 063.
    string motivasiSehat063() {
        string teks;
        teks = "Motivasi 063: tidak perlu sempurna, yang penting mulai dan konsisten.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 064.
    string motivasiSehat064() {
        string teks;
        teks = "Motivasi 064: setiap langkah kecil hari ini bisa menjadi hasil besar di masa depan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 065.
    string motivasiSehat065() {
        string teks;
        teks = "Motivasi 065: menjaga kesehatan adalah bentuk menghargai diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 066.
    string motivasiSehat066() {
        string teks;
        teks = "Motivasi 066: makan seimbang bukan berarti menyiksa diri, tetapi mengatur pilihan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 067.
    string motivasiSehat067() {
        string teks;
        teks = "Motivasi 067: olahraga ringan tetap lebih baik daripada tidak bergerak sama sekali.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 068.
    string motivasiSehat068() {
        string teks;
        teks = "Motivasi 068: progres setiap orang berbeda, jadi fokus pada diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 069.
    string motivasiSehat069() {
        string teks;
        teks = "Motivasi 069: catatan BMI membantu melihat perkembangan secara lebih objektif.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 070.
    string motivasiSehat070() {
        string teks;
        teks = "Motivasi 070: kesehatan adalah investasi yang manfaatnya terasa jangka panjang.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 071.
    string motivasiSehat071() {
        string teks;
        teks = "Motivasi 071: perubahan kecil yang dilakukan rutin lebih baik daripada rencana besar yang tidak dimulai.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 072.
    string motivasiSehat072() {
        string teks;
        teks = "Motivasi 072: tubuh sehat membantu belajar, bekerja, dan beraktivitas dengan lebih nyaman.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 073.
    string motivasiSehat073() {
        string teks;
        teks = "Motivasi 073: tidak perlu sempurna, yang penting mulai dan konsisten.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 074.
    string motivasiSehat074() {
        string teks;
        teks = "Motivasi 074: setiap langkah kecil hari ini bisa menjadi hasil besar di masa depan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 075.
    string motivasiSehat075() {
        string teks;
        teks = "Motivasi 075: menjaga kesehatan adalah bentuk menghargai diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 076.
    string motivasiSehat076() {
        string teks;
        teks = "Motivasi 076: makan seimbang bukan berarti menyiksa diri, tetapi mengatur pilihan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 077.
    string motivasiSehat077() {
        string teks;
        teks = "Motivasi 077: olahraga ringan tetap lebih baik daripada tidak bergerak sama sekali.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 078.
    string motivasiSehat078() {
        string teks;
        teks = "Motivasi 078: progres setiap orang berbeda, jadi fokus pada diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 079.
    string motivasiSehat079() {
        string teks;
        teks = "Motivasi 079: catatan BMI membantu melihat perkembangan secara lebih objektif.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 080.
    string motivasiSehat080() {
        string teks;
        teks = "Motivasi 080: kesehatan adalah investasi yang manfaatnya terasa jangka panjang.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 081.
    string motivasiSehat081() {
        string teks;
        teks = "Motivasi 081: perubahan kecil yang dilakukan rutin lebih baik daripada rencana besar yang tidak dimulai.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 082.
    string motivasiSehat082() {
        string teks;
        teks = "Motivasi 082: tubuh sehat membantu belajar, bekerja, dan beraktivitas dengan lebih nyaman.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 083.
    string motivasiSehat083() {
        string teks;
        teks = "Motivasi 083: tidak perlu sempurna, yang penting mulai dan konsisten.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 084.
    string motivasiSehat084() {
        string teks;
        teks = "Motivasi 084: setiap langkah kecil hari ini bisa menjadi hasil besar di masa depan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 085.
    string motivasiSehat085() {
        string teks;
        teks = "Motivasi 085: menjaga kesehatan adalah bentuk menghargai diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 086.
    string motivasiSehat086() {
        string teks;
        teks = "Motivasi 086: makan seimbang bukan berarti menyiksa diri, tetapi mengatur pilihan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 087.
    string motivasiSehat087() {
        string teks;
        teks = "Motivasi 087: olahraga ringan tetap lebih baik daripada tidak bergerak sama sekali.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 088.
    string motivasiSehat088() {
        string teks;
        teks = "Motivasi 088: progres setiap orang berbeda, jadi fokus pada diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 089.
    string motivasiSehat089() {
        string teks;
        teks = "Motivasi 089: catatan BMI membantu melihat perkembangan secara lebih objektif.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 090.
    string motivasiSehat090() {
        string teks;
        teks = "Motivasi 090: kesehatan adalah investasi yang manfaatnya terasa jangka panjang.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 091.
    string motivasiSehat091() {
        string teks;
        teks = "Motivasi 091: perubahan kecil yang dilakukan rutin lebih baik daripada rencana besar yang tidak dimulai.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 092.
    string motivasiSehat092() {
        string teks;
        teks = "Motivasi 092: tubuh sehat membantu belajar, bekerja, dan beraktivitas dengan lebih nyaman.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 093.
    string motivasiSehat093() {
        string teks;
        teks = "Motivasi 093: tidak perlu sempurna, yang penting mulai dan konsisten.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 094.
    string motivasiSehat094() {
        string teks;
        teks = "Motivasi 094: setiap langkah kecil hari ini bisa menjadi hasil besar di masa depan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 095.
    string motivasiSehat095() {
        string teks;
        teks = "Motivasi 095: menjaga kesehatan adalah bentuk menghargai diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 096.
    string motivasiSehat096() {
        string teks;
        teks = "Motivasi 096: makan seimbang bukan berarti menyiksa diri, tetapi mengatur pilihan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 097.
    string motivasiSehat097() {
        string teks;
        teks = "Motivasi 097: olahraga ringan tetap lebih baik daripada tidak bergerak sama sekali.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 098.
    string motivasiSehat098() {
        string teks;
        teks = "Motivasi 098: progres setiap orang berbeda, jadi fokus pada diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 099.
    string motivasiSehat099() {
        string teks;
        teks = "Motivasi 099: catatan BMI membantu melihat perkembangan secara lebih objektif.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 100.
    string motivasiSehat100() {
        string teks;
        teks = "Motivasi 100: kesehatan adalah investasi yang manfaatnya terasa jangka panjang.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 101.
    string motivasiSehat101() {
        string teks;
        teks = "Motivasi 101: perubahan kecil yang dilakukan rutin lebih baik daripada rencana besar yang tidak dimulai.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 102.
    string motivasiSehat102() {
        string teks;
        teks = "Motivasi 102: tubuh sehat membantu belajar, bekerja, dan beraktivitas dengan lebih nyaman.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 103.
    string motivasiSehat103() {
        string teks;
        teks = "Motivasi 103: tidak perlu sempurna, yang penting mulai dan konsisten.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 104.
    string motivasiSehat104() {
        string teks;
        teks = "Motivasi 104: setiap langkah kecil hari ini bisa menjadi hasil besar di masa depan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 105.
    string motivasiSehat105() {
        string teks;
        teks = "Motivasi 105: menjaga kesehatan adalah bentuk menghargai diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 106.
    string motivasiSehat106() {
        string teks;
        teks = "Motivasi 106: makan seimbang bukan berarti menyiksa diri, tetapi mengatur pilihan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 107.
    string motivasiSehat107() {
        string teks;
        teks = "Motivasi 107: olahraga ringan tetap lebih baik daripada tidak bergerak sama sekali.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 108.
    string motivasiSehat108() {
        string teks;
        teks = "Motivasi 108: progres setiap orang berbeda, jadi fokus pada diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 109.
    string motivasiSehat109() {
        string teks;
        teks = "Motivasi 109: catatan BMI membantu melihat perkembangan secara lebih objektif.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 110.
    string motivasiSehat110() {
        string teks;
        teks = "Motivasi 110: kesehatan adalah investasi yang manfaatnya terasa jangka panjang.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 111.
    string motivasiSehat111() {
        string teks;
        teks = "Motivasi 111: perubahan kecil yang dilakukan rutin lebih baik daripada rencana besar yang tidak dimulai.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 112.
    string motivasiSehat112() {
        string teks;
        teks = "Motivasi 112: tubuh sehat membantu belajar, bekerja, dan beraktivitas dengan lebih nyaman.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 113.
    string motivasiSehat113() {
        string teks;
        teks = "Motivasi 113: tidak perlu sempurna, yang penting mulai dan konsisten.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 114.
    string motivasiSehat114() {
        string teks;
        teks = "Motivasi 114: setiap langkah kecil hari ini bisa menjadi hasil besar di masa depan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 115.
    string motivasiSehat115() {
        string teks;
        teks = "Motivasi 115: menjaga kesehatan adalah bentuk menghargai diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 116.
    string motivasiSehat116() {
        string teks;
        teks = "Motivasi 116: makan seimbang bukan berarti menyiksa diri, tetapi mengatur pilihan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 117.
    string motivasiSehat117() {
        string teks;
        teks = "Motivasi 117: olahraga ringan tetap lebih baik daripada tidak bergerak sama sekali.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 118.
    string motivasiSehat118() {
        string teks;
        teks = "Motivasi 118: progres setiap orang berbeda, jadi fokus pada diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 119.
    string motivasiSehat119() {
        string teks;
        teks = "Motivasi 119: catatan BMI membantu melihat perkembangan secara lebih objektif.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 120.
    string motivasiSehat120() {
        string teks;
        teks = "Motivasi 120: kesehatan adalah investasi yang manfaatnya terasa jangka panjang.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 121.
    string motivasiSehat121() {
        string teks;
        teks = "Motivasi 121: perubahan kecil yang dilakukan rutin lebih baik daripada rencana besar yang tidak dimulai.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 122.
    string motivasiSehat122() {
        string teks;
        teks = "Motivasi 122: tubuh sehat membantu belajar, bekerja, dan beraktivitas dengan lebih nyaman.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 123.
    string motivasiSehat123() {
        string teks;
        teks = "Motivasi 123: tidak perlu sempurna, yang penting mulai dan konsisten.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 124.
    string motivasiSehat124() {
        string teks;
        teks = "Motivasi 124: setiap langkah kecil hari ini bisa menjadi hasil besar di masa depan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 125.
    string motivasiSehat125() {
        string teks;
        teks = "Motivasi 125: menjaga kesehatan adalah bentuk menghargai diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 126.
    string motivasiSehat126() {
        string teks;
        teks = "Motivasi 126: makan seimbang bukan berarti menyiksa diri, tetapi mengatur pilihan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 127.
    string motivasiSehat127() {
        string teks;
        teks = "Motivasi 127: olahraga ringan tetap lebih baik daripada tidak bergerak sama sekali.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 128.
    string motivasiSehat128() {
        string teks;
        teks = "Motivasi 128: progres setiap orang berbeda, jadi fokus pada diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 129.
    string motivasiSehat129() {
        string teks;
        teks = "Motivasi 129: catatan BMI membantu melihat perkembangan secara lebih objektif.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 130.
    string motivasiSehat130() {
        string teks;
        teks = "Motivasi 130: kesehatan adalah investasi yang manfaatnya terasa jangka panjang.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 131.
    string motivasiSehat131() {
        string teks;
        teks = "Motivasi 131: perubahan kecil yang dilakukan rutin lebih baik daripada rencana besar yang tidak dimulai.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 132.
    string motivasiSehat132() {
        string teks;
        teks = "Motivasi 132: tubuh sehat membantu belajar, bekerja, dan beraktivitas dengan lebih nyaman.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 133.
    string motivasiSehat133() {
        string teks;
        teks = "Motivasi 133: tidak perlu sempurna, yang penting mulai dan konsisten.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 134.
    string motivasiSehat134() {
        string teks;
        teks = "Motivasi 134: setiap langkah kecil hari ini bisa menjadi hasil besar di masa depan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 135.
    string motivasiSehat135() {
        string teks;
        teks = "Motivasi 135: menjaga kesehatan adalah bentuk menghargai diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 136.
    string motivasiSehat136() {
        string teks;
        teks = "Motivasi 136: makan seimbang bukan berarti menyiksa diri, tetapi mengatur pilihan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 137.
    string motivasiSehat137() {
        string teks;
        teks = "Motivasi 137: olahraga ringan tetap lebih baik daripada tidak bergerak sama sekali.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 138.
    string motivasiSehat138() {
        string teks;
        teks = "Motivasi 138: progres setiap orang berbeda, jadi fokus pada diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 139.
    string motivasiSehat139() {
        string teks;
        teks = "Motivasi 139: catatan BMI membantu melihat perkembangan secara lebih objektif.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 140.
    string motivasiSehat140() {
        string teks;
        teks = "Motivasi 140: kesehatan adalah investasi yang manfaatnya terasa jangka panjang.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 141.
    string motivasiSehat141() {
        string teks;
        teks = "Motivasi 141: perubahan kecil yang dilakukan rutin lebih baik daripada rencana besar yang tidak dimulai.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 142.
    string motivasiSehat142() {
        string teks;
        teks = "Motivasi 142: tubuh sehat membantu belajar, bekerja, dan beraktivitas dengan lebih nyaman.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 143.
    string motivasiSehat143() {
        string teks;
        teks = "Motivasi 143: tidak perlu sempurna, yang penting mulai dan konsisten.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 144.
    string motivasiSehat144() {
        string teks;
        teks = "Motivasi 144: setiap langkah kecil hari ini bisa menjadi hasil besar di masa depan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 145.
    string motivasiSehat145() {
        string teks;
        teks = "Motivasi 145: menjaga kesehatan adalah bentuk menghargai diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 146.
    string motivasiSehat146() {
        string teks;
        teks = "Motivasi 146: makan seimbang bukan berarti menyiksa diri, tetapi mengatur pilihan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 147.
    string motivasiSehat147() {
        string teks;
        teks = "Motivasi 147: olahraga ringan tetap lebih baik daripada tidak bergerak sama sekali.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 148.
    string motivasiSehat148() {
        string teks;
        teks = "Motivasi 148: progres setiap orang berbeda, jadi fokus pada diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 149.
    string motivasiSehat149() {
        string teks;
        teks = "Motivasi 149: catatan BMI membantu melihat perkembangan secara lebih objektif.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 150.
    string motivasiSehat150() {
        string teks;
        teks = "Motivasi 150: kesehatan adalah investasi yang manfaatnya terasa jangka panjang.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 151.
    string motivasiSehat151() {
        string teks;
        teks = "Motivasi 151: perubahan kecil yang dilakukan rutin lebih baik daripada rencana besar yang tidak dimulai.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 152.
    string motivasiSehat152() {
        string teks;
        teks = "Motivasi 152: tubuh sehat membantu belajar, bekerja, dan beraktivitas dengan lebih nyaman.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 153.
    string motivasiSehat153() {
        string teks;
        teks = "Motivasi 153: tidak perlu sempurna, yang penting mulai dan konsisten.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 154.
    string motivasiSehat154() {
        string teks;
        teks = "Motivasi 154: setiap langkah kecil hari ini bisa menjadi hasil besar di masa depan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 155.
    string motivasiSehat155() {
        string teks;
        teks = "Motivasi 155: menjaga kesehatan adalah bentuk menghargai diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 156.
    string motivasiSehat156() {
        string teks;
        teks = "Motivasi 156: makan seimbang bukan berarti menyiksa diri, tetapi mengatur pilihan.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 157.
    string motivasiSehat157() {
        string teks;
        teks = "Motivasi 157: olahraga ringan tetap lebih baik daripada tidak bergerak sama sekali.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 158.
    string motivasiSehat158() {
        string teks;
        teks = "Motivasi 158: progres setiap orang berbeda, jadi fokus pada diri sendiri.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 159.
    string motivasiSehat159() {
        string teks;
        teks = "Motivasi 159: catatan BMI membantu melihat perkembangan secara lebih objektif.";
        return teks;
    }

    // Fungsi untuk menyediakan motivasi sehat nomor 160.
    string motivasiSehat160() {
        string teks;
        teks = "Motivasi 160: kesehatan adalah investasi yang manfaatnya terasa jangka panjang.";
        return teks;
    }


    // Fungsi untuk menampilkan contoh menu makan sehat.
    void menuMakanSehat() {
        int nomor;
        cout << "\nAda 140 contoh menu makan sehat di dalam aplikasi.\n";
        nomor = inputAngka("Masukkan nomor menu 1-140: ", 1, 140);
        cout << ambilMenuMakanSehat(nomor) << "\n";
    }

    // Fungsi untuk mengambil contoh menu makan sehat berdasarkan nomor.
    string ambilMenuMakanSehat(int nomor) {
        switch (nomor) {

            case 1:
                return menuMakanSehat001();
            case 2:
                return menuMakanSehat002();
            case 3:
                return menuMakanSehat003();
            case 4:
                return menuMakanSehat004();
            case 5:
                return menuMakanSehat005();
            case 6:
                return menuMakanSehat006();
            case 7:
                return menuMakanSehat007();
            case 8:
                return menuMakanSehat008();
            case 9:
                return menuMakanSehat009();
            case 10:
                return menuMakanSehat010();
            case 11:
                return menuMakanSehat011();
            case 12:
                return menuMakanSehat012();
            case 13:
                return menuMakanSehat013();
            case 14:
                return menuMakanSehat014();
            case 15:
                return menuMakanSehat015();
            case 16:
                return menuMakanSehat016();
            case 17:
                return menuMakanSehat017();
            case 18:
                return menuMakanSehat018();
            case 19:
                return menuMakanSehat019();
            case 20:
                return menuMakanSehat020();
            case 21:
                return menuMakanSehat021();
            case 22:
                return menuMakanSehat022();
            case 23:
                return menuMakanSehat023();
            case 24:
                return menuMakanSehat024();
            case 25:
                return menuMakanSehat025();
            case 26:
                return menuMakanSehat026();
            case 27:
                return menuMakanSehat027();
            case 28:
                return menuMakanSehat028();
            case 29:
                return menuMakanSehat029();
            case 30:
                return menuMakanSehat030();
            case 31:
                return menuMakanSehat031();
            case 32:
                return menuMakanSehat032();
            case 33:
                return menuMakanSehat033();
            case 34:
                return menuMakanSehat034();
            case 35:
                return menuMakanSehat035();
            case 36:
                return menuMakanSehat036();
            case 37:
                return menuMakanSehat037();
            case 38:
                return menuMakanSehat038();
            case 39:
                return menuMakanSehat039();
            case 40:
                return menuMakanSehat040();
            case 41:
                return menuMakanSehat041();
            case 42:
                return menuMakanSehat042();
            case 43:
                return menuMakanSehat043();
            case 44:
                return menuMakanSehat044();
            case 45:
                return menuMakanSehat045();
            case 46:
                return menuMakanSehat046();
            case 47:
                return menuMakanSehat047();
            case 48:
                return menuMakanSehat048();
            case 49:
                return menuMakanSehat049();
            case 50:
                return menuMakanSehat050();
            case 51:
                return menuMakanSehat051();
            case 52:
                return menuMakanSehat052();
            case 53:
                return menuMakanSehat053();
            case 54:
                return menuMakanSehat054();
            case 55:
                return menuMakanSehat055();
            case 56:
                return menuMakanSehat056();
            case 57:
                return menuMakanSehat057();
            case 58:
                return menuMakanSehat058();
            case 59:
                return menuMakanSehat059();
            case 60:
                return menuMakanSehat060();
            case 61:
                return menuMakanSehat061();
            case 62:
                return menuMakanSehat062();
            case 63:
                return menuMakanSehat063();
            case 64:
                return menuMakanSehat064();
            case 65:
                return menuMakanSehat065();
            case 66:
                return menuMakanSehat066();
            case 67:
                return menuMakanSehat067();
            case 68:
                return menuMakanSehat068();
            case 69:
                return menuMakanSehat069();
            case 70:
                return menuMakanSehat070();
            case 71:
                return menuMakanSehat071();
            case 72:
                return menuMakanSehat072();
            case 73:
                return menuMakanSehat073();
            case 74:
                return menuMakanSehat074();
            case 75:
                return menuMakanSehat075();
            case 76:
                return menuMakanSehat076();
            case 77:
                return menuMakanSehat077();
            case 78:
                return menuMakanSehat078();
            case 79:
                return menuMakanSehat079();
            case 80:
                return menuMakanSehat080();
            case 81:
                return menuMakanSehat081();
            case 82:
                return menuMakanSehat082();
            case 83:
                return menuMakanSehat083();
            case 84:
                return menuMakanSehat084();
            case 85:
                return menuMakanSehat085();
            case 86:
                return menuMakanSehat086();
            case 87:
                return menuMakanSehat087();
            case 88:
                return menuMakanSehat088();
            case 89:
                return menuMakanSehat089();
            case 90:
                return menuMakanSehat090();
            case 91:
                return menuMakanSehat091();
            case 92:
                return menuMakanSehat092();
            case 93:
                return menuMakanSehat093();
            case 94:
                return menuMakanSehat094();
            case 95:
                return menuMakanSehat095();
            case 96:
                return menuMakanSehat096();
            case 97:
                return menuMakanSehat097();
            case 98:
                return menuMakanSehat098();
            case 99:
                return menuMakanSehat099();
            case 100:
                return menuMakanSehat100();
            case 101:
                return menuMakanSehat101();
            case 102:
                return menuMakanSehat102();
            case 103:
                return menuMakanSehat103();
            case 104:
                return menuMakanSehat104();
            case 105:
                return menuMakanSehat105();
            case 106:
                return menuMakanSehat106();
            case 107:
                return menuMakanSehat107();
            case 108:
                return menuMakanSehat108();
            case 109:
                return menuMakanSehat109();
            case 110:
                return menuMakanSehat110();
            case 111:
                return menuMakanSehat111();
            case 112:
                return menuMakanSehat112();
            case 113:
                return menuMakanSehat113();
            case 114:
                return menuMakanSehat114();
            case 115:
                return menuMakanSehat115();
            case 116:
                return menuMakanSehat116();
            case 117:
                return menuMakanSehat117();
            case 118:
                return menuMakanSehat118();
            case 119:
                return menuMakanSehat119();
            case 120:
                return menuMakanSehat120();
            case 121:
                return menuMakanSehat121();
            case 122:
                return menuMakanSehat122();
            case 123:
                return menuMakanSehat123();
            case 124:
                return menuMakanSehat124();
            case 125:
                return menuMakanSehat125();
            case 126:
                return menuMakanSehat126();
            case 127:
                return menuMakanSehat127();
            case 128:
                return menuMakanSehat128();
            case 129:
                return menuMakanSehat129();
            case 130:
                return menuMakanSehat130();
            case 131:
                return menuMakanSehat131();
            case 132:
                return menuMakanSehat132();
            case 133:
                return menuMakanSehat133();
            case 134:
                return menuMakanSehat134();
            case 135:
                return menuMakanSehat135();
            case 136:
                return menuMakanSehat136();
            case 137:
                return menuMakanSehat137();
            case 138:
                return menuMakanSehat138();
            case 139:
                return menuMakanSehat139();
            case 140:
                return menuMakanSehat140();
            default:
                return "Menu makan tidak ditemukan.";
        }
    }


    // Fungsi untuk menyediakan contoh menu makan sehat nomor 001.
    string menuMakanSehat001() {
        string teks;
        teks = "Menu 001: nasi, ayam panggang, sayur bening, tempe, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 002.
    string menuMakanSehat002() {
        string teks;
        teks = "Menu 002: oatmeal, pisang, telur rebus, dan susu rendah gula.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 003.
    string menuMakanSehat003() {
        string teks;
        teks = "Menu 003: nasi merah, ikan kukus, tumis kangkung, tahu, dan buah pepaya.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 004.
    string menuMakanSehat004() {
        string teks;
        teks = "Menu 004: kentang rebus, dada ayam, salad sayur, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 005.
    string menuMakanSehat005() {
        string teks;
        teks = "Menu 005: roti gandum, telur dadar, tomat, timun, dan buah apel.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 006.
    string menuMakanSehat006() {
        string teks;
        teks = "Menu 006: bubur kacang hijau rendah gula dan buah potong.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 007.
    string menuMakanSehat007() {
        string teks;
        teks = "Menu 007: nasi, telur, capcay, tahu, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 008.
    string menuMakanSehat008() {
        string teks;
        teks = "Menu 008: ubi rebus, ikan, sayur bayam, dan buah jeruk.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 009.
    string menuMakanSehat009() {
        string teks;
        teks = "Menu 009: nasi merah, ayam suwir, brokoli, tempe, dan buah melon.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 010.
    string menuMakanSehat010() {
        string teks;
        teks = "Menu 010: mie rebus homemade dengan telur dan banyak sayur.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 011.
    string menuMakanSehat011() {
        string teks;
        teks = "Menu 011: nasi, ayam panggang, sayur bening, tempe, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 012.
    string menuMakanSehat012() {
        string teks;
        teks = "Menu 012: oatmeal, pisang, telur rebus, dan susu rendah gula.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 013.
    string menuMakanSehat013() {
        string teks;
        teks = "Menu 013: nasi merah, ikan kukus, tumis kangkung, tahu, dan buah pepaya.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 014.
    string menuMakanSehat014() {
        string teks;
        teks = "Menu 014: kentang rebus, dada ayam, salad sayur, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 015.
    string menuMakanSehat015() {
        string teks;
        teks = "Menu 015: roti gandum, telur dadar, tomat, timun, dan buah apel.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 016.
    string menuMakanSehat016() {
        string teks;
        teks = "Menu 016: bubur kacang hijau rendah gula dan buah potong.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 017.
    string menuMakanSehat017() {
        string teks;
        teks = "Menu 017: nasi, telur, capcay, tahu, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 018.
    string menuMakanSehat018() {
        string teks;
        teks = "Menu 018: ubi rebus, ikan, sayur bayam, dan buah jeruk.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 019.
    string menuMakanSehat019() {
        string teks;
        teks = "Menu 019: nasi merah, ayam suwir, brokoli, tempe, dan buah melon.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 020.
    string menuMakanSehat020() {
        string teks;
        teks = "Menu 020: mie rebus homemade dengan telur dan banyak sayur.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 021.
    string menuMakanSehat021() {
        string teks;
        teks = "Menu 021: nasi, ayam panggang, sayur bening, tempe, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 022.
    string menuMakanSehat022() {
        string teks;
        teks = "Menu 022: oatmeal, pisang, telur rebus, dan susu rendah gula.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 023.
    string menuMakanSehat023() {
        string teks;
        teks = "Menu 023: nasi merah, ikan kukus, tumis kangkung, tahu, dan buah pepaya.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 024.
    string menuMakanSehat024() {
        string teks;
        teks = "Menu 024: kentang rebus, dada ayam, salad sayur, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 025.
    string menuMakanSehat025() {
        string teks;
        teks = "Menu 025: roti gandum, telur dadar, tomat, timun, dan buah apel.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 026.
    string menuMakanSehat026() {
        string teks;
        teks = "Menu 026: bubur kacang hijau rendah gula dan buah potong.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 027.
    string menuMakanSehat027() {
        string teks;
        teks = "Menu 027: nasi, telur, capcay, tahu, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 028.
    string menuMakanSehat028() {
        string teks;
        teks = "Menu 028: ubi rebus, ikan, sayur bayam, dan buah jeruk.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 029.
    string menuMakanSehat029() {
        string teks;
        teks = "Menu 029: nasi merah, ayam suwir, brokoli, tempe, dan buah melon.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 030.
    string menuMakanSehat030() {
        string teks;
        teks = "Menu 030: mie rebus homemade dengan telur dan banyak sayur.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 031.
    string menuMakanSehat031() {
        string teks;
        teks = "Menu 031: nasi, ayam panggang, sayur bening, tempe, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 032.
    string menuMakanSehat032() {
        string teks;
        teks = "Menu 032: oatmeal, pisang, telur rebus, dan susu rendah gula.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 033.
    string menuMakanSehat033() {
        string teks;
        teks = "Menu 033: nasi merah, ikan kukus, tumis kangkung, tahu, dan buah pepaya.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 034.
    string menuMakanSehat034() {
        string teks;
        teks = "Menu 034: kentang rebus, dada ayam, salad sayur, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 035.
    string menuMakanSehat035() {
        string teks;
        teks = "Menu 035: roti gandum, telur dadar, tomat, timun, dan buah apel.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 036.
    string menuMakanSehat036() {
        string teks;
        teks = "Menu 036: bubur kacang hijau rendah gula dan buah potong.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 037.
    string menuMakanSehat037() {
        string teks;
        teks = "Menu 037: nasi, telur, capcay, tahu, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 038.
    string menuMakanSehat038() {
        string teks;
        teks = "Menu 038: ubi rebus, ikan, sayur bayam, dan buah jeruk.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 039.
    string menuMakanSehat039() {
        string teks;
        teks = "Menu 039: nasi merah, ayam suwir, brokoli, tempe, dan buah melon.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 040.
    string menuMakanSehat040() {
        string teks;
        teks = "Menu 040: mie rebus homemade dengan telur dan banyak sayur.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 041.
    string menuMakanSehat041() {
        string teks;
        teks = "Menu 041: nasi, ayam panggang, sayur bening, tempe, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 042.
    string menuMakanSehat042() {
        string teks;
        teks = "Menu 042: oatmeal, pisang, telur rebus, dan susu rendah gula.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 043.
    string menuMakanSehat043() {
        string teks;
        teks = "Menu 043: nasi merah, ikan kukus, tumis kangkung, tahu, dan buah pepaya.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 044.
    string menuMakanSehat044() {
        string teks;
        teks = "Menu 044: kentang rebus, dada ayam, salad sayur, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 045.
    string menuMakanSehat045() {
        string teks;
        teks = "Menu 045: roti gandum, telur dadar, tomat, timun, dan buah apel.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 046.
    string menuMakanSehat046() {
        string teks;
        teks = "Menu 046: bubur kacang hijau rendah gula dan buah potong.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 047.
    string menuMakanSehat047() {
        string teks;
        teks = "Menu 047: nasi, telur, capcay, tahu, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 048.
    string menuMakanSehat048() {
        string teks;
        teks = "Menu 048: ubi rebus, ikan, sayur bayam, dan buah jeruk.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 049.
    string menuMakanSehat049() {
        string teks;
        teks = "Menu 049: nasi merah, ayam suwir, brokoli, tempe, dan buah melon.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 050.
    string menuMakanSehat050() {
        string teks;
        teks = "Menu 050: mie rebus homemade dengan telur dan banyak sayur.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 051.
    string menuMakanSehat051() {
        string teks;
        teks = "Menu 051: nasi, ayam panggang, sayur bening, tempe, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 052.
    string menuMakanSehat052() {
        string teks;
        teks = "Menu 052: oatmeal, pisang, telur rebus, dan susu rendah gula.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 053.
    string menuMakanSehat053() {
        string teks;
        teks = "Menu 053: nasi merah, ikan kukus, tumis kangkung, tahu, dan buah pepaya.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 054.
    string menuMakanSehat054() {
        string teks;
        teks = "Menu 054: kentang rebus, dada ayam, salad sayur, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 055.
    string menuMakanSehat055() {
        string teks;
        teks = "Menu 055: roti gandum, telur dadar, tomat, timun, dan buah apel.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 056.
    string menuMakanSehat056() {
        string teks;
        teks = "Menu 056: bubur kacang hijau rendah gula dan buah potong.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 057.
    string menuMakanSehat057() {
        string teks;
        teks = "Menu 057: nasi, telur, capcay, tahu, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 058.
    string menuMakanSehat058() {
        string teks;
        teks = "Menu 058: ubi rebus, ikan, sayur bayam, dan buah jeruk.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 059.
    string menuMakanSehat059() {
        string teks;
        teks = "Menu 059: nasi merah, ayam suwir, brokoli, tempe, dan buah melon.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 060.
    string menuMakanSehat060() {
        string teks;
        teks = "Menu 060: mie rebus homemade dengan telur dan banyak sayur.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 061.
    string menuMakanSehat061() {
        string teks;
        teks = "Menu 061: nasi, ayam panggang, sayur bening, tempe, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 062.
    string menuMakanSehat062() {
        string teks;
        teks = "Menu 062: oatmeal, pisang, telur rebus, dan susu rendah gula.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 063.
    string menuMakanSehat063() {
        string teks;
        teks = "Menu 063: nasi merah, ikan kukus, tumis kangkung, tahu, dan buah pepaya.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 064.
    string menuMakanSehat064() {
        string teks;
        teks = "Menu 064: kentang rebus, dada ayam, salad sayur, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 065.
    string menuMakanSehat065() {
        string teks;
        teks = "Menu 065: roti gandum, telur dadar, tomat, timun, dan buah apel.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 066.
    string menuMakanSehat066() {
        string teks;
        teks = "Menu 066: bubur kacang hijau rendah gula dan buah potong.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 067.
    string menuMakanSehat067() {
        string teks;
        teks = "Menu 067: nasi, telur, capcay, tahu, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 068.
    string menuMakanSehat068() {
        string teks;
        teks = "Menu 068: ubi rebus, ikan, sayur bayam, dan buah jeruk.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 069.
    string menuMakanSehat069() {
        string teks;
        teks = "Menu 069: nasi merah, ayam suwir, brokoli, tempe, dan buah melon.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 070.
    string menuMakanSehat070() {
        string teks;
        teks = "Menu 070: mie rebus homemade dengan telur dan banyak sayur.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 071.
    string menuMakanSehat071() {
        string teks;
        teks = "Menu 071: nasi, ayam panggang, sayur bening, tempe, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 072.
    string menuMakanSehat072() {
        string teks;
        teks = "Menu 072: oatmeal, pisang, telur rebus, dan susu rendah gula.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 073.
    string menuMakanSehat073() {
        string teks;
        teks = "Menu 073: nasi merah, ikan kukus, tumis kangkung, tahu, dan buah pepaya.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 074.
    string menuMakanSehat074() {
        string teks;
        teks = "Menu 074: kentang rebus, dada ayam, salad sayur, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 075.
    string menuMakanSehat075() {
        string teks;
        teks = "Menu 075: roti gandum, telur dadar, tomat, timun, dan buah apel.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 076.
    string menuMakanSehat076() {
        string teks;
        teks = "Menu 076: bubur kacang hijau rendah gula dan buah potong.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 077.
    string menuMakanSehat077() {
        string teks;
        teks = "Menu 077: nasi, telur, capcay, tahu, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 078.
    string menuMakanSehat078() {
        string teks;
        teks = "Menu 078: ubi rebus, ikan, sayur bayam, dan buah jeruk.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 079.
    string menuMakanSehat079() {
        string teks;
        teks = "Menu 079: nasi merah, ayam suwir, brokoli, tempe, dan buah melon.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 080.
    string menuMakanSehat080() {
        string teks;
        teks = "Menu 080: mie rebus homemade dengan telur dan banyak sayur.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 081.
    string menuMakanSehat081() {
        string teks;
        teks = "Menu 081: nasi, ayam panggang, sayur bening, tempe, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 082.
    string menuMakanSehat082() {
        string teks;
        teks = "Menu 082: oatmeal, pisang, telur rebus, dan susu rendah gula.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 083.
    string menuMakanSehat083() {
        string teks;
        teks = "Menu 083: nasi merah, ikan kukus, tumis kangkung, tahu, dan buah pepaya.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 084.
    string menuMakanSehat084() {
        string teks;
        teks = "Menu 084: kentang rebus, dada ayam, salad sayur, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 085.
    string menuMakanSehat085() {
        string teks;
        teks = "Menu 085: roti gandum, telur dadar, tomat, timun, dan buah apel.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 086.
    string menuMakanSehat086() {
        string teks;
        teks = "Menu 086: bubur kacang hijau rendah gula dan buah potong.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 087.
    string menuMakanSehat087() {
        string teks;
        teks = "Menu 087: nasi, telur, capcay, tahu, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 088.
    string menuMakanSehat088() {
        string teks;
        teks = "Menu 088: ubi rebus, ikan, sayur bayam, dan buah jeruk.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 089.
    string menuMakanSehat089() {
        string teks;
        teks = "Menu 089: nasi merah, ayam suwir, brokoli, tempe, dan buah melon.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 090.
    string menuMakanSehat090() {
        string teks;
        teks = "Menu 090: mie rebus homemade dengan telur dan banyak sayur.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 091.
    string menuMakanSehat091() {
        string teks;
        teks = "Menu 091: nasi, ayam panggang, sayur bening, tempe, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 092.
    string menuMakanSehat092() {
        string teks;
        teks = "Menu 092: oatmeal, pisang, telur rebus, dan susu rendah gula.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 093.
    string menuMakanSehat093() {
        string teks;
        teks = "Menu 093: nasi merah, ikan kukus, tumis kangkung, tahu, dan buah pepaya.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 094.
    string menuMakanSehat094() {
        string teks;
        teks = "Menu 094: kentang rebus, dada ayam, salad sayur, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 095.
    string menuMakanSehat095() {
        string teks;
        teks = "Menu 095: roti gandum, telur dadar, tomat, timun, dan buah apel.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 096.
    string menuMakanSehat096() {
        string teks;
        teks = "Menu 096: bubur kacang hijau rendah gula dan buah potong.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 097.
    string menuMakanSehat097() {
        string teks;
        teks = "Menu 097: nasi, telur, capcay, tahu, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 098.
    string menuMakanSehat098() {
        string teks;
        teks = "Menu 098: ubi rebus, ikan, sayur bayam, dan buah jeruk.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 099.
    string menuMakanSehat099() {
        string teks;
        teks = "Menu 099: nasi merah, ayam suwir, brokoli, tempe, dan buah melon.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 100.
    string menuMakanSehat100() {
        string teks;
        teks = "Menu 100: mie rebus homemade dengan telur dan banyak sayur.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 101.
    string menuMakanSehat101() {
        string teks;
        teks = "Menu 101: nasi, ayam panggang, sayur bening, tempe, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 102.
    string menuMakanSehat102() {
        string teks;
        teks = "Menu 102: oatmeal, pisang, telur rebus, dan susu rendah gula.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 103.
    string menuMakanSehat103() {
        string teks;
        teks = "Menu 103: nasi merah, ikan kukus, tumis kangkung, tahu, dan buah pepaya.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 104.
    string menuMakanSehat104() {
        string teks;
        teks = "Menu 104: kentang rebus, dada ayam, salad sayur, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 105.
    string menuMakanSehat105() {
        string teks;
        teks = "Menu 105: roti gandum, telur dadar, tomat, timun, dan buah apel.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 106.
    string menuMakanSehat106() {
        string teks;
        teks = "Menu 106: bubur kacang hijau rendah gula dan buah potong.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 107.
    string menuMakanSehat107() {
        string teks;
        teks = "Menu 107: nasi, telur, capcay, tahu, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 108.
    string menuMakanSehat108() {
        string teks;
        teks = "Menu 108: ubi rebus, ikan, sayur bayam, dan buah jeruk.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 109.
    string menuMakanSehat109() {
        string teks;
        teks = "Menu 109: nasi merah, ayam suwir, brokoli, tempe, dan buah melon.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 110.
    string menuMakanSehat110() {
        string teks;
        teks = "Menu 110: mie rebus homemade dengan telur dan banyak sayur.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 111.
    string menuMakanSehat111() {
        string teks;
        teks = "Menu 111: nasi, ayam panggang, sayur bening, tempe, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 112.
    string menuMakanSehat112() {
        string teks;
        teks = "Menu 112: oatmeal, pisang, telur rebus, dan susu rendah gula.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 113.
    string menuMakanSehat113() {
        string teks;
        teks = "Menu 113: nasi merah, ikan kukus, tumis kangkung, tahu, dan buah pepaya.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 114.
    string menuMakanSehat114() {
        string teks;
        teks = "Menu 114: kentang rebus, dada ayam, salad sayur, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 115.
    string menuMakanSehat115() {
        string teks;
        teks = "Menu 115: roti gandum, telur dadar, tomat, timun, dan buah apel.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 116.
    string menuMakanSehat116() {
        string teks;
        teks = "Menu 116: bubur kacang hijau rendah gula dan buah potong.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 117.
    string menuMakanSehat117() {
        string teks;
        teks = "Menu 117: nasi, telur, capcay, tahu, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 118.
    string menuMakanSehat118() {
        string teks;
        teks = "Menu 118: ubi rebus, ikan, sayur bayam, dan buah jeruk.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 119.
    string menuMakanSehat119() {
        string teks;
        teks = "Menu 119: nasi merah, ayam suwir, brokoli, tempe, dan buah melon.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 120.
    string menuMakanSehat120() {
        string teks;
        teks = "Menu 120: mie rebus homemade dengan telur dan banyak sayur.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 121.
    string menuMakanSehat121() {
        string teks;
        teks = "Menu 121: nasi, ayam panggang, sayur bening, tempe, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 122.
    string menuMakanSehat122() {
        string teks;
        teks = "Menu 122: oatmeal, pisang, telur rebus, dan susu rendah gula.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 123.
    string menuMakanSehat123() {
        string teks;
        teks = "Menu 123: nasi merah, ikan kukus, tumis kangkung, tahu, dan buah pepaya.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 124.
    string menuMakanSehat124() {
        string teks;
        teks = "Menu 124: kentang rebus, dada ayam, salad sayur, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 125.
    string menuMakanSehat125() {
        string teks;
        teks = "Menu 125: roti gandum, telur dadar, tomat, timun, dan buah apel.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 126.
    string menuMakanSehat126() {
        string teks;
        teks = "Menu 126: bubur kacang hijau rendah gula dan buah potong.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 127.
    string menuMakanSehat127() {
        string teks;
        teks = "Menu 127: nasi, telur, capcay, tahu, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 128.
    string menuMakanSehat128() {
        string teks;
        teks = "Menu 128: ubi rebus, ikan, sayur bayam, dan buah jeruk.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 129.
    string menuMakanSehat129() {
        string teks;
        teks = "Menu 129: nasi merah, ayam suwir, brokoli, tempe, dan buah melon.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 130.
    string menuMakanSehat130() {
        string teks;
        teks = "Menu 130: mie rebus homemade dengan telur dan banyak sayur.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 131.
    string menuMakanSehat131() {
        string teks;
        teks = "Menu 131: nasi, ayam panggang, sayur bening, tempe, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 132.
    string menuMakanSehat132() {
        string teks;
        teks = "Menu 132: oatmeal, pisang, telur rebus, dan susu rendah gula.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 133.
    string menuMakanSehat133() {
        string teks;
        teks = "Menu 133: nasi merah, ikan kukus, tumis kangkung, tahu, dan buah pepaya.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 134.
    string menuMakanSehat134() {
        string teks;
        teks = "Menu 134: kentang rebus, dada ayam, salad sayur, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 135.
    string menuMakanSehat135() {
        string teks;
        teks = "Menu 135: roti gandum, telur dadar, tomat, timun, dan buah apel.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 136.
    string menuMakanSehat136() {
        string teks;
        teks = "Menu 136: bubur kacang hijau rendah gula dan buah potong.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 137.
    string menuMakanSehat137() {
        string teks;
        teks = "Menu 137: nasi, telur, capcay, tahu, dan air putih.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 138.
    string menuMakanSehat138() {
        string teks;
        teks = "Menu 138: ubi rebus, ikan, sayur bayam, dan buah jeruk.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 139.
    string menuMakanSehat139() {
        string teks;
        teks = "Menu 139: nasi merah, ayam suwir, brokoli, tempe, dan buah melon.";
        return teks;
    }

    // Fungsi untuk menyediakan contoh menu makan sehat nomor 140.
    string menuMakanSehat140() {
        string teks;
        teks = "Menu 140: mie rebus homemade dengan telur dan banyak sayur.";
        return teks;
    }


    // Fungsi untuk menampilkan panduan kategori BMI agar mudah dijelaskan saat presentasi.
    void tampilkanPanduanKategoriBMI() {
        cout << "\n=== PANDUAN KATEGORI BMI ===\n";
        cout << "BMI < 18.5        : Kurus\n";
        cout << "BMI 18.5 - 24.9   : Normal\n";
        cout << "BMI 25.0 - 29.9   : Gemuk\n";
        cout << "BMI >= 30.0       : Obesitas\n";
        cout << "\nRumus BMI = berat badan / (tinggi badan * tinggi badan)\n";
        cout << "Berat badan menggunakan satuan kilogram.\n";
        cout << "Tinggi badan menggunakan satuan meter.\n";
    }

    // Fungsi untuk menghapus semua data yang ada di dalam aplikasi.
    void resetSemuaData() {
        if (dataMasihKosong()) {
            return;
        }

        int yakin;
        cout << "\nApakah yakin ingin menghapus semua data?\n";
        cout << "1. Ya\n";
        cout << "2. Tidak\n";
        yakin = inputAngka("Pilih: ", 1, 2);

        if (yakin == 1) {
            jumlahData = 0;
            nomorIdTerakhir = 1000;
            cout << "\nSemua data berhasil direset.\n";
        } else {
            cout << "\nReset data dibatalkan.\n";
        }
    }
};

int main() {
    AplikasiBMI aplikasi;
    aplikasi.jalankanAplikasi();

    return 0;
}
