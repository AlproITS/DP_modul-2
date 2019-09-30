# Array dan String

# Array

Adalah kumpulan data bertipe sama yang menggunakan nama sama. Dengan menggunakan array, sejumlah variabel dapat memakai nama yang sama. Antara satu variabel dengan variabel lain di dalam array dibedakan berdasarkan indexnya.

## Array Satu Dimensi

Merupakan kumpulan data yang bernama sama dengan pembeda sebuah indeks. Contoh penggunaan array satu dimensi :
```c
int main () {

  int a[10]; //Deklarasi Array
  
  int b[10] = {}; //Deklarasi Array Kosong
  
  a[0] = 50;
  a[1] = 20;
  
  printf("%d %d\n", a[0], a[1]);
  
  return 0;

}
```
Array pertama kali dideklarasikan seperti halnya variabel biasa, tetapi dengan kapasitas di dalam kurung siku, isi array yang bisa diakses adalah antara 0 sampai kapasitas-1, jadi jika mendeklarasikan array berkapasitas 10, indeks yang bisa diakses hanya indeks 0 sampai 9. Kemudian assign dan akses isi array sama dengan variabel biasa, tetapi menggunakan indeks.

Mengapa perlu array? Andaikan kita membutuhkan 1000 inputan data, kita tidak perlu membuat deklarasi variabel a1 hinga a1000, kita cukup menuliskan 1 variabel a dengan tipe array berkapasitas 1000.

Contoh program tanpa array:
```c
int main () {

  int a, b, c, d, e; //Deklarasi 5 variabel integer
  
  scanf("%d %d %d %d %d", &a, &b, &c, &d, &e);
  
  printf("Bilangan pertama adalah %d\n, a);
  printf("Bilangan kedua adalah %d\n, b);
  printf("Bilangan ketiga adalah %d\n, c);
  printf("Bilangan keempat adalah %d\n, d);
  printf("Bilangan kelima adalah %d\n, e);
  return 0;

}
```

Bayangkan kita tidak hanya memasukkan 5 data, melainkan 1000 data, bagaimana kita mendeklarasikan semuanya dalam variable dan kemudian mencetaknya? Maka dari itulah array digunakan.

Contoh program menggunakan array:
```c
int main () {

  int a[5], i;
  
  for(i = 0; i < 5; i++) scanf("%d", &a[i]); //Input array
  
  for(i = 0; i < 5; i++) prinf("Bilangan ke-%d adalah %d\n", i+1, a[i]; // Output array
  
  return 0;

}
```

## Array Multidimensi

Array Multidimensi adalah array yang dapat menampung lebih dari satu array. Apabila array satu dimensi hanya memiliki sebuah index, array multidimensi memiliki dua atau lebih index untuk mengakses seluruh elemen dalam array tersebut. 
Contoh program dengan array dua dimensi:
```c
int main () {

  int matriks[10][10];
  
  matriks[2][3] = 100;
  
  printf("%d\n", matriks[2][3]);
  
  return 0;

}
```
Apabila program diatas dibuat dengan menggunakan array satu dimensi, maka setiap baris pada matriks tersebut harus dideklarasikan sebagai variabel yang berbeda (misal: matriks1[100], matriks2[100], matriks3[100], dst). Tentunya hal ini akan sangat sulit diimplementasikan ditambah lagi apabila baris pada matriks ditentukan oleh user yang menggunakan program dan jumlah baris tersebut sangat besar.

# String

String adalah tipe data yang menyimpan kumpulan karakter/simbol. Dalam bahasa pemrograman C, suatu string dideklarasikan sebagai array yang bertipe char.

Contoh pendeklarasian string (1):
```c
#include <stdio.h>

int main () {
  
  char array[] = "Halo";
  
  return 0;

}
```

Contoh di atas akan mendeklarasikan string bernama array dengan kapasitas 5 karakter, di mana array[0] = 'H', array[1] = 'a', array[2] = 'l', array[3] = 'o', dan array[4] = '\0'.
Perhatikan bahwa array[4] berisi karakter '\0' (null character), padahal dalam konstanta string di atas tidak ada karakter tersebut. 

Dalam bahasa C, null character digunakan untuk menandakan akhir dari sebuah string.

Contoh pendeklarasian string (2):
```c
#include <stdio.h>

int main () {
  
  char array[10];
  
  return 0;

}
```

Contoh di atas akan mendeklarasikan string bernama array yang dapat menampung maksimal 10 karakter, termasuk null character.

Untuk menerima inputan string dari user, kita dapat menggunakan scanf atau gets. Perintah scanf akan membaca inputan string dari user dan berhenti ketika ada spasi, enter (newline) ataupun interupsi dari pengguna. Sedangkan gets akan membaca satu baris kumpulan karakter hingga enter atau interupsi dari pengguna.

Contoh source code penggunaan scanf untuk membaca string:
```c
#include <stdio.h>

int main () {
  
  char array[10];
  while(true)
  {
    scanf("%s", arr);
    
    printf("-- %s\n", arr);
  }
  return 0;

}
```

Contoh penggunaan gets untuk membaca string:
```c
#include <stdio.h>

int main () {
  
  char array[100];
  while(true)
  {
    gets(arr);
    
    printf("-- %s\n", arr);
  }
  return 0;

}
```
String yang dibaca dengan mengunakan scanf atau gets akan secara otomatis memiliki null character di akhir stringnya.

