import java.util.Scanner;
//import import java.util.Scanner; itu kegunaanya untuk membaca imput dari pengguna //

public class uas{
//public class uas mendeklarasi nama kelas utama dengan nama uas //

    public static void main(String[] args) {
        //  public static void main titik awal dijalankanya kode dan semua ada yang didalam main mthode //

        Scanner scanner = new Scanner(System.in);
        // Scanner untuk meerima input dari pengguna //


        // Array untuk menyimpan nama pesanan, harga, dan jumlah //
        String[] orders = new String[100];
        //orders itu  kegunaanya menyimpan daftar pesanan sebagai array string //

        int[] prices = new int[100];
        // prices itu kegunaaanya untuk menyimpan harga sebagai array intrger //

        int[] quantities = new int[100]; 
        //quantities itu kegunaanya untuk menyimpan jumlah pesanan sebagai array intrager //

        int orderCount = 0;
        //ordercount ini kegunaanya untuk menyimpan jumlah pesanan yang telah dimasukkan kedalam daftar pembelian //


        System.out.println("===== Selamat Datang di Kafe Bromo Hills =====");
        System.out.println("\n==== Daftar Menu ====");
        System.out.println("1. Espresso    - Rp20000");
        System.out.println("2. Amricano    - Rp25000");
        System.out.println("3. Bromo Coffe - Rp30000");
        System.out.println("4. Kentang Goreng - Rp30000");
        System.out.println("5. Roti Bakar     - Rp20000");
        System.out.println("6. Cappuccino     - Rp20000");
        System.out.println("7. Creame Brule   - Rp25000");
        // system.out. println ini kegunaanya untuk bertujuan menampilkan daftar menu dan masing masing item yang telah kita pesan //


        while (true) {
            System.out.println("\nPilih opsi berikut:");
            System.out.println("1. Tambah Pesanan");
            System.out.println("2. Lihat Daftar Pesanan");
            System.out.println("3. Hitung Total Biaya");
            System.out.println("4. Lakukan Pembayaran");
            System.out.println("5. Selesai");
            System.out.print("Masukkan pilihan Anda: ");
            int choice = scanner.nextInt();
            //jika kondisinya benar akan di cetak //


            if (choice == 1) {
            // kegunaan dari if (choice == 1 ) untuk mengecek apa variaber bernilai benar,maka program tersebut akan meminta imput dari pengguna untuk memilih menu //   

                System.out.print("Masukkan nomor menu yang ingin dipesan: ");
                // untuk menampilkan teks memasukkan nomor menu yang ingin di pesan //

                int menuNumber = scanner.nextInt();
                //untuk membaca input angka dari pengguna dan menyimpan dalam varibel //

                System.out.print("Masukkan jumlah pesanan: ");
                // untuk membaca jumlah pesanan yang dimasukkan //

                int quantity = scanner.nextInt();
                // untuk mebaca input interger //

                // Menentukan nama pesanan dan harga berdasarkan nomor menu
                String orderName = "";
                // untuk menyimpan nama pesaana // 

                int price = 0;
                // untk mentimpa hharga pesannann //

                switch (menuNumber) {
                // untuk  menentukan nama dan harga pesanan berdasrkan menu Number yang di masukkan oleh pemngguns //


                    case 1:
                        orderName = "Espresso";
                        // orderName  ini kegunaanya untuk mengisi aitem yang akan kita beli // 

                        price = 20000;
                        // ini untuk harga nya //

                        break;
                        // untuk menghentikan pemesanna atau eksekusi //


                    case 2:
                        orderName = "Americano";
                         // orderName  ini kegunaanya untuk mengisi aitem yang akan kita beli // 

                        price = 25000;
                         // ini untuk harga nya //

                        break;
                         // untuk menghentikan pemesanna atau eksekusi //


                    case 3:
                        orderName = "Bromo Coffe";
                        // orderName  ini kegunaanya untuk mengisi aitem yang akan kita beli // 

                        price = 30000;
                          // ini untuk harga nya //

                        break;
                         // untuk menghentikan pemesanna atau eksekusi //


                    case 4:
                        orderName = "Kentang Goreng";
                        // orderName  ini kegunaanya untuk mengisi aitem yang akan kita beli // 

                        price = 30000;
                          // ini untuk harga nya //

                        break;
                         // untuk menghentikan pemesanna atau eksekusi //


                    case 5:
                        orderName = "Roti Bakar";
                        // orderName  ini kegunaanya untuk mengisi aitem yang akan kita beli // 

                        price = 20000;
                          // ini untuk harga nya //

                        break;
                         // untuk menghentikan pemesanna atau eksekusi //


                    case 6:
                        orderName = "Cappuccino";
                        // orderName  ini kegunaanya untuk mengisi aitem yang akan kita beli // 

                        price = 30000;
                          // ini untuk harga nya //

                        break;
                         // untuk menghentikan pemesanna atau eksekusi //


                    case 7:
                        orderName = "Cream brule";
                        // orderName  ini kegunaanya untuk mengisi aitem yang akan kita beli // 

                        price = 25000;
                          // ini untuk harga nya //

                        break;
                         // untuk menghentikan pemesanna atau eksekusi //

                    default:
                        System.out.println("Menu tidak valid. Silakan coba lagi.");
                        continue;
                }


                // Menyimpan ke dalam array
                orders[orderCount] = orderName;
                //orders[orderCount]  kegunanyan untuk menyimpan data nam pesanan pada array //

                prices[orderCount] = price;
                //prices[orderCount] menyimpan harga pesaana yang dipesan pada array //

                quantities[orderCount] = quantity;
                //quantities[orderCount] ini kegunaanya untuk menyimpan jumlah pesana di array //

                orderCount++;
                //  Dan orderCount++; untuk menabah jumlah pesanan kita dalam emmilih daftar makaan // 


                System.out.println(orderName + " berhasil ditambahkan ke pesanan.");
                // System.out.println _orderName ini kegunannya untuk mencetak pesaaan kita kelayar bahwa pesannan kita berhasil di tambahkan //

            } else if (choice == 2) {
                // else if (choice == 2) ini untuk menegcek apakah pengguna memiliki opsi 2(atau meliaht daftar pesannan) //

                System.out.println("\n=== Daftar Pesanan ===");
                // menampilka header daftar pesanan //

                int totalCost = 0;
                // mengisialisasi variabel untuk menyimpan total harga //

                for (int i = 0; i < orderCount; i++) {
                    // melalkukan sebuah inteasi untuk pesanan yang tersimpan //

                    int subtotal = prices[i] * quantities[i];
                    // menghitung harga total untuk untuk pesanan //

                    System.out.println(orders[i] + " x" + quantities[i] + " - Rp" + subtotal);
                    totalCost += subtotal;
                    // ini untuk menampilkan pesanan dalam frmat (naam pesanan * jumlah - total) //
                }
                System.out.println("Total Biaya: Rp" + totalCost);
                // menampilkan total biaya dari keseluruhan //


            } else if (choice == 3) {
                // ini berguna untuk mengecek apakah pengguna memili 0psi 3 (melihat total biaya semua pesanan)//

                int totalCost = 0;
                //menganalisi ulang //

                for (int i = 0; i < orderCount; i++) {
                    //melakukan interaksi untuk menghitung semua biaya pemesanan //

                    totalCost += prices[i] * quantities[i];\
                    //menabhkann setiap subtotal ke totalCost//

                }
                System.out.println("\nTotal Biaya dari Semua Pesanan: Rp" + totalCost);
                //menampilkan total semua biaya pesanan //


            } else if (choice == 4) {
                // menecek apakah pengguna memilih opsi 4 (proses pembayaran)//

                // Sistem pembayaran
                int totalCost = 0;
                //menganalisis ulang //

                for (int i = 0; i < orderCount; i++) {
                    //menghitung total biaya semua pesanan //

                    totalCost += prices[i] * quantities[i];
                    //menabhkann setiap subtotal ke totalCost//
                }

                System.out.println("\n=== Pembayaran ===");
                // menampilkan pesana bahwa sistem masuk ke proses pembayaran //

                System.out.println("Total Biaya: Rp" + totalCost);
                // ini mencetak total biaya yang harus dibayar.//

                System.out.print("Masukkan jumlah uang yang dibayarkan: ");
                //ini menampilkan pesan untuk meminta pengguna memasukkan jumlah uang yang  dibayarkan  //

                int payment = scanner.nextInt();
                //untuk mengambil input dari pengguna, yaitu jumlah uang yang akan dibayarkan //

                while (payment < totalCost) {
                    // untuk memeriksa apakah jumlah uang yang dibayar (payment )  kurang dari total biaya yang harus di bayar //

                    System.out.println("Uang tidak mencukupi. Masukkan jumlah yang sesuai.");
                    System.out.print("Masukkan jumlah uang yang dibayarkan: ");
                    payment = scanner.nextInt();
                    // jika sesuai dengan nilai total uang yang di akan di bayar maka akam lanjut ke tahap berikutnya //

                }

                int change = payment - totalCost;
                // menghitung kembalaian yang harus di beri kepada pengguna setelah mereka melakukan pembayarann //

                System.out.println("Pembayaran berhasil. Kembalian Anda: Rp" + change);
                System.out.println("Terima kasih telah memesan. Sampai jumpa!");
                break; // Program selesai setelah pembayaran
                // setelah selesai melakukan pembayaran program akan keeluar dari Stuktur kontrol dan selesai //

            } else if (choice == 5) {
                // kita sudah selesai melakukan pememesan dan pemembayar //
                System.out.println("Terima kasih telah memesan. Sampai jumpa!");
                break;
                // keluar dari struktur kontrol atau Loop//
            } else {
                System.out.println("Pilihan tidak valid. Silakan coba lagi.");
                //Ini memberi tahu pengguna bahwa input yang mereka masukkan tidak ada dalam daftar opsi yang valid (1, 2, 3, 4, 5), sehingga mereka perlu memasukkan pilihan yang benar.//
            }
        }

        scanner.close();
        //ini menutup Scanner yang digunakan untuk membaca input dari pengguna.//   
    }

 {
    
}
}