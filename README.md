# writing-presentation-week-2

## Javascript - Scope<br>
### Pengertian Scope
> Scope adalah konsep dalam flow data variabel.
### Blocks
> Blocks adalah code yang berada didalam curly braces {}.
### Global Scope
- Global scope berarti variabel yang kita buat dapat diakses dimanapun dalam suatu file.
- Agar menjadi Global Scope, suatu variabel harus dideklarasikan diluar Blocks.
- Contoh Global Scope
  ```Javacript
  let MyName = 'Yohanes'
  function greeting(){
      return myName
  }
  
  console.log(myName) //Output: Yohanes
  ```
### Local Scope
- Local scope berarti kita mendeklarasikan variabel didalam blocks seperti function, conditional, dan looping.
- Variabel hanya bisa diakses didalam blocks saja. Tidak bisa diakses diluar blocks.
- Contoh Local Scope
  ```Javascript
  function greeting(){
      let MyName = 'Yohanes'
      return myName
  }
  
  console.log(greeting())
  greeting(myName)
  ```
  <br>
## Javascript - Function<br>
### Pengertian Function
> Function adalah sebuah blok kode dalam sebuah grup untuk menyelesaikan 1 task/1 fitur.
### Membuat Function
```Javascript
function greeting(){
    return 'Hello World'
}
```
Penjelasan :
- function adalah function keyword.
- greeting adalah identifier.
- { return 'Hello World' } adalah function body
### Memanggil Function
```Javascript
    greeting()
    console.log(greeting())
```
### Parameter dan Argumen
- Parameter Function
  - Dengan parameter, function dapat menerima sebuah inputan data dan menggunakannya untuk melakukan task/tugas.
  - Saat membuat function/fitur, kita harus tahu data-data yang dibutuhkan. Misalnya saat membuat function penambahan 2 buah nilai. Data yang dibutuhkan adalah 2 buah nilai tersebut.
  - Contoh Parameter Function
    ```Javascript
    function tambah(a, b){
        return a + b
    }
    ```
    Penjelasan :
    > a, b adalah parameter
- Argumen Function
  - Argumen adalah nilai yang digunakan saat memanggil function.
  - Jumlah argumen harus sama dengan jumlah parameternya
  - Jadi jika di function penambahan ada 2 parameter nilai saat membuat function. Saat memanggil function kita gunakan 2 buah nilai argumen.
  - Contoh Argumen Function
    ```Javascript
    function tambah(a, b){
        return a + b
    }
    
    console.log(tambah(10, 6)) //Output: 16
    ```
    penjelasan :
    > 10, 6 adalah argumen sebagai nilai
- Default Parameters
  - Default paramaters digunakan untuk memberikan nilai awal/default pada parameter function.
  - Default parameters bisa digunakan jika kita ingin menjaga function agar tidak error saat dipanggil tanpa argumen.
  - Contoh Default Parameter
    ```Javascript
    function sapa(nama = 'orang'){
        return 'Halo' + nama
    }
    
    console.log(sapa('Yohanes'))
    console.log(sapa())
    ```
