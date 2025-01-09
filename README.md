# project-UAS-Den-Fahmi-Satria
Nama: Den Fahmi Satria <p>
Nim: 312410523 <p>
kelas: TI.24.A5 <p>
Mata Kuliah: Bahasa Pemograman <p>

## Program Input buku, Code Dan Penjelasan
```
1. kelas Data <p>
Kelas ini bertanggung jawab untuk menyimpan dan mengelola data buku.
Kode:
``` python
class Data:
    def _init_(self):
        self.books = []

    def add_book(self, title):
        self.books.append(title)

    def remove_book(self, title):
        if title in self.books:
            self.books.remove(title)

    def get_books(self):
        return self.books ```
Penjelasan: <p>
- _init_: Metode ini membuat daftar kosong untuk menyimpan buku.
- add_book: Menambahkan buku ke daftar.
- remove_book: Menghapus buku dari daftar jika ada dalam daftar.
- get_books: Mengembalikan daftar buku.

2. Kelas View
Kelas ini bertanggung jawab untuk berinteraksi dengan pengguna, menampilkan pesan dan mendapatkan input dari pengguna.
Kode:
python
``` class View:
    def display_books(self, books):
        if not books:
            print("Daftar buku kosong.")
        else:
            print("Daftar Buku:")
            for book in books:
                print(f"- {book}")

    def get_user_input(self):
        return input("Masukkan judul buku: ")

    def show_message(self, message):
        print(message) ```
Penjelasan:
- display_books: Menampilkan daftar buku.

- get_user_input: Mendapatkan input dari pengguna berupa judul buku.

- show_message: Menampilkan pesan kepada pengguna.

3. Layer Process
Layer ini bertanggung jawab untuk menangani logika program dan mengoordinasikan interaksi antara layer Data dan View.

Kode:
python
``` class Process:
    def _init_(self):
        self.data = Data()
        self.view = View()

    def add_book(self):
        while True:
            title = self.view.get_user_input()
            self.data.add_book(title)
            self.view.show_message(f"Buku '{title}' telah ditambahkan.")
            
            another = input("Apakah Anda ingin menambah buku lagi? (y/n): ").strip().lower()
            if another != 'y':
                break

    def remove_book(self):
        title = self.view.get_user_input()
        self.data.remove_book(title)
        self.view.show_message(f"Buku '{title}' telah dihapus.")

    def show_books(self):
        books = self.data.get_books()
        self.view.display_books(books)

    def run(self):
        while True:
            print("\nMenu:")
            print("1. Tambah Buku")
            print("2. Hapus Buku")
            print("3. Tampilkan Daftar Buku")
            print("4. Keluar")
            choice = input("Pilih opsi: ")

            if choice == '1':
                self.add_book()
            elif choice == '2':
                self.remove_book()
            elif choice == '3':
                self.show_books()
            elif choice == '4':
                print("Keluar dari program.")
                break
            else:
                print("Opsi tidak valid. Silakan coba lagi.") ```
Penjelasan:
- _init_: Menginisialisasi objek Data dan View.

- add_book: Menambahkan buku dengan berulang kali meminta input pengguna hingga pengguna selesai menambah buku.

- remove_book: Menghapus buku yang ditentukan oleh pengguna.

- show_books: Menampilkan daftar buku yang ada.

- run: Menyediakan antarmuka menu utama yang memungkinkan pengguna untuk memilih opsi untuk menambah, menghapus, menampilkan daftar buku, atau keluar dari program.

4. Kelas Main
Kelas ini bertanggung jawab untuk menjalankan program dan mengoordinasikan keseluruhan alur kerja aplikasi dengan menginisialisasi kelas Process dan memanggil metode run untuk memulai aplikasi.

Kode:
python
``` from process import Process

if _name_ == "_main_":
    app = Process()
    app.run() ```
Penjelasan:
- from process import Process: Mengimpor kelas Process dari modul process.

- if _name_ == "_main_":: Ini adalah cara Python untuk memastikan bahwa kode dalam blok ini hanya akan dijalankan jika skrip dieksekusi secara langsung, bukan jika skrip diimpor sebagai modul.

- app = Process(): Membuat instance dari kelas Process.

- app.run(): Memanggil metode run pada instance Process untuk memulai aplikasi. Metode run akan menampilkan menu utama dan menangani logika aplikasi berdasarkan pilihan pengguna.


### Berikut adalah Link Youtube Mengenai Pembuatan dan Eksekusi Program 
https://www.youtube.com/watch?v=VcsnOlX2v80
