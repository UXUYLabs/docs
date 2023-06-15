# White Paper(Indonisia)

### Introduction:

Saat ini, ketika menggunakan aplikasi sosial terpusat, pengguna tidak benar-benar memiliki aset sosial yang mereka ciptakan (seperti hubungan sosial, data sosial, dll.). Ketika aplikasi terpusat mengubah aturan, memblokir akun, atau menghentikan layanan, pengguna akan kehilangan semua hubungan sosial dan data pribadi mereka. Di sisi lain, ketika produk aplikasi memperoleh nilai komersial dari hubungan sosial dan data sosial pengguna, pengguna tidak dapat atau jarang mendapatkan keuntungan dari itu. Situasi ini umum terjadi pada era Web2.



Protokol Graf Sosial UXUY bertujuan untuk melindungi, memonetisasi, dan mengoptimalkan aset sosial pengguna. Melalui sifat terdesentralisasi blockchain, protokol ini membantu pengguna sepenuhnya memiliki kedaulatan data sosial mereka, mengoptimalkan aset sosial, dan mengenkripsi informasi ini di rantai. UXUY sepenuhnya menjaga kepentingan pengguna terdesentralisasi, membantu pengguna melindungi data sosial mereka, dan memonetisasinya. Ketika beberapa DAPP menggunakan hubungan sosial dan data pengguna, pengguna akan menerima imbalan token.



UXUY berkomitmen untuk membangun infrastruktur untuk memfasilitasi aplikasi sosial Web3 generasi berikutnya yang berskala besar. Ini akan menjadi protokol di blockchain, memastikan enkripsi data dan skalabilitas ekosistem. Kami menamai protokol ini "Protokol UXUY". Protokol UXUY menggunakan "Token UXUY" sebagai token insentif, dan menggunakan mekanisme POL (Proof Of Link) untuk mencatat kontribusi pengguna ke seluruh jaringan sosial. Semakin besar dan bernilai jaringan sosial yang dibangun oleh pengguna, semakin banyak imbalan token yang mereka terima. Token juga dapat digunakan untuk membeli layanan di DAPP lain atau dalam skenario lainnya.

### Fitur Protokol UXUY:

#### Akses Langsung dari WEB2 ke WEB3

Pengguna dapat membuat akun Web3 menggunakan platform seperti Google, Twitter, WeChat, dan lainnya. UXUY menyediakan dompet MPC yang terenkripsi kepada pengguna, sehingga mereka dapat menggunakan dan mengalami aplikasi Web3 tanpa perlu mencatat kunci publik dan pribadi yang rumit. Hal ini menurunkan hambatan pengguna untuk masuk ke Web3 sambil memaksimalkan nilai akun sosial pengguna di platform Web2.

#### Identitas Eksklusif

Melalui Protokol UXUY, pengguna dapat membuat identitas berbasis blockchain yang disebut Profil UXUY. Profil UXUY ini berfungsi sebagai titik referensi desentralisasi identitas pengguna, yang dapat terhubung dan digunakan dengan lancar di internet dan DAPP berbasis blockchain. Profil UXUY menggunakan metode kriptografi Web3 untuk mewakili data status, relasi keanggotaan, dan verifikasi sosial.

#### Komposabilitas Plug-and-Play

Inovasi teknologi terbesar dari Protokol UXUY adalah desain dan implementasi standar penyimpanan dan penggunaan informasi yang dapat digunakan oleh berbagai DAPP. Sebagai dasar jaringan sosial dalam Web3, Protokol UXUY dapat diintegrasikan ke dalam aplikasi Web3 mana pun, memungkinkan pengembang DAPP untuk dengan mudah mengakses lebih banyak pengguna Web3.

#### Mendukung Multi-Chain

Protokol UXUY menggunakan jaringan Arbitrum yang efisien dan aman, dan telah mendapatkan dukungan kerjasama dari Arbitrum untuk menyediakan layanan teknologi yang aman dan cepat bagi UXUY. Di masa depan, UXUY juga akan memperluas kehadirannya di berbagai jaringan blockchain lainnya, sehingga ekosistem UXUY menjadi semakin kaya.



### Arsitektur teknis dari protokol UXUY

Protokol UXUY adalah infrastruktur otentikasi yang dapat disisipkan untuk aplikasi Web3.

<figure><img src="../.gitbook/assets/whitepaper_01.jpg" alt=""><figcaption><p>I</p></figcaption></figure>

### Tokenomics UXUY Protokol

Protokol UXUY akan menggunakan model dua token, yaitu token aplikasi (UXUY Token) dan token pengelolaan (UXUY Governance Token).

#### 1.Token Aplikasi UXUY

&#x20;1.1 Mekanisme Penghargaan Token UXUY