- Function Helper
  - Kita bisa menggunakan function yang sudah dibuat pada function lain.
  - Contoh Function Helper
    ```Javascript
    function tambah(nomor){
        return nomor * 10
    }
    function bagi(number){
        return tambah(number) / 2
    }
    
    bagi(10) //Returns 50
- Arrow Function
  - Arrow function adalah cara lain menuliskan function. Ini adalah fitur terbaru yang ada pada ES6 (Javascript Version)
  - Contoh Arrow Function
    ```Javascript
    const sapa = () => {
        return 'Hello World'
    }
    
    const tambah = (a, b) = {
    return a + b
    }
    ```
- Short Syntax Function
  - Nol Parameter
    ```Javascript
    const functionName = () => {}
    ```
  - Satu Parameter
    ```Javascript
    const functionName = paramOne = {}
    ```
  - Dua atau lebih Parameter
    ```Javascript
    const functionName = (paramOne, paramTwo) => {}
    ```
  - Single Line Block
    ```Javascript
    const sumNumber = number => number +number
    ```
  - Multi-Line Block
    ```Javascript
    const sumNumber = number => {
        const sum = number + number;
        return sum;
    }
    ```
    <br>
## Errors dan Debugging<br>
### Error
- Error objek dilempar ketika kesalahan runtime terjadi. Objek Errorjuga dapat digunakan sebagai objek dasar untuk pengecualian yang ditentukan pengguna.
- Kesalahan runtime menghasilkan Errorobjek baru yang dibuat dan dibuang.
- Tipe - Tipe Error
  - EvalError
    <br>Membuat instance yang mewakili kesalahan yang terjadi terkait fungsi global eval().
  - RangeError
    <br>Membuat instance yang mewakili kesalahan yang terjadi saat variabel numerik atau parameter berada di luar rentang validnya.
  - ReferenceError
    <br>Membuat instance yang mewakili kesalahan yang terjadi saat mereferensikan referensi yang tidak valid.
  - SyntaxError
    <br>Membuat instance yang mewakili kesalahan sintaks.
  - TypeError
    <br>Membuat instance yang mewakili kesalahan yang terjadi saat variabel atau parameter bukan tipe yang valid.
  - URIError
    <br>Membuat instance yang mewakili kesalahan yang terjadi saat encodeURI()atau decodeURI()melewati parameter yang tidak valid.
  - AggregateError
    <br>Membuat instance yang mewakili beberapa kesalahan yang dibungkus dalam satu kesalahan ketika beberapa kesalahan perlu dilaporkan oleh suatu operasi, misalnya oleh Promise.any().
  - InternalError
    <br>embuat instance yang mewakili kesalahan yang terjadi saat kesalahan internal di mesin JavaScript dilemparkan. Misalnya "terlalu banyak rekursi".
- Constructor
  <br> Membuat Error objek baru.
- Metode Statis
  - Error.captureStackTrace()
  - Error.stackTraceLimit
  - Error.prepareStackTrace()
- Instance Properties
  - Error.prototype.message
  - Error.prototype.name
  - Error.prototype.cause
### Debugging
- Cara Debugging Javascript
  - Cara termudah dan mungkin yang paling umum adalah dengan console.log() variabel yang ingin Anda periksa
  - Menggunakan alat pengembang chrome, buka halaman Anda dengan kode JS Anda (tekan cmd+o di macOS atau Ctrl+o di Windows) dan pilih file Anda untuk di-debug, klik baris yang ingin Anda debug dan segarkan kembali halaman Anda (F5).
- Call Stack
  - Jalur yang telah diambil program Anda untuk mencapai titik saat Anda menetapkan titik putus atau Anda mengalami kesalahan.
  - Contoh Call Stack
    (function testing(){
        var obj = {
        add
    }
    function add(a, b) {
        var result = a + b
        return result.split('')
    }
    var stringResult = obj.add("1", "2") // stringResult becomes "12"
    var numberResult = obj.add(1, 2) // numberResult is never set, an error is thrown
    })()
    ```
    Penjelasan :
    - testing dipanggil secara otomatis karena ini adalah IIFE (immediately Invoked Function Expression);
    - variabel obj dideklarasikan dengan function add (menggunakan ES6 shorthand untuk fungsi dalam objek, itu akan sama dengan memiliki var obj = { add: add };
    - function add dipanggil dari variabel obj dengan dua string memiliki parameter, ada yang ditambahkan yang menjadikannya "12" dalam skenario ini dan kemudian split dipanggil sebelum mengembalikan ["1", "2"];
    - function add dipanggil lagi, kali ini dengan angka, nilai ditambahkan sehingga menjadi 3 tetapi kemudian, split (yang tidak tersedia untuk variabel tipe angka ) dipanggil yang membuat error dilemparkan;
- Alat untuk menghindari runtime errors
  - quokka untuk mengevaluasi kode pada saat mengetik
  - eslint untuk memastikan panduan gaya konsisten dan itu akan membawa satu atau dua kesalahan di sepanjang mengoding
  - Bagi Anda yang ingin menjadikan JS pengalaman mengetik yang lebih kuat, Anda dapat melihat hal-hal seperti TypeScript (seperti yang saya katakan di artikel sebelumnya, ketika belajar saya lebih suka menghindari perpustakaan yang mengabstraksi bahasa inti jadi saya tidak akan merekomendasikan yang terakhir ini ketika mulai).<br>
## Javascript Dasar - Data Type Built in Prototype and Method<br>
### Data Type
Data Primitive
1. String 
   - Deretan karakter yang diapit oleh sepasang tanda kutip (" "), berguna untuk menyimpan data yang dapat direpresentasikan dalam bentuk teks
   - Properties

     1. Constructor
        <br>Mengembalikan fungsi yang dibuat string prototipe objek
     2. Length
        <br>Mengembalikan panjang string JavaScript
        ```
        const str = 'skilvul';
        console.log(str.length); // Output: 7
        ```
     3. Prototype
        <br>Menambah metode dan properti ke dalam sebuah objek
        ```
        String.prototype.reverse = function(){ 
          let s = " "    
          for (let i = String(this).length-1; i >= 0; i-- { 
            s = s + String(this)[i]
          } 
          return s 
        }
        console.log("hallo".reverse()) //Output: 'ollah'
        ```
   - Method
     1. charAt()
        <br>Mengembalikan karakter pada index yang spesifik (posisi)
        ```
        let hewan = 'Dinosaurus';
        console.log(hewan.charAt(4)); //Output : s
        ```
     2. indexOf()
        <br>Kembalikan posisi kemunculan pertama yang ditemukan dari teks yang ditentukan dalam sebuah string
        ```
        const str = 'saya sedang belajar javascript';
        console.log(str.indexOf('a')); // 1 :: s(a)ya ... 
        console.log(str.indexOf('ja')); // 16 :: ... bela(ja)r javascript
        ```
     3. lastIndexOf()
        <br>Kembalikan posisi kemunculan terakhir yang ditemukan dari teks yang ditentukan dalam sebuah string
        ```
        const str = 'saya sedang belajar javascript';
        console.log(str.lastIndexOf('a')); // 23 :: ... belajar jav(a)script
        console.log(str.lastIndexOf('ja')); // 20 :: ... belajar (ja)vascript
        console.log(str.lastIndexOf('ja', 19)); // 16 :: ... bela(ja)r javascript
        ```
     4. replace()
        <br>Cari string untuk nilai dan kembalikan string baru dengan nilai yang diganti
        ```
        const str = 'aku sedang belajar javascript';
        console.log(str.replace('aku', 'saya')); // saya sedang belajar javascript
        ```
     5. slice()
         <br>Ekstrak bagian dari string dan kembalikan string baru
         <br>Sintaks : slice(indeksAwal, indeksAkhir);
         ```
         const str = 'saya sedang belajar javascript';
         console.log(str.slice(5, 11)); // sedang
         console.log(str.slice(5)); // sedang belajar javascript
         ```
     6. split()
         <br>Memisahkan string ke dalam array substring
         <br>Sintaks : split(separator, limit);
         ```
         const str = 'saya sedang belajar javascript';
         console.log(str.split()); // ["saya sedang belajar javascript"]
         console.log(str.split(' ')); // ["saya", "sedang", "belajar", "javascript"]
         console.log(str.split(' ', 2)); //  ["saya", "sedang"]
         ```
     7. substring()
         <br>Ekstrak bagian dari string antara dua posisi yang ditentukan
         ```
         const str = 'saya sedang belajar javascript';
         console.log(str.substring(1, 3)); // ay
         console.log(str.substring(5)); // sedang belajar javascript
         ```
     8. toLowerCase()
         <br>Ubah string menjadi huruf kecil
         ```
         const str = 'Skilvul';
         console.log(str.toLowerCase()); //Output: skilvul
         ```
     9. toUpperCase()
         <br>Ubah string menjadi huruf besar
         ```
         const str = 'skilvul';
         console.log(str.toUpperCase()); //Output: SKILVUL
         ```
     10. trim()
         <br>Hapus spasi dari kedua ujung string
         ```
         const str = '     skilvul      ';
         console.log(str.trim()); // 'skilvul'
         ```
     11. includes()
         <br>mengembalikan nilai true or false apalah dalam variabel ada string tersebut
         ```
         let hewan = "Dinosaurus"
         console.log(hewan.includes("saur"); // Output : true
         ```     
2. number
   > Bilangan bulat, pecahan, dan lain-lain yang berbentuk angka
     ```
     const a = 19;
     console.log(a); // 19
     console.log(typeof a); // number
     console.log(a instanceof Number); // false    
     ```
     - Properties (jarang digunakan, kebanyakan menggunakan methods number)
     - Methods
        1. isNan() --> NaN (Not a Number)
        <br>Mengecek apakah ini bukan angka. Mengembalikan nilai Boolean, true jika nilai yang diuji NaN(bukan angka), false jika angka
        ```
        isNan("hallo") //true
        isNan(12345) //false, karena ini angka
        isNan(true) //false, karena boolean true dianggap sebagai 1, dan 1 itu termasuk angka
        isNan("12345") //false, karena ada angka didalam string
        ```
        2. toString()
        <br>Untuk mengubah angka menjadi string
        ```
        let angka = 25
        angka.toString() //Output: '25'
        ```
        3. toFixed()
        <br>Dapat menentukan jumlah angka dibelakang tanda koma. Return nilainya berupa string
        ```
        let pi = 3.14159265
        pi.toFixed() //Output: '3'
        pi.toFixed(1) //Output: '3.1'
        pi.toFixed(4) //Output: '3.1415'
        ```
        4. parseInt() dan Number()
        <br>Mengubah string menjadi number
        ```
        myString = "27";
        console.log(parseInt(myString)); // Output: 27
        console.log(Number(myString)); //Output: 27
        ```
 - Data Non-Primitive
  1. Object
  <br> contoh:
     ```
     let a = [10]
     let b = a
     console.log(a === b) // true
     a.push(10)
     console.log(a) // [10, 10]
     console.log(a === b) // true
     ```
  2. Array
  3. Function
### Math
<br> mempermudah dalam perhitungan matematika
<br> contoh :
```
Math.pi //Output: 3.1415
Math.LOG2E //Output: 1.4426
Math.sqrt2 //Output: 1.4426 {menghitung akar dua}
```
   - Methods Math
   1. Math.abs()
      <br> mengembalikan nilai negatif menjadi nilai positif
      ```
      Math.abs(-13) //Output: 13     
      ```
   2. Math.pow()
      <br> menghitung pangkat
      ```
      Math.pow(3, 2) //Output: 9
      ```
   3. Math.sqrt()
      <br> menghitung akar
      ```
      Math.sqrt(9) //Output: 3
      ```
   4. Math.round()
      <br> membulatkan angka
      ```
      Math.round(123.456) //Output: 123
      ```
   5. Math.floor()
      <br> membulatkan angka kebawah
      ```
      Math.floor(4.4) //Output: 4
      Math.floor(4.9) //Output: 4
      ```
   6. Math.ceil()
      <br> membulatkan angka keatas
      ```
      Math.ceil(5.6) //Output: 6
      Math.ceil(5.1) //Output: 6
      ```
   7. Math.random()
      <br> menampilkan angka acak
