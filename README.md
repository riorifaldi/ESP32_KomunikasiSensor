﻿# ESP32_KomunikasiSensor

ESP32 adalah nama dari mikrokontroler yang dirancang oleh perusahaan yang berbasis di Shanghai, China yakni Espressif Systems. ESP32 menawarkan solusi jaringan WiFi dan BLE. ESP32 menggunakan prosesor dual core yang berjalan di instruksi Xtensa LX16. Selain itu, ESP32 telah mendukung protokol komunikasi seperti I2C, UART dan SPI.

**ALAT DAN BAHAN**
1) ESP32
2) Breadboard
3) Kabel jumper
4) Sensor DHT 11, RFID
5) LED (5) dan Push Button (3)
6) Servo
7) Resistor 330,1K, 10K Ohm (@ 3)


**1) ESP32 Capacitive Touch Sensor**

**Contoh**


https://user-images.githubusercontent.com/41616849/209112987-79b2e3e8-2d4d-4be9-9859-ab05ffb474a3.mp4

Analisa : <br />
Dari contoh tersebut ESP32 dapat digunakan sebagai Touch Sensor dimana kondisi saat kabel jumper disentuh, akan menghasilkan data pada serial plotter. Ketika sensor (kabel) tidak disentuh nilai pada serial plotter akan tinggi sedangkan saat sensor (kabel) disentuh maka serial plotter akan rendah

**Kemudian Buatlah Rangkaian dibawah ini** <br />
![image](https://user-images.githubusercontent.com/41616849/209115047-caf5c1ad-eff1-460f-a123-e68a182a7acd.png)  <br />

**Keluaran** <br />
a) Lampu LED On saat disentuh dan Off saat tidak disentuh <br />



https://user-images.githubusercontent.com/41616849/209116914-23ed1904-4a93-4208-83cf-e4585ddd020b.mp4  

Analisa : <br />
Dari contoh diatas kita dapat mengimplementasikan nilai serial plotter untuk menghidupkan dan menyalkan lampu LED dengan perintah if else pada program yang menghasilkan LED akan menyala ketika sensor disentuh dan akan mati ketika sensor tidak disentuh. <br />

b) Lampu LED akan menyala Blink saat disentuh <br />

https://user-images.githubusercontent.com/41616849/209118112-209c4f1b-6ab5-4fd4-a3d7-191cad0f9403.mp4

Analisa : <br />
Percobaan kali ini masih mengimplementasikan hasil serial plotter tetapi pada programnya dapat diatur seingga ketika sensor disentuh maka LED akan menyala BLINK dan mati ketika sensor tidak disentuh. <br />

c) Ketika LED menyala Serial Monitor akan menampilkan angka yang bertambah tiap kali sensor disntuh <br />

https://user-images.githubusercontent.com/41616849/209118853-09e14b7a-6ba7-4bcd-b8e3-85f5d5f1969e.mp4

Analisa : <br />
Percobaan kali ini menghasilkan data ketika sensor disentuh, maka akan mengirimkan data untuk menambahkan angka yang akan tampil pada serial monitor. <br />

d) Lampu LED akan menyala Running saat sensor disentuh <br />

https://user-images.githubusercontent.com/41616849/209119462-2cac19fa-6147-4143-8977-80bca4ee5a50.mp4

Analisa : <br />
Pada percobaan ini program diubah sehingga ketika sensor disentuh maka LED akan menyala running dari kiri ke kanan, kemudian kanan ke kiri secara continue <br />

**2) DHT 11 Sensor** <br />
Pada Percobaan kali ini menggunakan sensor suhu dan kelembapan DHT 11 yang dapat menghasilkan data sehingga dapat disimpan pada ESP32. Untuk rangkaiannya seperti ini <br />
![image](https://user-images.githubusercontent.com/41616849/209120548-e0bac69c-7d9b-4002-87f5-0a7e16526ae0.png) <br />
rangkaian diatas kemudian ditambah buzzer yang akan berbunyi saat sensor membaca suhu 30 derajat celcius dan 3 buah LED yang akan menyala running saat suhu dibawah 30 derajat celcius <br />

https://user-images.githubusercontent.com/41616849/209121035-1647dcfe-ee5e-407e-94fe-a8e10e025bea.mp4

Analisa : <br />
Dengan data yang didapat sensor DHT 11 kita dapat membuat program untuk memberikan sebuah state pada keadaan tertentu. <br />

**3) Sensor RFID**

**Buatlah rangkaian seperti berikut**

![image](https://user-images.githubusercontent.com/41616849/209123901-b261bf28-8be5-443a-aadf-cb393fa20e94.png)


Keluaran 

![image](https://user-images.githubusercontent.com/41616849/209123721-e27870b9-23ab-4e33-afd5-f146bd19903d.png)


**Kondisi apabila Tag RFID didekatkan pada Reader, maka LED Hijau akan menyala, servo akan bergerak ke kanan (lalu kembali ke posisi semula setelah 3 detik) dan di Serial Monitor akan menampilkan pesan “Akses Diterima, Silahkan Masuk”. Apabila Tag RFID tidak dikenali, maka LED Merah akan menyala, servo tidak bergerak dan di Serial Monitor akan menampilkan pesan “Akses Ditolak”**

Keluaran 

https://user-images.githubusercontent.com/41616849/209267160-384c77bf-cb98-4829-82b5-d5c539dcbece.mp4

Analisa : <br />
Setelah mengetahui tentang cara kerja RFID kita bisa tambahkan motor servo. Ketika kartu akses diterima maka ESP32 akan mengirimkan data pada motor servo untuk berputar 180 derajat selama 3 detik lalu kembali ke posisi awal dan menyalakan LED hijau, sedangkan ketika kartu akses ditolak maka lampu LED merah yang akan menyala
