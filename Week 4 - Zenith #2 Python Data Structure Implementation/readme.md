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
| Dictionary    | 🚫           | 🚫      | `{'a': 1, 'b': 2, 'c': 3}` |
> Sederhananya perbedaannya adalah seperti tabel diatas
#### Kenapa kita perlu mengetahui struktur data? 🤔 
*Emang ada hubungannya kah dengan yang nantinya kita pelajari dalam mengolah data?*
#### Jelas ada Dong 🤗
*Berikut beberapa contoh penerapan struktur data python pada data preprocessing*
## A. Columns filtering using `List`
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
## B. Check Inconsistent Value using `Set`
Dalam kasus preprocessing data bisa saja data yang kita terima tidak hanya berasal dari sumber. Bisa saja kita menggabungkan data dari berbagai sumber menjadi satu.

Data yang dikumpulkan dari berbagai sumber bisa saja tidak konsisten, misalnya seperti data berikut (contoh data kepuasan pelanggan dari seluruh cabang) <br>
**Data Kepuasan Pelanggan Customer Cabang A** 
| Nama Customer | Gender | Rating | Usia |
|---------------|--------|--------|------|
| John          | Male   | A      | 28   |
| Emily         | Female | B      | 41   |
| Bobi          | Unknown| C      | 28   |
| John          | Male   | A      | 26   |
| Emily         | Female | B      | 33   |

**Data Kepuasan Pelanggan Customer Cabang B** 
| Nama Customer | Gender  | Rating | Usia |
|---------------|---------|--------|------|
| Bang          | M       | Bagus  | 38   |
| Bingg         | F       | Biasa  | 28   |
| Bung          | Unknown | Jelek  | 39   |
| Bong          | M       | Bagus  | 45   |
| Bonkk         | F       | Biasa  | 33   |

**Data Kepuasan Pelanggan Customer Cabang C** 
| Nama Customer | Gender  | Rating | Usia |
|---------------|---------|--------|------|
| Jordd          | L       | 3      | 38   |
| Jirddd         | P       | 2      | 28   |
| Jurdd          | -       | 1      | 39   |
| Tensu          | L       | 3      | 45   |
| Rapat         | P       | 2      | 33   |


Nah mungkin dengan contoh simple berikut kita langsung notice kalau disini terjadi ***inkonsistensi data*** pada kolom `gender` dan `rating. 

Nah cuman gimana kasusnya kolomnya kalo banyak dan variasinya banyak, pasti lebih sulit dong buat mantenginnya. oleh karena itu disini kita bisa menggunakan struktur data set. 
```
columns_to_check = [col for col in df.columns if col not in ['Nama Customer', 'Usia']]

def check_col_val(df1, df2, df3, col):
    return list(set(df1[col]) ^ set(df2[col]) ^ set(df3[col]))

for col in columns_to_check:
    print(f'Columns {col}: {check_col_val(df1, df2, df3, col)}')

Output:
Columns Gender: ['-', 'F', 'Female', 'L', 'Male', 'M', 'P']
Columns Rating: ['B', 'C', 'Bagus', 'Biasa', 'A', '2', '1', 'Jelek', '3']
```

Dengan bantuan set kita dapat lebih mudah mengidentifikasi inkonsistensi data pada data kita
 > *Data consistency is a crucial aspect that ensures the accuracy and reliability of data*.

## C. Trace Changelog using `Tuple`
![image](https://miro.medium.com/v2/resize:fit:720/format:webp/1*UJNfWhGGQCXZ7Vhmky-hmg.png)
Faktanya preprocessing data *(data cleaning)* biasanya mengonsumsi waktu lebih banyak ketimbang data tersebut diproses lebih lanjut *(machine learning misalnya)* 

Banyaknya hal dan percobaan yang dilakukan ketika data preprocessing terkadang juga menjadi tantangan, salah satunya adalah melacak perubahan yang sudah kita lakukan.

Nah dengan bantuan `Tuple` kita dapat melacak perubahan setiap step by step yang kita lakukan pada preprocessing data
| Nama Customer | Gender | Rating | Usia |
|---------------|--------|--------|------|
| NaN           | Female | B      | 44.0 |
| Bobi          | NaN    | C      | 39.0 |
| John          | Male   | NaN    | NaN  |
| NaN           | Female | B      | NaN  |
| Bobi          | NaN    | C      | NaN  |

```
def fill_missing_val(df):
    fill_nama_customer = df['Nama Customer'].fillna('Unknown')
    fill_gender = df['Gender'].fillna(df['Gender'].mode()[0])
    fill_rating = df['Rating'].fillna('A')
    fill_usia = df['Usia'].fillna(df['Usia'].mean())
    return (fill_nama_customer, fill_gender, fill_rating, fill_usia)

step1, step2, step3, step4 = fill_missing_val(df)
display(step1, step2, step3, step4)
# Output
0       John
..........
8       Bobi
Name: Nama Customer, dtype: object0      Male
1    Female
..........
8    Female
Name: Gender, dtype: object0    A
1    B
.........
8    C
Name: Rating, dtype: object0    24.000000
1    47.000000
..........
8    39.333333
Name: Usia, dtype: float64
```
Dengan bantuan tuple, kita dapat melakukan multiple return value pada sebuah fungsi, dimana di kasus ini kita gunakan untuk melacak perubahan yang kita lakukan pada setiap imputasi data yang kita lakukan

## D. Make Data Consistent using `Dictionary`
| Nama Customer | Gender | Rating | Usia |
|---------------|--------|--------|------|
| John          | Male   | A      | 48   |
| Emily         | Female | B      | 25   |
| Bobi          | Unknown| C      | 25   |
| John          | M      | Bagus  | 23   |
| Emily         | F      | Biasa  | 29   |

**Bagaimana biar data tersebut konsisten?**
Kita bisa menggunakan fungsi `map` dari `pandas` dengan input value dari `dictionary` (untuk memetakan `nilai yang mau diubah`:`nilai setelah diubah` | `key`:`value`) 
```
def mapping_value(df):
    gender_map = {
        'Male': 'M', 
        'Female': 'F', 
        'Unknown': '-'
        }
    df['Gender'] = df['Gender'].map(lambda x: gender_map[x] if x in gender_map else x)
    
    rating_map = {
        'Bagus': 'A', 
        'Biasa': 'B', 
        'Jelek': 'C'
        }
    df['Rating'] = df['Rating'].map(lambda x: rating_map[x] if x in rating_map else x)
    
    return df

new_df = mapping_value(new_df)
new_df.head()
```
| Nama Customer | Gender | Rating | Usia |
|---------------|--------|--------|------|
| John          | Male   | A      | 27   |
| Emily         | Female | B      | 45   |
| Bobi          | Unknown| C      | 24   |
| John          | Male   | A      | 25   |
| Emily         | Female | B      | 33   |
| Bobi          | Unknown| C      | 38   |
