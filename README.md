# Jarkom-Modul-4-B12-2021

Anggota: Faisal Reza M (05111940000009)

Spesifikasi: harus ada screenshot, cara pengerjaan, kendala

## Cara pengerjaan
**Buat topografi**
![image](https://user-images.githubusercontent.com/11045113/143685901-8effe04e-67b6-4ac3-b150-16d047d9a951.png)

**Cari subnet-subnet yang ada**
![image](https://user-images.githubusercontent.com/11045113/143685993-eab465bf-cec8-4d4c-87e4-b183486c01cc.png)

### VLSM
**buat tree nya di app.diagrams.net**

![vlsm drawio](https://user-images.githubusercontent.com/11045113/143686124-0e24ce9d-cda3-4d96-b272-3d8ed40be011.png)

**letakkan di tabel, lalu hitung netmask dan broadcast addressnya**

![image](https://user-images.githubusercontent.com/11045113/143686929-91dfbe3b-4f1a-48ec-bcf0-dc6bc39b9a5b.png)

**konfigurasikan interface dan routing di CPT**
A4
di foosha, atur interface yang mengarah ke water7, masukkan subnet mask A5, dan ip subnet A5 + 1 (+ centang On, berlaku juga untuk interface2 selanjutnya)

![image](https://user-images.githubusercontent.com/11045113/143686976-9b363e60-5447-4b4b-bffe-16b889680511.png)

di water7, atur interface yang mengarah ke foosha, masukkan subnet mask A5, dan ip subnet A5 + 2

![image](https://user-images.githubusercontent.com/11045113/143687008-ab6d44d1-7e59-4c5d-9563-6fcc3119df63.png)

di water7, atur interface yang mengarah ke A4, masukkan subnet mask A4, dan ip subnet A4 + 1

![image](https://user-images.githubusercontent.com/11045113/143687074-4ebc8688-e29c-49c1-a8f1-dea09b56b172.png)

di CIPHER (client yang ada di A4), atur interface yang mengarah ke water7, masukkan subnet mask A4, dan ip subnet A4 + 2

![image](https://user-images.githubusercontent.com/11045113/143687142-27031c24-2244-4378-b765-b5efe3b256ee.png)

di foosha, tambahkan routing untuk subnet yang tidak bersentuhan langsung dengan foosha (subnet yang bersentuhan: A5, A6, A7, A8), dengan nexthop yaitu ip router mana yg harus dilewati untuk menuju subnet yang diinginkan

![image](https://user-images.githubusercontent.com/11045113/143687203-7c0c11b9-936e-4f76-a6e5-b09942af6130.png)

di water7, tambahkan routing untuk subnet di bawah dia yang tidak bersentuhan langsung dengan foosha (subnet yang bersentuhan: A3 dan A4), yaitu A1 dan A2

lalu, di water7, tambahkan juga routing dengan network dan mask 0.0.0.0 dan next hop router yang tepat berada di atasnya (ini juga perlu ditambahkan ke tiap router lain yang tidak bersentuhan dengan NAT/Cloud)

![image](https://user-images.githubusercontent.com/11045113/143687291-504c96b2-4801-4970-8a09-ce4dcd400743.png)

**Lakukan hal yang sama untuk setiap subnet yang ada (untuk subnet a2, karena ada 2 end client, maka client1 menggunakan ip subnet + 2, dan client2 menggunakan ip subnet + 3)**

**tes dengan mengirim paket**

![image](https://user-images.githubusercontent.com/11045113/143686461-dec5c004-7245-466f-8825-e0c65d424047.png)
![image](https://user-images.githubusercontent.com/11045113/143686462-e5b9d86c-255e-44c6-9a59-39636fbb61ba.png)
![image](https://user-images.githubusercontent.com/11045113/143686463-51744a3f-e20d-4b3f-beab-5d91ef493946.png)


## Kendala
- praktikum sendirian sehingga tidak bisa bagi tugas