UXUY Token tidak memiliki token yang ditahan dan menggunakan mekanisme Proof of Link (POL) yang sepenuhnya adil. Setiap orang yang ingin memperoleh UXUY Token harus memberikan kontribusi pada pembangunan jaringan sosial Web3. Pengguna perlu memperluas jaringan sosial mereka (mengundang pengguna lain) untuk mendapatkan lebih banyak UXUY Token. UXUY Token dapat disimpan dalam dompet kripto yang kompatibel dengan Ethereum. Setiap kali pengguna berhasil menghubungkan simpul sosial (mengundang seseorang), mereka akan mendapatkan sejumlah tertentu UXUY Token sebagai penghargaan. Semakin awal pengguna membuat jaringan sosial mereka, semakin banyak UXUY Token yang mereka dapatkan.



1.2 Formula Penurunan Penghargaan Pembangunan Simpul

{% code overflow="wrap" %}
```vue
 Rewards = OG * [ TAM(ts) * (1 + EAR（cLg）)* cLu / log2(cLg) ]
```
{% endcode %}

#### Keterangan:

* TAM(ts0) = <mark style="color:green;">max(3000 - \[(ts0 - tsG)/3600\*24], 1)</mark>
* EAR(cLg) = <mark style="color:green;">max((k/100) - 0.001 \* \[cLg / 100000], 0)</mark>
* OG - Pengguna yang memiliki NFT SEAMAN, dengan faktor insentif tertimbang sebesar 120%.
* TAM - Time amplifier, penguat waktu untuk insentif peserta awal.
* EAR - Early Adopter Reward, insentif kontributor awal.
  * 0-10 ribu simpul jaringan, koefisien insentif EAR dimulai dari 90%.
  * 10 ribu-1 juta simpul jaringan, koefisien insentif EAR dimulai dari 30%.
  * Setelah 1 juta simpul jaringan, koefisien insentif EAR turun menjadi 10% dan turun 0,1% setiap 100 ribu simpul.
  * k - Koefisien insentif EAR:
    * _<mark style="color:green;">\[cLg < 10 ribu, k=40]</mark>_
    * _<mark style="color:green;">\[10 ribu < cLg < 1 juta, k=20]</mark>_
    * _<mark style="color:green;">\[1 juta < cLg, k=10]</mark>_
* ts0 - Waktu saat ini saat simpul dibangun.
* tsG - Waktu mulai rilis proyek dari awal.
* cLu - Jumlah orang yang membangun simpul saat ini.
* cLg - Jumlah total orang dalam jaringan UXUY saat ini.
* Jika cLg >= 30 juta, Rewards = 0, artinya tidak akan ada lagi UXUY Token baru yang dihasilkan ketika jaringan mencapai 30 juta orang. Pada saat itu, nilai yang dihasilkan oleh efek jaringan dapat mendukung pengguna dan simpul untuk terus berkembang hingga mencapai skala miliaran.

UXUY Token mengikuti logika penurunan yang mirip dengan penambangan Bitcoin dan menggunakan rumus perhitungan yang paling mirip dengan penambangan Bitcoin. Penurunan token melibatkan faktor-faktor seperti waktu, jumlah orang yang terhubung ke simpul tunggal, dan total jumlah orang dalam jaringan UXUY. Oleh karena itu, seiring berjalannya waktu setelah peluncuran UXUY dan peningkatan jumlah orang dalam jaringan UXUY, pengguna akan menerima UXUY Token yang semakin berkurang secara eksponensial. Semakin lambat pengguna masuk ke jaringan UXUY, semakin sedikit UXUY Token yang akan mereka peroleh.



1.3 Mekanisme Pembakaran UXUY Token

UXUY Token adalah token aplikasi dari protokol UXUY yang dapat digunakan untuk membayar biaya gas dalam ekosistem UXUY, termasuk operasi seperti pengiriman transaksi, transfer token, dan akses ke jaringan sosial. Dalam ekosistem UXUY, 15% dari biaya-biaya ini akan dibakar.



#### 2.Token Pengelolaan UXUY

2.1 In the future

Di masa depan, UXUY juga akan merilis token pengelolaan komunitas (UXUY Governance Token, sementara disebut sebagai UGT). Sebagian besar token pengelolaan akan dialokasikan kepada komunitas, sementara sebagian kecil akan dialokasikan kepada mitra, tim, dan investor.

### Ringkasan:

UXUY adalah protokol sosial berbasis teknologi blockchain yang bertujuan untuk melindungi, memonetisasi, dan mengoptimalkan aset sosial pengguna. Protokol ini menggunakan mekanisme POL (Proof of Link) yang sepenuhnya adil, dengan UXUY Token sebagai token imbalan. Pengguna dapat membangun simpul jaringan sosial dalam protokol UXUY untuk mendapatkan imbalan, dan UXUY Token juga dapat digunakan untuk membeli layanan atau produk di dunia Web3.

UXUY sedang menciptakan ekosistem sosial Web3 yang baru, di mana berbagai jenis DAPP akan terhubung ke protokol UXUY secara bertahap. Di masa depan, ekosistem UXUY ini akan menjadi lebih kaya.
