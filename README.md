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