## Fungsi-Fungsi String

Dalam bahasa pemrograman C, terdapat library yang dibuat dengan tujuan memudahkan pengguna dalam mengolah string. Library tersebut tersimpan dalam string.h, oleh karena itu, untuk mengakses library ini, diperlukan tambahan, yaitu:
#include <string.h>
Berikut adalah fungsi-fungsi yang dibagi berdasarkan kegunaannya dalam mengolah sebuah string (diambil dari www.cplusplus.com):
- Copying :
  + memcpy (Copy block of memory)
  + memmove (Move block of memory)
  + strcpy (Copy string)
  + strncpy (Copy characters from string)
- Concatenation :
  + strcat (Concatenate strings)
  + strncat (Append character from string)
- Comparison :
  + memcmp (Compare two blocks of memory)
  + strcmp (Compare two strings)
  + strcoll (Compare two strings using locale)
  + strncmp (Compare characters of two strings)
  + strxfrm (Transform string using locale)
- Searching :
  + memchr (Locate character in block of memory)
  + strchr (Locate first occurrence of character in string)
  + strcspn (Get span until character in string)
  + strpbrk (Locate characters in string)
  + strrchr (Locate last occurrence of character in string)
  + strspn (Get span of character set in string)
  + strstr (Locate substring)
  + strtok (Split string into tokens)
- Other :
  + memset (Fill block of memory)
  + strerror (Get pointer to error message string)
  + strlen (Get string length)

### Fungsi strcpy 
```c
char * strcpy ( char * destination, const char * source );
```
Fungsi strcpy digunakan untuk melakukan copy dari sebuah string ke string lainnya. 
Contoh penggunaan dalam kode program:
```c
#include <stdio.h>
#include <string.h>

int main () {
  
  char a[] = "Halo";
  char b[10];
  
  // Copy string a ke string b
  strcpy(b, a);
  
  printf("%s\n", b);
  
  return 0;

}
```

### Fungsi strcat 
```c
char * strcat ( char * destination, const char * source );
```
Fungsi strcat digunakan untuk melakukan penempelan sebuah string pada akhir suatu string tertentu. 
Contoh penggunaan dalam kode program:

```c
#include <stdio.h>
#include <string.h>

int main () {
  
  char a[] = "Halo";
  char b[] = " Kawan";
  char c[20];
  
  // Copy string a ke string b
  strcpy(c, a);
  
  // Tempelkan string b ke akhir string c
  strcat(c, b);
  
  printf("%s\n", c);
  
  return 0;

}
```

### Fungsi strcmp
```c
int strcmp ( const char * str1, const char * str2 );
```
Fungsi strcmp digunakan untuk melakukan pembandingan sebuah string dengan string yang lain. Return value dari fungsi ini dapat berupa bilangan negatif, nol ataupun positif. Jika fungsi ini mengembalikan nilai negatif, maka str1 memiliki tingkat leksikoglafi lebih kecil dari str2. Sedangkan jika fungsi ini mengembalikan nilai postifi, maka str1 memiliki tingkat leksikografi lebih besar dari str2. Terakhir, jika return value nya nol, maka str1 sama dengan str2. 

Berikut adalah contoh penggunaan fungsi ini dalam kode progam:
```c
#include <stdio.h>
#include <string.h>

int main () {
  
  char a[] = "Halo";
  char b[] = "Hai";
  char c[] = "Halo;
  
  if(strcmp(a, b) == 0) printf("String a sama dengan b\n");
  else printf("String a tidak sama dengan b\n");
  
  if(strcmp(a, c) == 0) printf("String a sama dengan c\n");
  else printf("String a tidak sama dengan c\n");
  
  return 0;

}
```

### Fungsi strlen
```c
size_t strlen ( const char * str );
```
Fungsi strlen digunakan untuk mengetahui panjang dari sebuah string.
```c
#include <stdio.h>
#include <string.h>

int main () {
  
  char a[] = "Halo";
  
  printf("Panjang string a adalah %d\n", strlen(a));
  
  return 0;

}
```

## Soal Latihan

### Soal 1

Buatlah program untuk mencetak N buah angka yang diinput secara terbalik. Input baris pertama adalah N yang merupakan banyaknya angka yang akan diinput. Baris berikutnya terdapat N buah angka (dipisahkan spasi).

**Contoh Input**

```
5
1 4 3 2 9
```

**Contoh Output**

```
9
2
3
4
1
```
### Soal 2

Buatlah sebuah program untuk menghitung jumlah huruf vokal yang terdapat pada sebuah string S. Panjang string S tidak melebihi 100 karakter dan terdiri dari huruf lowercase, uppercase dan spasi.

**Contoh Input**

```
Dasar Pemograman Keren
```

**Contoh Output**

```
A/a : 4
I/i : 0
U/u : 0
E/e : 3
O/o : 1
```

### Soal 3

Diberikan sebuah nama variabel dalam bentuk **snake_case**. Buatlah program untuk mengubah nama variabel tersebut menjadi bentuk **camelCase**. Nama variabel hanya terdiri dari huruf lowercase, uppercase, dan simbol underscore.

**Contoh Input 1**

```
skor_pemain
```

**Contoh Output 1**

```
skorPemain
```

**Contoh Input 2**

```
VariabEl_Satu
```

**Contoh Output 2**

```
variabelSatu
```
