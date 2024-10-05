#include <iostream>

using namespace std;

int main() {
    int komputer, pemain;
    char mainLagi;

    do {
        // Menghasilkan pilihan acak untuk komputer
        komputer = (time(0) % 3); // Menggunakan time sebagai seed sederhana

        // Menampilkan pilihan kepada pemain
        cout << "Pilih: " << endl;
        cout << "0 - Batu" << endl;
        cout << "1 - Gunting" << endl;
        cout << "2 - Kertas" << endl;
        cout << "Masukkan pilihan Anda (0/1/2): ";
        cin >> pemain;

        // Memastikan input yang dimasukkan pemain valid
        while (pemain < 0 || pemain > 2) {
            cout << "Pilihan tidak valid. Silakan masukkan 0, 1, atau 2: ";
            cin >> pemain;
        }

        cout << "Pilihan Komputer: " << komputer << endl;
        cout << "Pilihan Anda: " << pemain << endl;

        // Menentukan pemenang
        if (pemain == komputer) {
            cout << "Hasil: Seri!" << endl;
        } else if ((pemain == 0 && komputer == 1) || (pemain == 1 && komputer == 2) || (pemain == 2 && komputer == 0)) {
            cout << "Selamat! Anda menang!" << endl;
        } else {
            cout << "Sayang sekali, Anda kalah!" << endl;
        }

        // Menanyakan apakah pemain ingin bermain lagi atau tidak
        cout << "Apakah Anda ingin bermain lagi? (y/n): ";
        cin >> mainLagi;

    } while (mainLagi == 'y' || mainLagi == 'Y');

    cout << "Terima kasih telah bermain!" << endl;

    return 0;
}
