# Tugas9_MuhammadAhnafMaulana_5311421074
# Module 4
## Teknik Pencarian Blind Search (Breadth First Search)

#### Penjelasan
![alt text](https://github.com/nnooi/Tugas9_MuhammadAhnafMaulana_5311421074/blob/e7fbaf92ac80a6283339743497efda1c60274b9d/Praktikum4/img/Metode_BFS.jpeg?raw=true)
Pada module 4 BSF digunakan untuk melakukan atau mencari suatu goal state dari initial statenya dengan metode yang bisa dilihat pada gambar diatas. 

Pada Metode tersebut semua node pada level n akan dikunjungi  terlebih dahulu sebelum mengunjungi node-node pada level n+1. Pencarian dimulai dari node akar terus ke level ke-1 dari kiri ke kanan, kemudian berpindah ke level berikutnya demikian pula dari kiri ke kanan hingga ditemukannya solusi. 

## Tugas

- Tentukan bagaimana algoritma BFS di atas dapat menentukan node ke 8, 6, dan 7. dari ([sc, Tugas no 1](https://github.com/nnooi/Tugas9_MuhammadAhnafMaulana_5311421074/blob/e7fbaf92ac80a6283339743497efda1c60274b9d/Praktikum4/src/tugas1.java))
- Ubahlah method static void main sehingga bentuk tree seperti Gambar 4.6 dapat dibentuk. Kemudian tentukan bagaimana algoritma BFS dapat menemukan node 5. 
- Ubahlah method static void main sehingga bentuk tree seperti Gambar 4.5 dapat dibentuk.  Kemudian tentukan bagaimana algoritma BFS dapat menemukan node 9
- Ubahlah kode program di atas sehingga bentuk tree seperti Gambar 4.7 dapat dibentuk. Kemudian tentukan bagaimana algoritma BFS dapat menemukan node C
Note : Gambar terdapat pada Module praktikum

#### Jawab
- Algoritma BFS dalam program di atas digunakan untuk mencari jarak terpendek dari node awal (dalam kasus ini, node n3) ke semua node lain dalam graph. Algoritma ini juga akan menentukan node yang dijangkau dengan menyusuri graph secara berlapis (layer by layer) dari node awal.
Algoritma dimulai dengan menginisialisi semua node dalam grapgh dengan beberapa parameter, salah satunya yaitu distace (jarak). Kemudian n3 (node 3) diinisiasi dengan jarak = 0. dan algoritma akan menjelajahi node awal (node3). Selanjutnya algoritma akan menjelajahi node node yang berdekatan (distancenya kecil = 1) yaitu node 4 dan node 2. Selanjutnya algoritma akan mengunjungi node 5, 6, dan 1 dengan distance 2 dari jarak awal. Dan yang terakhir akan mengunjungi node 7 dan node 8. Maka dari itu, BFS dalam menentukan node 8, 6, dan ke 7 dapat dilakukan dengan dengan memperhatikan distance antar node dengan node awal. hasil dari distancenya dapat dilihat pada gambar berikut
![alt text](https://github.com/nnooi/Tugas9_MuhammadAhnafMaulana_5311421074/blob/2dd1af28126f8cdf3d93a03b8fd162ce3999b91d/Praktikum4/img/hasilno1.jpeg?raw=true)
- Lalu pada soal berikutnya, ubah static void main dr soal 1 agar menjadi tree pada gambar 4.5. static void main dapat dilihat pada code dibawah dan akan diubah nilainya untuk membuat tree seperti yang diperintahkan denagan sc yang saya buat ([sc, Tugas no 2](https://github.com/nnooi/Tugas9_MuhammadAhnafMaulana_5311421074/blob/2dd1af28126f8cdf3d93a03b8fd162ce3999b91d/Praktikum4/src/tugas2.java))
```sh
public static void main(String[] args){
            AdjacencyList graph = new AdjacencyList();
            Node n1 = new Node(1);
```
Lalu sc yang dijalankan akan memberikan desain tree yang diminta, dan node 5 didapatkan pada layer 2 dari node awal berdasarkan distancenya yaitu 2
![alt text](https://github.com/nnooi/Tugas9_MuhammadAhnafMaulana_5311421074/blob/2dd1af28126f8cdf3d93a03b8fd162ce3999b91d/Praktikum4/img/hasilno2.jpeg?raw=true)
- Ubah code yang sebelumnya agar menjadi desain tree yang diminta ([sc, Tugas no 3](https://github.com/nnooi/Tugas9_MuhammadAhnafMaulana_5311421074/blob/2dd1af28126f8cdf3d93a03b8fd162ce3999b91d/Praktikum4/src/tugas3.java))
Lalu jalankan dan akan memberikan hasil sebagai berikut
![alt text](https://github.com/nnooi/Tugas9_MuhammadAhnafMaulana_5311421074/blob/2dd1af28126f8cdf3d93a03b8fd162ce3999b91d/Praktikum4/img/hasilno3.jpeg?raw=true)
node 9 ditemukan pada layer 3 dikarenakan distancenya dengan node awal yaitu berjarak 3.
- Selanjutnya ubah code untuk memberikan desain tree pada gambar 4.7. Untuk desain tree yang digunakan menggunakan huruf, maka tipe data pada node diubah terlebih dahulu menjadi char. 
```sh
public static class Node
    {
        char data;
        int distance;
        Node predecessor;
        NodeColour colour;
            public Node(char data)
                {
                this.data = data;
                }
        public String toString()
            {
            return "(" + data + ",d=" + distance + ")";
            }
    }
```
Selanjutnya saya ubah code manjadi ([sc, Tugas no 4](https://github.com/nnooi/Tugas9_MuhammadAhnafMaulana_5311421074/blob/2dd1af28126f8cdf3d93a03b8fd162ce3999b91d/Praktikum4/src/no4.java)), lalu menghasilkan desain tree sebagai berikut :
![alt text](https://github.com/nnooi/Tugas9_MuhammadAhnafMaulana_5311421074/blob/2dd1af28126f8cdf3d93a03b8fd162ce3999b91d/Praktikum4/img/hasilno4.jpeg?raw=true)
Dapat dilihat, bahwa BFS dapat menentukan node C pada layer 3 dikarenakan distancenya dengan node awalnya (node F) bernilai 3.

# Module 5
## TEKNIK HEURISTIC SEARCH (Heuristic Search)

Teknik Heuristic Search merupakan suatu proses dimana pencarian solusi akan ditemukan dengan baik namun bisa juga kemungkinan tidak ada solusi. Teknik ini mmebutuhkan sebuah nilai untuk menentukan pencarian berikutnya. Nilai heuristic dapat ditentukan melalui fungsi heuristic. Fungsi heuristic merupakan fungsi yang melakukan pemetaan dari diskripsi keadaan ke pengukur kebutuhan. Umumnya fungsi ini direpresentasikan ke dalam bentuk angka. Dalam ilmu  Kecerdasan Buatan, heuristic dihadapkan dalam 2 keadaan dasar.
 Persoalan/problema yang mungkin memiliki solusi eksak, namun biaya perhitungan untuk menemukan solusi tersebut sangat tinggi dalam kebanyakan persoalan (seperti catur), ruang keadaan bertambah secara luar biasa seiring dengan jumlah.
 Persoalan yang mungkin tidak memiliki solusi eksak karena ambiquitas (ketidakpastian) mendasar dalam pernyataan persoalan atau data yang tersedia diagnosa medis merupakan salah satu contohnya.

Penggunaannya dapat dicontohkan pada kasus 8 -puzzle berikut :
![alt text](https://github.com/nnooi/Tugas9_MuhammadAhnafMaulana_5311421074/blob/1c5753854c200ca816f87f8292c1ea0fc7915391/praktikum5/img/Model.jpeg?raw=true)
Langkah pertama dari permainan tersebut seperti terlihat pada diatas, Apabila  digunakan blind search, kita tidak perlu mengetahui operasi apa yang akan dikerjakan (sembarang operasi bisa digunakan). Pada pencarian heuristik perlu diberikan informasi khusus dalam domain tersebut. Informasi yang bisa diberikan, antara lain:
a. Untuk jumlah ubin yang menempati posisi yang benar: jumlah yang lebih tinggi  adalah yang lebih diharapkan (lebih baik),
b. Untuk jumlah ubin yang menempati posisi yang salah: jumlah yang lebih kecil adalah  yang diharapkan (lebih baik),
c. Menghitung total gerakan yang diperlukan untuk mencapai tujuan; jumlah yang lebih kecil adalah yang diharapkan (lebih baik).

## Tugas

- TPelajari class EightPuzzleSearch, EightPuzzleSpace, dan Node.
- Ubahlah initial dan goal state dari program di atas sehingga bentuk initial dan goal statenya Gambar 8. Kemudian tentukan langkah-langkah mana saja sehingga puzzlenya mencapai goal state. Analisa dan bedakan dengan solusi pada point 1.
- Ubahlah initial dan goal state dari program di atas sehingga bentuk initial dan goal statenya  Gambar 5.9. Kemudian tentukan langkah-langkah mana saja sehingga puzzlenya mencapai goal state. Analisa dan bedakan dengan solusi pada point 1 dan 2.
- Ubahlah initial dan goal state dari program di atas sehingga bentuk initial dan goal statenya Gambar 5.10. Kemudian tentukan langkah-langkah mana saja sehingga puzzlenya mencapai goal state. Analisa dan bedakan dengan solusi pada point 1, 2, dan 3.
- Ubahlah initial dan goal state dari program dan class-class di atas sehingga bentuk initial dan goal statenya Gambar 5.11. Kemudian tentukan langkah-langkah mana saja sehingga puzzlenya mencapai goal state
Note : Gambar terdapat pada Module praktikum

#### Jawab
- Teknik Heuristic Search sendiri digunakan untuk mencari intial state menjadi goal state. EightPuzzleSearch sendiri merupakan calss yang mendeskripsikan algoritma heuristic, menghitung cost heuristic, mencetak alur (path) dari root ke suatu node, dan menentukan node terbaik berdasarkan nilai dari fungsi heuristic. dijelaskan pada ([sc, EightPuzzleSearch](https://github.com/nnooi/Tugas9_MuhammadAhnafMaulana_5311421074/blob/1c5753854c200ca816f87f8292c1ea0fc7915391/praktikum5/src/EightPuzzleSearch.java))
Sedangkan, EightPuzzleSpace merupakan Objek yang berfungsi untuk mendefinisikan initial state dan goal state sehingga penggua (user) dengan mudah menentukan contoh initial dan goal state pada 8-puzzle, dituliskan pada ([sc, EightPuzzleSearch](https://github.com/nnooi/Tugas9_MuhammadAhnafMaulana_5311421074/blob/1c5753854c200ca816f87f8292c1ea0fc7915391/praktikum5/src/EightPuzzleSpace.java))
Hasil dari penggunaannya dapat dilihat pada gambar dibawah : 
![alt text](https://github.com/nnooi/Tugas9_MuhammadAhnafMaulana_5311421074/blob/1c5753854c200ca816f87f8292c1ea0fc7915391/praktikum5/img/hasil1.jpeg?raw=true)
Dijelaskan bahwa penggunaan Heursitik Search dapat memberikan goal state dari intial state yang dideklarasikan dengan cost atau step dijelaskan pada gambar diatas
- Lalu selanjutnya ubah intial state dan goalnya sebgai berikut :
```sh
int ex[] = {3, 1, 2, 4, 7, 5, 6, 8, 0}; // initial state
int state[] = {1, 2, 3, 4, 0, 5, 6, 7, 8}; // goal state
```
Lalu jalankan code tersebut, maka costnya dapat dilihat pada gambar berikut :
![alt text](https://github.com/nnooi/Tugas9_MuhammadAhnafMaulana_5311421074/blob/1c5753854c200ca816f87f8292c1ea0fc7915391/praktikum5/img/hasil2.jpeg?raw=true)
Dapat dilihat bahwa penggunaan algoritma tersebut dapat memberikan hasil yang bagus. Namun jika dibandingkan dengan point 1 costnya lebih banyak dikarenakan persoalan dari intitial dan goalnya memiliki solusi yang eksak.
- Lalu ubah lagi intial dan goalnya :
```sh
int ex[] = {1,5,3,4,6,8,2,7,0}; // initial state
int state[] = {7, 2, 4, 5, 0, 6, 8, 3, 1}; // goal state
```
Lalu jalankan code tersebut, maka costnya dapat dilihat pada gambar berikut :
![alt text](https://github.com/nnooi/Tugas9_MuhammadAhnafMaulana_5311421074/blob/1c5753854c200ca816f87f8292c1ea0fc7915391/praktikum5/img/hasil3.jpeg?raw=true)
Dapat dilihat bahwa penggunaan algoritma tersebut tidak dapat memberikan hasil. Dikarenakan persoalan yang dilakukan tidak memiliki solusi yang eksak (ambigu)
