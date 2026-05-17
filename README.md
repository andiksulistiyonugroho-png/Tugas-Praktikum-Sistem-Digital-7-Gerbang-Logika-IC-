#### Nama anggota kelompok 3 shift B :
 1. Andik Sulistiyo Nugroho (H1H025001)
 2. Safina Nabilatuz Zulfa (H1H025003)
 3. Agnisa Lintang Anjali (H1H025066)

---

#### Komponen Utama & Pola Dasar Pemasangan :
1. **Sumber Daya (Power Supply) :**
   <br>Diatur pada tegangan **5V**. Kabel **Merah** adalah Positif (VCC/5V) dan kabel **Hitam** adalah Negatif (GND/Ground).
2. **DIP Switch (Saklar) :**
   <br>Berfungsi sebagai input digital. 
   <br>- Saklar ke atas = **1 (HIGH / 5V)**
   <br>- Saklar ke bawah = **0 (LOW / GND)**
3. **Konfigurasi Pin IC :**
   <br>Setiap IC membutuhkan daya aktif pada pin sudutnya :
   <br>- **Pin 14 (Pojok Kanan Atas):** Dihubungkan ke jalur Positif VCC (Kabel Merah).
   <br>- **Pin 7 (Pojok Kiri Bottom):** Dihubungkan ke jalur Negatif Ground (Kabel Hitam).
4. **Indikator Output (LED & Resistor) :**
   <br>LED berfungsi sebagai indikator (Menyala = 1, Mati = 0). Resistor dipasang secara seri sebelum LED untuk membatasi arus (*current limiting*) agar komponen tidak rusak, dengan menggunakan Resistor (220 Ohm) ke semua IC.

*Catatan : pastikan pemasangan pada setiap kabel rapih dan bedakan warna-nya agar memudahkan saat pemasangan dan untuk menghindari kesalahan pembacaan pada pin*

<br>

#### Langkah pemasangan dan cara kerja 7 gerbang logika :

#### 1. Gerbang AND (IC 74HC08)
**Karakteristik :** Output akan bernilai `1` (LED menyala) **hanya jika kedua input** bernilai `1`.
<br>

* **Langkah Pemasangan :** 
  <br>1. Pasang IC 74HC08 pada *breadboard*. Hubungkan Pin 14 ke VCC dan Pin 7 ke GND.
  <br>2. Hubungkan Saklar 1 dan Saklar 2 menggunakan kabel kuning ke **Pin 1 (Input 1A)** dan **Pin 2 (Input 1B)**.
  <br>3. Hubungkan **Pin 3 (Output 1)** ke kaki Resistor, lalu sambungkan ke Anoda (kaki panjang) LED. Katoda LED dihubungkan ke GND.
  
* **Tabel Kebenaran :**
  | Input A | Input B | Output (LED) |
  | :---: | :---: | :---: |
  | 0 | 0 | 0 (MATI) |
  | 0 | 1 | 0 (MATI) |
  | 1 | 0 | 0 (MATI) |
  | 1 | 1 | **1 (NYALA)** |
* **Gambar Rangkaian**
<img width="464" height="379" alt="Screenshot 2026-05-15 123526" src="https://github.com/user-attachments/assets/7888e01f-757d-4a8f-8bc9-90966eb86509" />

#### 2. Gerbang OR (IC 74HC32)
**Karakteristik :** Output akan bernilai `1` jika **salah satu atau kedua** input bernilai `1`.
<br>

* **Langkah Pemasangan:**
  <br>1. Pasang IC 74HC32. Hubungkan daya (Pin 14 ke VCC, Pin 7 ke GND).
  <br>2. Tarik jalur dari Saklar 1 ke **Pin 1 (Input 1A)** dan Saklar 2 ke **Pin 2 (Input 1B)**.
  <br>3. Hubungkan **Pin 3 (Output 1)** melewati resistor pembatas arus menuju Anoda LED.
  
* **Tabel Kebenaran :**
  | Input A | Input B | Output (LED) |
  | :---: | :---: | :---: |
  | 0 | 0 | 0 (MATI) |
  | 0 | 1 | **1 (NYALA)** |
  | 1 | 0 | **1 (NYALA)** |
  | 1 | 1 | **1 (NYALA)** |
* **Gambar Rangkaian**
<img width="463" height="376" alt="Screenshot 2026-05-15 131050" src="https://github.com/user-attachments/assets/a74fd861-efa3-495c-9528-012a1f3fea4f" />

#### 3. Gerbang NOR (IC 74HC02)
* **Karakteristik :** Kebalikan dari OR. Output bernilai `1` **hanya jika semua input bernilai 0**.
IC 74HC02 memiliki susunan pin yang terbalik dibandingkan IC logika lainnya. **Pin 1 adalah Output**, sedangkan **Pin 2 dan Pin 3 adalah Input**.

* **Langkah Pemasangan:**
  <br>1. Pasang IC 74HC02, hubungkan Pin 14 ke VCC dan Pin 7 ke GND.
  <br>2. Hubungkan Saklar 1 ke **Pin 2 (Input 1A)** dan Saklar 2 ke **Pin 3 (Input 1B)**.
  <br>3. Hubungkan **Pin 1 (Output 1)** ke rangkaian resistor dan LED.

* **Tabel Kebenaran :**
  | Input A | Input B | Output (LED) |
  | :---: | :---: | :---: |
  | 0 | 0 | **1 (NYALA)** |
  | 0 | 1 | 0 (MATI) |
  | 1 | 0 | 0 (MATI) |
  | 1 | 1 | 0 (MATI) |
* **Gamabr Rangkaian**
<img width="739" height="566" alt="Screenshot 2026-05-15 134950" src="https://github.com/user-attachments/assets/3a6b9c1c-ea27-4666-a3c3-a3f8c8458713" />

