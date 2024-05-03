# Welcome to ZENITH 2 🧘

## Sudahkah kalian tahu struktur data pada Python? 😁
> harusnya sudah ya, dipertemuan terakhir sudah kita bahas :"

#### Ada apa aja hayooo? 🤓 
Terdapat 4 struktur data pada pemrograman bahasa Python, ada list, tuple, set dan dictionary

#### Masih ingat tidak apa perbedaannya? 🤔
| Struktur Data | Sekuensial? | Dapat Diubah? | Example |
|---------------|--------------|------------|---------|
 List          | ✅           | ✅         | `[1, 2, 3, 4, 5]` |        
| Set           | ✅           | 🚫      | `{1, 2, 3, 4, 5}` |        
| Tuple         | 🚫        | ✅         | `(1, 2, 3, 4, 5)` |        
| Dictionary    | ✅           | 🚫      | `{'a': 1, 'b': 2, 'c': 3}` |
> Sederhananya perbedaannya adalah seperti tabel diatas
#### Kenapa kita perlu mengetahui struktur data? 🤔 
*Emang ada hubungannya kah dengan yang nantinya kita pelajari dalam mengolah data?*
#### Jelas ada Dong 🤗
*Berikut beberapa contoh penerapan struktur data python pada data preprocessing*
## Columns filtering using `List`
Semisal kita punya Dataframe seperti berikut:

|   Name |   Age | Birthdate   | City        |
|--------|-------|-------------|-------------|
|   John |    25 | 1996-05-10  | New York    |
|  Alice |    30 | 1992-08-20  | Los Angeles |
|    Bob |    35 | 1987-12-05  | Chicago     |
|    Eve |    40 | 1982-04-15  | Seattle     |

Kita bisa melakukan hal seperti ini
```
date_col = ['Birthdate']
object_columns = [col for col in df.select_dtypes(include='O')]
num_columns = [col for col in df.select_dtypes(exclude='O') if col not in date_col]
```
Dan akan mendapatkan hasil seperti ini
```
Object Columns: ['Name', 'Birthdate', 'City']
Numeric Columns: ['Age']
Date Columns: ['Birthdate']
```
#### Emang apa manfaatnya?
Pada real case tidak menutup kemungkinan bahwa data yang kita miliki mempunyai banyak kolom atau feature, 
#### Emang kenapa kalo banyak fitur/kolom?
Dengan banyaknya feature tersebut memiliki kemungkinan bahwa terdapat berbagai jenis tipe data seperi `date`, `int/float` dan `kategorikal`
#### Emang kenapa kalo tipe datanya berbeda-beda?
Berbeda tipe data artinya berbeda juga cara menanganinya pada data preprocessing
#### Contoh
Misalnya terdapat pada missing value pada fitur kategorikal data kita, kita melakukan imputasi dengan teknik modus `mengisi null value dengan nilai modus pada kolom`
#### Tetapi apakah hal tersebut juga berlaku untuk kolom numerik? 
Dalam melakukan imputasi pada data numerik tentunya mempunyai teknik yang berbeda (`mean atau median`)
#### Wah jadi penting sekali ya?
Tentu saja, hal tersebut juga bisa kita aplikasikan apabila kita ingin memvisualisasikan keseluruhan kolom sesuai dengan jenis datanya `(casenya kita sedang memantau hubungan setiap variabel numerik dengan kolom jumlah belanja)`
#### Alih-alih memvisualisasikannya satu-satu, seperti kode berikut 
`advanced_scatter_plot('pendapatan', 'jumlah_belanja, TARGET, df)`
kita bisa membuat fungsi tersebut untuk dimasukkan ke dalam perulangan, dimana perulangan tersebut akan berjalan iterasinya selama banyaknya kolom yang mau di visualisasikan
#### Sekarang bayangin kalo menggunakan data real
contohnya data yang terkenal di kompetisi kaggle
[House Price Prediction](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques/data?select=train.csv), data ini memiliki total 81 kolom dengan jumlah data yang berbeda, apakah your hand tidak `kemeng` nantinya? 😱
#### Zen of Python
> Ketika kita membuat suatu kode memang harus bisa menyelesaikan masalah, tetapi jangan lupa ***Readability is Counts***, Apabila beberapa program kita bisa di automasikan lebih baik maka lakukanlah

*Contoh
```
#Opsi A
for col in category_cols:
    df[col] = df[col].fillna(method='mode')
for col in num_cols:
    df[col] = df[col].fillna(method='mean')
```
```
#Opsi B
df[A] = df[A].fillna(method='mode')
df[B] = df[B].fillna(method='mode')
df[C] = df[C].fillna(method='mode')
.......................
.......................
df[X] = df[X].fillna(method='mean')
df[Y] = df[Y].fillna(method='mean')
df[Z] = df[Z].fillna(method='mean')
```
#### Mana yang lebih baik `A` atau `B`? 

#### Kesimpulan
- Variabe adalah tempat/nama yang digunakan untuk menyimpan data/nilai
- Struktur data adalah cara untuk mengorganisir dan menyimpan data sehingga dapat diakses dan dimanipulasi dengan efisien.
- Dengan memahami karakteristik struktur data lebih baik dapat membawa kita ke dalam hal-hal berikut:
a. Efisiensi Algoritma
b. Skalabilitasi
c. Peningkatan Kualitas Kode


### Nah menurutmu gimana untuk struktur data lainnya? 
> Bagaimanakah set, tuple dan dictionary di terapkan pada preprocessing data?