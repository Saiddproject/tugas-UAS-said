# tugas-UAS-said

from data.mahasiswa import DataMahasiswa
from view.input_form import InputForm
from view.mahasiswa import ViewMahasiswa

def main():
    data_mahasiswa = DataMahasiswa()

    while True:
        print("\nMenu:")
        print("1. Tambah Mahasiswa")
        print("2. Tampilkan Semua Mahasiswa")
        print("3. Cari Mahasiswa")
        print("4. Ubah Mahasiswa")
        print("5. Hapus Mahasiswa")
        print("6. Keluar")

        pilihan = input("Pilih menu: ")

        if pilihan == "1":
            nim, nama, jurusan = InputForm.input_data()
            data_mahasiswa.tambah_mahasiswa(nim, nama, jurusan)
            print("\nMahasiswa berhasil ditambahkan!")
        elif pilihan == "2":
            ViewMahasiswa.tampilkan_semua(data_mahasiswa.data)
        elif pilihan == "3":
            nim = input("Masukkan NIM Mahasiswa: ")
            mahasiswa = data_mahasiswa.cari_mahasiswa(nim)
            ViewMahasiswa.tampilkan_detail(mahasiswa)
        elif pilihan == "4":
            nim = input("Masukkan NIM Mahasiswa yang akan diubah: ")
            nama_baru = input("Masukkan Nama Baru: ")
            jurusan_baru = input("Masukkan Jurusan Baru: ")
            data_mahasiswa.ubah_mahasiswa(nim, nama_baru, jurusan_baru)
            print("\nData mahasiswa berhasil diubah!")
        elif pilihan == "5":
            nim = input("Masukkan NIM Mahasiswa yang akan dihapus: ")
            data_mahasiswa.hapus_mahasiswa(nim)
            print("\nMahasiswa berhasil dihapus!")
        elif pilihan == "6":
            print("Program selesai.")
            break
        else:
            print("Pilihan tidak valid!")
            
   if __name__ == "__main__":
    main()