#### 4. Gerbang NOT / Inverter (IC 74HC04)
* **Karakteristik:** Membalikkan nilai input tunggal (`1` menjadi `0`, `0` menjadi `1`).
* **Langkah Pemasangan :**
  <br>1. Pasang IC 74HC04. Hubungkan pin daya standar (14 ke VCC, 7 ke GND).
  <br>2. Pada rangkaian ini digunakan *DIP Switch dengan saklar tinggal* (tombol merah). Hubungkan terminal tombol ke **Pin 1 (Input 1)**.
  <br>3. Hubungkan **Pin 2 (Output 1)** ke resistor dan LED.
     
* **Tabel Kebenaran :**
  | Input | Output (LED) |
  | :---: | :---: |
  | 0 (Dilepas) | **1 (NYALA)** |
  | 1 (Ditekan) | 0 (MATI) |
* **Gambar Rangkaian**
<img width="657" height="514" alt="Screenshot 2026-05-15 133523" src="https://github.com/user-attachments/assets/88e39fdc-adff-40c9-87e7-d54be4f66d98" />

#### 5. Gerbang NAND (IC 74HC00)
* **Karakteristik :** Kebalikan dari AND. Output bernilai `0` **hanya jika semua input bernilai 1**.
* **Langkah Pemasangan :**
  <br>1. Pasang IC 74HC00. Hubungkan daya VCC (Pin 14) dan GND (Pin 7).
  <br>2. Sambungkan Saklar 1 dan 2 ke **Pin 1 (Input 1A)** dan **Pin 2 (Input 1B)**.
  <br>3. Hubungkan **Pin 3 (Output 1)** ke kaki input resistor penurun tegangan menuju LED.
     
* **Tabel Kebenaran :**
  | Input A | Input B | Output (LED) |
  | :---: | :---: | :---: |
  | 0 | 0 | **1 (NYALA)** |
  | 0 | 1 | **1 (NYALA)** |
  | 1 | 0 | **1 (NYALA)** |
  | 1 | 1 | 0 (MATI) |
* **Gamabr Rangkaian**
<img width="571" height="464" alt="Screenshot 2026-05-15 134228" src="https://github.com/user-attachments/assets/ba411aab-d190-4b98-8ba5-b2b9d636abdf" />

#### 6. Gerbang XOR (IC 74HC86)
* **Karakteristik :** *Exclusive OR*. Output bernilai `1` jika **kedua input memiliki nilai logika yang berbeda**.
* **Langkah Pemasangan :**
  <br>1. Pasang IC 74HC86. Hubungkan Pin 14 ke VCC dan Pin 7 ke GND.
  <br>2. Hubungkan Saklar 1 ke **Pin 1 (Input 1A)** dan Saklar 2 ke **Pin 2 (Input 1B)**.
  <br>3. Hubungkan **Pin 3 (Output 1)** secara seri dengan resistor menuju LED.
     
* **Tabel Kebenaran :**
  | Input A | Input B | Output (LED) |
  | :---: | :---: | :---: |
  | 0 | 0 | 0 (MATI) |
  | 0 | 1 | **1 (NYALA)** |
  | 1 | 0 | **1 (NYALA)** |
  | 1 | 1 | 0 (MATI) |
* **Gambar Rangkaian**
<img width="778" height="627" alt="Screenshot 2026-05-15 135815" src="https://github.com/user-attachments/assets/d384c465-4d28-4d00-b6eb-a4a63d528590" />

#### 7. Gerbang XNOR (Kombinasi IC 74HC86 + 74HC04)
* **Karakteristik :** Kebalikan dari XOR. Output bernilai `1` jika **kedua input bernilai sama** (sama-sama 0 atau sama-sama 1).
* **Pendekatan Rangkaian :** Karena tidak menggunakan IC XNOR tunggal, modul rangkaian ini dibuat dengan **melewatkan output XOR ke gerbang NOT (Inverter)**.
* **Langkah Pemasangan :**
  <br>1. Pasang kedua IC secara berdampingan: IC 74HC86 (XOR) dan IC 74HC04 (NOT). Hubungkan VCC dan GND pada kedua IC tersebut.
  <br>2. Hubungkan Saklar 1 dan Saklar 2 ke **Pin 1** dan **Pin 2** pada **IC XOR (74HC86)**.
  <br>3. Hubungkan **Pin 3 (Output XOR)** menggunakan kabel jumper menuju **Pin 1 (Input NOT)** pada **IC 74HC04**.
  <br>4. Ambil keluaran dari **Pin 2 (Output NOT)** pada IC 74HC04, lalu sambungkan ke rangkaian resistor dan LED pembatas arus.
     
* **Tabel Kebenaran :**
  | Input A | Input B | Hasil XOR | Output Akhir XNOR (NOT XOR) |
  | :---: | :---: | :---: | :---: |
  | 0 | 0 | 0 | **1 (NYALA)** |
  | 0 | 1 | 1 | 0 (MATI) |
  | 1 | 0 | 1 | 0 (MATI) |
  | 1 | 1 | 0 | **1 (NYALA)** |
* **Gambar Rangkaian**
<img width="558" height="565" alt="Screenshot 2026-05-15 140347" src="https://github.com/user-attachments/assets/c18748c8-50ec-43eb-a98b-329f62e1e52b" />

---

*Link Tinkercad : https://www.tinkercad.com/things/2rbzXxFRrMF-7-gerbang-logika-ic/editel?returnTo=https%3A%2F%2Fwww.tinkercad.com%2Fdashboard&sharecode=CyXh9FvdddFv0ObrKkWPpEmiV1nQIBuXhKJ7325rvTw*
