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
