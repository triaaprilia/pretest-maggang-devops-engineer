# Pre-Test Bootcamp DevOps

## knowledge base

1. Apa yang anda ketahui tentang DevOps?
2. Apa yang anda ketahui tentang Infrastructure?
3. Apa yang anda ketahui tentang server, sebutkan implementasi berserta contohnya?
4. Mengapa server dibutuhkan dalam pengembangan/development suatu software?
5. Apa yang anda ketahui mengenai Virtualisasi dan Container?
6. Mengapa teknology container saat ini sangat populer?
7. Apa yang anda ketahui tentang Orchestration Container System?

Cara pengerjaan, silahkan update file ini tulis jawabanya di bawah ini
1.	Apa yang anda ketahui tentang DevOps? 
DevOps atau Development dan Operation yaitu prinsip atau pola pikir yang digunakan di dunia IT untuk mengkoordinasikan antar tim yaitu tim development dengan tim operations dengan efektif dan efisien. Pola pikir yang dibentuk oleh DevOps adalah koordinasi antar tim yang dapat dilakukan dengan cara singkat sehingga tidak membutuhkan banyak pertanyaan. Tim operation atau development cukup mengonfigurasi beberapa komponen yang dibutuhkan melalui prosedur yang dibuat.

2.	Apa yang anda ketahui tentang Infrastructure?
Infrastructure merupakan kerangka kerja yang mendukung operasi teknologi informasi suatu organisasi. Ini meliputi perangkat keras, perangkat lunak, jaringan, sistem operasi, dan lingkungan fisik yang diperlukan untuk menjalankan aplikasi dan layanan.

3.	Apa yang anda ketahui tentang server, sebutkan implementasi berserta contohnya?
Server berperan penting dalam menyediakan layanan akses supaya lebih cepat untuk mengirim atau menerima data maupun informasi yang tersedia pada server. Server merupakan suatu sistem computer yang memiliki layanan berupa penyimpanan data , data yang disimpan melalui server berupa informasi dan beragam jenis dokumen yang kompleks.
Implementasi server:
•	Web server: Meng-host situs web dan menyampaikan konten web kepada pengguna, contohnya Apache atau Nginx.
•	Database server: Menyimpan dan mengelola basis data, seperti MySQL atau PostgreSQL.
•	File server: Menyimpan dan mengelola file yang dapat diakses oleh klien dalam jaringan, seperti Windows File Server atau Samba.
•	Mail server: Menangani pengiriman, penerimaan, dan penyimpanan email, seperti Microsoft Exchange atau Postfix.

4.	Mengapa server dibutuhkan dalam pengembangan/development suatu software?
Server dibutuhkan dalam pengembangan/development suatu software karena server menyediakan lingkungan yang konsisten dan terpisah untuk menguji dan mengembangkan aplikasi. Tim pengembangan dapat mengatur server untuk meniru kondisi produksi dan menguji aplikasi dalam lingkungan yang mirip dengan yang akan digunakan oleh pengguna akhir. Ini membantu mengidentifikasi masalah potensial dan memastikan bahwa aplikasi berjalan dengan baik sebelum diluncurkan. Server juga menyediakan alat dan fitur untuk otomatisasi dan manajemen pengembangan perangkat lunak. Mereka memungkinkan otomatisasi tugas-tugas seperti pengujian, pengiriman, dan penyebaran aplikasi. Server juga dapat dilengkapi dengan sistem manajemen konfigurasi yang memfasilitasi pengaturan dan pemeliharaan lingkungan pengembangan.

5.	Apa yang anda ketahui mengenai Virtualisasi dan Container?
Virtualisasi adalah teknologi yang memungkinkan penggunaan sumber daya komputasi yang terpisah secara fisik untuk menciptakan lingkungan virtual yang terisolasi. Dalam konteks server, virtualisasi memungkinkan pengguna menjalankan beberapa sistem operasi atau aplikasi secara bersamaan pada satu server fisik. Dalam lingkungan virtualisasi, setiap sistem operasi atau aplikasi berjalan sebagai mesin virtual yang terisolasi, dengan sumber daya yang dikelola secara terpisah.
Container, di sisi lain, adalah metode virtualisasi tingkat sistem operasi yang memungkinkan aplikasi dan dependensinya untuk diisolasi dalam wadah yang terpisah. Setiap wadah berjalan sebagai entitas independen dengan lingkungan file sistem, perpustakaan, dan konfigurasi sendiri.

Jadi, virtualisasi dan container adalah dua pendekatan virtualisasi yang berbeda dengan tujuan yang sama: mengisolasi dan mengelola aplikasi dengan cara yang efisien, portabel, dan terukur. Virtualisasi lebih cocok untuk mengelola sumber daya perangkat keras secara luas, sedangkan container lebih cocok untuk mengemas dan menjalankan aplikasi secara mandiri dengan efisiensi tinggi.

6.	Mengapa teknology container saat ini sangat populer?
Karena teknologi container bisa menyimpan aplikasi Bersama infrastruktur secara keseluruhan serta resiko aplikasi dan infrastruktur jika tidak kompatibel pun bisa ditekan. Jadi saat aplikasi on board  di developer bisa jalan, di multicloud bisa jalan, pun di infrastruktur lain pun bisa berjalan dengan lancar. Inilah yang menjadi keunggulan container.

7.	Apa yang anda ketahui tentang Orchestration Container System?
Orchestration Container System adalah sistem yang digunakan untuk mengelola dan mengotomatisasi implementasi, penjadwalan, peningkatan, dan penurunan container dalam lingkungan yang terdistribusi. 
Contoh sistem orchestration container termasuk Kubernetes, Docker Swarm, dan Apache Mesos. Sistem ini menyediakan fitur-fitur seperti manajemen skala, pemantauan, manajemen jaringan, dan penyebaran aplikasi container yang terdistribusi, memudahkan pengelolaan dan pengoperasian lingkungan container yang kompleks.


## Task 1 (Virtualization)

- Buatlah sebuah VM dengan kententuan
  - username: `<github_user>` contoh `dimasm93`
  - hostname: `<email_without_at>` contoh `dimas.tabeldata.com`
  - OS: `ubuntu-20.04` atau `centos-7`
- Install webserver `nginx`
- Buatlah web profile temen-temen kemudian deploy ke webserver nginx tersebut yang telah di deploy
  
(kirimkan hasil screenshotnya simpan dalam folder `screenshot` dengan nama `task1.png`)

## Task 2 (Container)

Jika saya memiliki architecture seperti berikut:

![container-apps](docs/images/01-container.png)

Dimana berikut adalah configurasi docker image:

1. Backend container
  - image: `dimmaryanto93/udemy-springboot-app:latest`
  - port: `8080`
  - env: 
    - `DATABASE_HOST`: `<ip-domain-db>`
    - `DATABASE_PORT`: `5432` 
    - `DATABASE_NAME`: `<db-name>`
    - `DATABASE_PASSWORD`: `<db-password>`
    - `APPLICATION_PORT`: `8080`
  need:
    - Database PostgreSQL v14.2
2. Frontend container
  - image: `dimmaryanto93/udemy-angular-app:latest`
  - port: `80`
  - env:
    - `APPLICATION_PORT`: `80`
    - `NGINX_ROOT_DOCUMENT`: `/var/www/html`
    - `BACKEND_HOST`: `<ip-backend-apps>`
    - `BACKEND_PORT`: `<port-backend-apps>`
    - `BACKEND_CONTEXT_PATH`: `/`
  - need:
    - Backend container

Silahkan buat docker-compose filenya, kemudian simpan dalam folder `tasks` dengan nama `docker-compose.yaml`

