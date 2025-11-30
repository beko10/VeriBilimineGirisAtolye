# Pandas ile Veri Bilimi Atölyesi

## İçindekiler
1. Pandas'a Giriş
2. Temel Operasyonlar
3. Veri Manipülasyonu
4. İleri Seviye Konulara Giriş
5. Pratik Bir Örnek: Mini Proje

---

## 1. Pandas'a Giriş

### Pandas Nedir ve Veri Bilimindeki Önemi Nedir?

Pandas, Python programlama dili için yazılmış, açık kaynaklı bir veri analizi ve manipülasyonu kütüphanesidir. Adını "Panel Data" (Panel Veri) kelimesinden alır ve özellikle tablosal verilerle (Excel tabloları, SQL veritabanı tabloları gibi) çalışmak için tasarlanmıştır. Veri bilimi projelerinin büyük bir kısmı, veriyi analiz için hazır hale getirme sürecini içerir. Bu sürece **veri temizleme** ve **veri hazırlama** denir. Pandas, bu süreçleri son derece kolaylaştıran güçlü araçlar sunar. Veri bilimciler, Pandas'ı kullanarak veriyi okuyabilir, temizleyebilir, dönüştürebilir, birleştirebilir ve analiz edebilir. Kısacası, Pandas veri bilimcinin en iyi arkadaşlarından biridir.

### Neden NumPy veya Standart Python Listeleri Yerine Pandas?

Python'da verileri saklamak için listeler veya NumPy dizileri gibi yapılar zaten varken neden Pandas'a ihtiyaç duyalım? Bu sorunun cevabı, Pandas'ın sunduğu avantajlarda gizlidir.

| Özellik | Standart Python Listeleri | NumPy Dizileri | Pandas DataFrame/Series |
| :--- | :--- | :--- | :--- |
| **Veri Tipi** | Esnek (farklı tipler bir arada) | Homojen (genellikle sayılar) | Esnek (her sütun farklı tipte olabilir) |
| **Etiketleme** | Sadece sayısal indeks (0, 1, 2...) | Sadece sayısal indeks | Hem sayısal hem de özel etiketli indeks | 
| **Performans** | Yavaş | Hızlı (C tabanlı) | Çok Hızlı (NumPy tabanlı) |
| **Eksik Veri** | Standart bir yöntemi yok | Sınırlı destek (`np.nan`) | Kapsamlı ve kolay araçlar (`dropna`, `fillna`) |
| **Fonksiyonellik** | Temel operasyonlar | Gelişmiş matematiksel işlemler | Veri manipülasyonu, birleştirme, gruplama için zengin fonksiyon seti |

**Özetle:**
- **Python Listelerine Göre:** Pandas, çok daha büyük veri setleriyle çalışırken daha hızlı ve hafıza açısından daha verimlidir. Ayrıca, listelerde bulunmayan yüzlerce veri işleme fonksiyonu sunar.
- **NumPy'a Göre:** Pandas, NumPy'ın üzerine inşa edilmiştir ve onun hız avantajını miras alır. Ancak NumPy, genellikle aynı tipte veri içeren sayısal diziler için idealken, Pandas farklı veri tiplerini (sayı, metin, tarih vb.) bir arada tutan **etiketli** tablolarla çalışmak için optimize edilmiştir. Bu etiketler (sütun isimleri ve satır indeksleri), veriyi anlamayı ve işlemeyi çok daha sezgisel hale getirir.

### Temel Veri Yapıları: Series ve DataFrame

Pandas'ın temelini oluşturan iki ana veri yapısı vardır: **Series** ve **DataFrame**.

**Series (Seri):**
- Tek boyutlu bir dizidir.
- Bir Excel sayfasındaki **tek bir sütun** gibi düşünebilirsiniz.
- Her verinin bir etiketi (indeksi) vardır. Eğer bir indeks belirtmezseniz, varsayılan olarak 0, 1, 2, ... şeklinde sayısal bir indeks oluşturur.

```python
import pandas as pd

# Basit bir Seri oluşturalım
notlar = pd.Series([85, 92, 78, 65], index=['Ali', 'Veli', 'Ayşe', 'Fatma'])
print(notlar)
```

**Çıktı:**
```
Ali      85
Veli     92
Ayşe     78
Fatma    65
dtype: int64
```

**DataFrame (Veri Çerçevesi):**
- İki boyutlu, tablo şeklinde bir veri yapısıdır.
- Bir Excel sayfasının **tamamı** veya bir SQL tablosu gibi düşünebilirsiniz.
- Hem satırları hem de sütunları için indekslere (etiketlere) sahiptir.
- Aslında bir araya gelmiş bir grup Seri'den oluşur. Her sütun bir Seri'dir.

```python
import pandas as pd

# Bir sözlükten DataFrame oluşturalım
veri = {
    'İsim': ['Ali', 'Veli', 'Ayşe', 'Fatma'],
    'Not': [85, 92, 78, 65],
    'Şehir': ['Ankara', 'İstanbul', 'İzmir', 'Ankara']
}

df = pd.DataFrame(veri)
print(df)
```

**Çıktı:**
```
    İsim  Not       Şehir
0    Ali   85      Ankara
1   Veli   92    İstanbul
2   Ayşe   78       İzmir
3  Fatma   65      Ankara
```

Aradaki temel fark, **Series**'in tek boyutlu (tek bir sütun), **DataFrame**'in ise iki boyutlu (satırlar ve sütunlar) olmasıdır.

---

## 2. Temel Operasyonlar (Bol Kod Örnekli)

Bu bölümde, Pandas ile en sık yapacağımız temel işlemleri öğreneceğiz. Veriyi nasıl yükleyeceğimizden, ilk bakışta nasıl anlayacağımıza ve istediğimiz kısımları nasıl seçeceğimize kadar birçok konuya değineceğiz.

### Farklı Dosya Türlerinden Veri Okuma

Veri analizi genellikle harici bir dosyada bulunan veriyi okumakla başlar. Pandas, CSV, Excel, JSON, SQL veritabanları gibi birçok farklı formattaki veriyi kolayca okuyabilir.

**CSV Dosyasından Veri Okuma (`read_csv`)**

CSV (Comma-Separated Values), verilerin virgülle ayrılarak saklandığı basit bir metin dosyası formatıdır. En yaygın kullanılan formatlardan biridir.

```python
import pandas as pd

# satislar.csv dosyasını okuyup bir DataFrame'e aktaralım
df_satislar = pd.read_csv('satislar.csv')
print(df_satislar)
```

**Çıktı:**
```
      Urun     Kategori  Fiyat  Adet
0   Laptop   Elektronik  15000    10
1   Klavye   Elektronik    500    50
2    Kitap        Kitap     80   120
3   Defter    Kırtasiye     20   200
4    Kalem    Kırtasiye      5   500
```

**Excel Dosyasından Veri Okuma (`read_excel`)**

Excel dosyalarını okumak için `read_excel` fonksiyonu kullanılır. Bu fonksiyonu kullanabilmek için `openpyxl` kütüphanesinin kurulu olması gerekebilir (`pip install openpyxl`).

```python
# satislar.xlsx adında bir Excel dosyasını okumak için kullanılacak kod
# df_excel = pd.read_excel('satislar.xlsx')

# Eğer Excel dosyasında birden fazla sayfa varsa, sayfa adını belirtebiliriz
# df_sayfa2 = pd.read_excel('satislar.xlsx', sheet_name='Sayfa2')
# print(df_excel)
```

### DataFrame Oluşturmanın Farklı Yolları

Bazen veriyi bir dosyadan okumak yerine, doğrudan kod içinde kendimiz oluşturmak isteyebiliriz.

**Python Sözlüğünden (Dictionary) Oluşturma:**
Bu en yaygın yöntemlerden biridir. Sözlüğün anahtarları sütun isimleri, değerleri ise sütun verileri olur.

```python
veri = {
    'İsim': ['Ali', 'Veli', 'Ayşe', 'Fatma'],
    'Yaş': [25, 30, 22, 35],
    'Meslek': ['Mühendis', 'Doktor', 'Öğretmen', 'Avukat']
}
df_sozluk = pd.DataFrame(veri)
print(df_sozluk)
```

**Çıktı:**
```
    İsim  Yaş    Meslek
0    Ali   25  Mühendis
1   Veli   30    Doktor
2   Ayşe   22  Öğretmen
3  Fatma   35    Avukat
```

### Veriyi İlk Bakışta Anlama

Veri setini yükledikten sonraki ilk adım, veri hakkında genel bir fikir edinmektir. Pandas bunun için çok kullanışlı fonksiyonlar sunar.

`df_satislar` DataFrame'ini kullanalım:

- **`head()`**: DataFrame'in ilk 5 satırını gösterir. Büyük veri setlerine hızlıca göz atmak için idealdir.
```python
print(df_satislar.head())
```
**Çıktı:**
```
      Urun     Kategori  Fiyat  Adet
0   Laptop   Elektronik  15000    10
1   Klavye   Elektronik    500    50
2    Kitap        Kitap     80   120
3   Defter    Kırtasiye     20   200
4    Kalem    Kırtasiye      5   500
```

- **`tail()`**: DataFrame'in son 5 satırını gösterir.
```python
print(df_satislar.tail(3)) # Son 3 satırı görmek için içine sayı yazabiliriz
```
**Çıktı:**
```
    Urun   Kategori  Fiyat  Adet
2  Kitap      Kitap     80   120
3  Defter  Kırtasiye     20   200
4   Kalem  Kırtasiye      5   500
```

- **`shape`**: DataFrame'in (satır sayısı, sütun sayısı) bilgisini verir.
```python
print(df_satislar.shape)
```
**Çıktı:**
```
(5, 4)
```

- **`info()`**: DataFrame hakkında özet bilgi sunar. İndeks tipi, sütunlar, boş olmayan değer sayısı ve bellek kullanımı gibi bilgileri içerir. Özellikle eksik veri olup olmadığını hızlıca kontrol etmek için çok yararlıdır.
```python
print(df_satislar.info())
```
**Çıktı:**
```
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 5 entries, 0 to 4
Data columns (total 4 columns):
 #   Column    Non-Null Count  Dtype 
---  ------    --------------  ----- 
 0   Urun      5 non-null      object
 1   Kategori  5 non-null      object
 2   Fiyat     5 non-null      int64 
 3   Adet      5 non-null      int64 
dtypes: int64(2), object(2)
memory usage: 288.0+ bytes
None
```

- **`describe()`**: Sayısal sütunlar için temel istatistiksel bilgileri (sayım, ortalama, standart sapma, min, max vb.) hesaplar. Verinin dağılımını anlamak için kullanılır.
```python
print(df_satislar.describe())
```
**Çıktı:**
```
              Fiyat        Adet
count      5.000000    5.000000
mean    3121.000000  176.000000
std     6643.918270  193.209720
min        5.000000   10.000000
25%       20.000000   50.000000
50%       80.000000  120.000000
75%      500.000000  200.000000
max    15000.000000  500.000000
```

### Sütun ve Satır Seçme, Filtreleme

Veri analizinin en temel adımlarından biri, veri setinin belirli kısımlarına odaklanmaktır.

**Sütun Seçme:**
- Tek bir sütun seçmek için `[]` kullanılır. Sonuç bir Seri'dir.
```python
print(df_satislar['Urun'])
```
**Çıktı:**
```
0     Laptop
1     Klavye
2      Kitap
3     Defter
4      Kalem
Name: Urun, dtype: object
```
- Birden fazla sütun seçmek için `[[]]` (iç içe iki parantez) kullanılır. Sonuç bir DataFrame'dir.
```python
print(df_satislar[['Urun', 'Fiyat']])
```
**Çıktı:**
```
      Urun  Fiyat
0   Laptop  15000
1   Klavye    500
2    Kitap     80
3   Defter     20
4    Kalem      5
```

**Satır Seçme ve Filtreleme (`loc` ve `iloc`)**

Pandas'ta satır seçmek için en çok kullanılan iki yöntem `loc` ve `iloc`'tur.

- **`loc` (location - konum):** Etiket bazlı seçim yapar. Yani satır ve sütunların isimlerini (indekslerini) kullanır.
- **`iloc` (integer location - tamsayı konumu):** Tamsayı bazlı (0, 1, 2 gibi) pozisyonel seçim yapar. Python listelerindeki gibi çalışır.

```python
# loc ile indeksi '2' olan satırı seçme
print(df_satislar.loc[2])

# iloc ile 3. satırı (indeksi 2 olan) seçme
print(df_satislar.iloc[2])
```
**İki kodun da Çıktısı:**
```
Urun         Kitap
Kategori     Kitap
Fiyat           80
Adet           120
Name: 2, dtype: object
```

**Koşullu Seçim (Filtreleme):**
Belirli bir koşulu sağlayan satırları seçmek, veri analizinin kalbidir.

Örneğin, fiyatı 100'den büyük olan ürünleri bulalım:
```python
# Koşulu yazalım (Sonuç True/False içeren bir Seri döner)
kosul = df_satislar['Fiyat'] > 100
print(kosul)
```
**Çıktı:**
```
0     True
1     True
2    False
3    False
4    False
Name: Fiyat, dtype: bool
```

Şimdi bu koşulu DataFrame'e filtre olarak uygulayalım:
```python
print(df_satislar[df_satislar['Fiyat'] > 100])
```
**Çıktı:**
```
      Urun     Kategori  Fiyat  Adet
0   Laptop   Elektronik  15000    10
1   Klavye   Elektronik    500    50
```

Birden fazla koşul da kullanabiliriz. `&` (ve), `|` (veya) operatörlerini kullanırız. Koşulları parantez içine almayı unutmayın!

Örneğin, kategorisi 'Kırtasiye' **ve** adedi 300'den fazla olan ürünler:
```python
print(df_satislar[(df_satislar['Kategori'] == 'Kırtasiye') & (df_satislar['Adet'] > 300)])
```
**Çıktı:**
```
    Urun   Kategori  Fiyat  Adet
4  Kalem  Kırtasiye      5   500
```

---

---\n
---

## 3. Veri Manipülasyonu

Veriyi sadece okumak ve seçmek yeterli değildir. Genellikle veriyi analiz için daha uygun bir hale getirmek, yani onu manipüle etmek gerekir. Bu bölümde yeni sütunlar oluşturmayı, eksik verilerle başa çıkmayı ve veri tiplerini değiştirmeyi öğreneceğiz.

Örnekler için yeni bir DataFrame oluşturalım. Bu sefer içinde eksik veriler de bulunsun.

```python
import pandas as pd
import numpy as np # Eksik veri (NaN) oluşturmak için numpy kütüphanesini kullanacağız

veri = {
    'Urun': ['A', 'B', 'C', 'D', 'E'],
    'Fiyat': [100, 150, np.nan, 200, 120],
    'Adet': [10, 5, 8, np.nan, 15],
    'Stok Kodu': ['SK001', 'SK002', 'SK003', 'SK004', 'SK005']
}
df_manip = pd.DataFrame(veri)
print(df_manip)
```

**Çıktı:**
```
  Urun  Fiyat  Adet Stok Kodu
0    A  100.0   10.0     SK001
1    B  150.0    5.0     SK002
2    C    NaN    8.0     SK003
3    D  200.0    NaN     SK004
4    E  120.0   15.0     SK005
```

### Yeni Sütun Ekleme ve Türetme

En sık yapılan işlemlerden biri, mevcut sütunları kullanarak yeni bilgiler içeren sütunlar oluşturmaktır. Örneğin, her bir ürün için toplam geliri hesaplayalım.

**Toplam Gelir = Fiyat * Adet**

```python
df_manip['Toplam Gelir'] = df_manip['Fiyat'] * df_manip['Adet']
print(df_manip)
```

**Çıktı:**
```
  Urun  Fiyat  Adet Stok Kodu  Toplam Gelir
0    A  100.0   10.0     SK001        1000.0
1    B  150.0    5.0     SK002         750.0
2    C    NaN    8.0     SK003           NaN
3    D  200.0    NaN     SK004           NaN
4    E  120.0   15.0     SK005        1800.0
```

Gördüğünüz gibi, eğer işlem yapılan sütunlardan birinde eksik veri (`NaN`) varsa, sonuç da `NaN` olur. Bu, Pandas'ın eksik veriyi yayma davranışıdır ve genellikle istenen bir durumdur çünkü veri kaybını önler.

### Eksik Verilerle Başa Çıkma

Gerçek dünya verileri nadiren tam ve temizdir. Eksik verilerle (`NaN` - Not a Number) nasıl başa çıkacağımızı bilmek çok önemlidir.

**Eksik Verileri Tespit Etme (`isnull()` ve `isna()`)**

`isnull()` (veya eşanlamlısı `isna()`) fonksiyonu, DataFrame'deki her bir hücre için eksik olup olmadığını kontrol eder ve `True`/`False` içeren bir DataFrame döndürür.

```python
print(df_manip.isnull())
```

**Çıktı:**
```
    Urun  Fiyat   Adet  Stok Kodu  Toplam Gelir
0  False  False  False      False         False
1  False  False  False      False         False
2  False   True  False      False          True
3  False  False   True      False          True
4  False  False  False      False         False
```

Genellikle her sütunda kaç tane eksik veri olduğunu görmek daha kullanışlıdır. Bunun için `sum()` fonksiyonu ile `isnull()`'u birleştirebiliriz.

```python
print(df_manip.isnull().sum())
```

**Çıktı:**
```
Urun            0
Fiyat           1
Adet            1
Stok Kodu       0
Toplam Gelir    2
dtype: int64
```

**Eksik Verileri Silme (`dropna()`)**

Eksik verilerden kurtulmanın en basit yolu, o veriyi içeren satırları veya sütunları silmektir. 

```python
# Eksik veri içeren herhangi bir satırı sil
df_temiz = df_manip.dropna()
print(df_temiz)
```

**Çıktı:**
```
  Urun  Fiyat  Adet Stok Kodu  Toplam Gelir
0    A  100.0   10.0     SK001        1000.0
1    B  150.0    5.0     SK002         750.0
4    E  120.0   15.0     SK005        1800.0
```
**Dikkat:** `dropna()` çok fazla veri kaybına neden olabilir. Eğer bir satırda tek bir eksik değer bile varsa, o satır tamamen silinir. Bu yüzden dikkatli kullanılmalıdır.

**Eksik Verileri Doldurma (`fillna()`)**

Daha iyi bir yaklaşım, eksik verileri silmek yerine onları mantıklı bir değerle doldurmaktır.

Örneğin, eksik olan `Fiyat` bilgisini, mevcut fiyatların ortalaması ile dolduralım.

```python
# 1. Fiyat ortalamasını hesapla
ortalama_fiyat = df_manip['Fiyat'].mean()
print(f"Fiyat Ortalaması: {ortalama_fiyat}")

# 2. Eksik Fiyat değerlerini bu ortalama ile doldur
df_manip['Fiyat'].fillna(ortalama_fiyat, inplace=True) # inplace=True, değişikliği orijinal DataFrame üzerinde yapar

print(df_manip)
```

**Çıktı:**
```
Fiyat Ortalaması: 142.5
  Urun   Fiyat  Adet Stok Kodu  Toplam Gelir
0    A  100.00   10.0     SK001        1000.0
1    B  150.00    5.0     SK002         750.0
2    C  142.50    8.0     SK003           NaN
3    D  200.00    NaN     SK004           NaN
4    E  120.00   15.0     SK005        1800.0
```

Benzer şekilde, eksik `Adet` bilgisini de 0 ile doldurabiliriz.

```python
df_manip['Adet'].fillna(0, inplace=True)
print(df_manip)
```

**Çıktı:**
```
   Urun   Fiyat  Adet Stok Kodu  Toplam Gelir
0    A  100.00   10.0     SK001        1000.0
1    B  150.00    5.0     SK002         750.0
2    C  142.50    8.0     SK003           NaN
3    D  200.00    0.0     SK004           NaN
4    E  120.00   15.0     SK005        1800.0
```

### Veri Tiplerini Değiştirme (`astype()`)

Bazen Pandas bir sütunun veri tipini yanlış anlayabilir veya biz analiz gereği tipi değiştirmek isteyebiliriz. Örneğin, ondalıklı bir sayıyı tamsayı yapmak veya bir metin sütununu kategorik tipe çevirmek gibi.

`info()` ile mevcut tiplere bakalım:
```python
print(df_manip.info())
```
**Çıktı:**
```
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 5 entries, 0 to 4
Data columns (total 5 columns):
 #   Column        Non-Null Count  Dtype  
---  ------        --------------  -----  
 0   Urun          5 non-null      object 
 1   Fiyat         5 non-null      float64
 2   Adet          5 non-null      float64
 3   Stok Kodu     5 non-null      object 
 4   Toplam Gelir  3 non-null      float64
dtypes: float64(3), object(2)
memory usage: 328.0+ bytes
None
```
`Adet` sütunu, başlangıçta `NaN` içerdiği için otomatik olarak `float64` (ondalıklı sayı) yapıldı. Artık eksik veri kalmadığına göre, bunu `int` (tamsayı) yapabiliriz.

```python
df_manip['Adet'] = df_manip['Adet'].astype(int)
print(df_manip.info())
```

**Çıktı:**
```
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 5 entries, 0 to 4
Data columns (total 5 columns):
 #   Column        Non-Null Count  Dtype  
---  ------        --------------  -----  
 0   Urun          5 non-null      object 
 1   Fiyat         5 non-null      float64
 2   Adet          5 non-null      int64  
 3   Stok Kodu     5 non-null      object 
 4   Toplam Gelir  3 non-null      float64
dtypes: float64(2), int64(1), object(2)
memory usage: 328.0+ bytes
None
```
Gördüğünüz gibi `Adet` sütununun `Dtype`'ı `int64` olarak değişti.

---

## 4. İleri Seviye Konulara Giriş

Temel veri manipülasyonu adımlarını öğrendikten sonra, veriden daha derinlemesine anlamlar çıkarmamızı sağlayan daha güçlü tekniklere geçebiliriz. Bu bölümde gruplama ve birleştirme gibi konulara giriş yapacağız.

### Gruplama ve Agregasyon (`groupby()`)

`groupby()` fonksiyonu, "böl-uygula-birleştir" (split-apply-combine) stratejisinin temel taşıdır. Veri setini belirli bir veya daha fazla sütundaki değerlere göre gruplara ayırmamızı, her grup üzerinde bir fonksiyon (örneğin `sum`, `mean`) uygulamamızı ve sonuçları bir araya getirmemizi sağlar.

Örneğin, bir mağazanın farklı kategorilerdeki toplam satış adetlerini veya her bir şehirdeki çalışanların yaş ortalamasını bulmak gibi işlemler için `groupby` kullanılır.

`satislar.csv` verimizi tekrar kullanalım:

```python
import pandas as pd

df_satislar = pd.read_csv('satislar.csv')
print("Orijinal Veri:")
print(df_satislar)
```

**Çıktı:**
```
Orijinal Veri:
      Urun     Kategori  Fiyat  Adet
0   Laptop   Elektronik  15000    10
1   Klavye   Elektronik    500    50
2    Kitap        Kitap     80   120
3   Defter    Kırtasiye     20   200
4    Kalem    Kırtasiye      5   500
```

**Amacımız:** Her bir kategorideki toplam satılan ürün adedini bulmak.

```python
# 1. Veriyi 'Kategori' sütununa göre grupla
# 2. Her grup için 'Adet' sütununun toplamını al ('sum()')
kategoriye_gore_adet = df_satislar.groupby('Kategori')['Adet'].sum()
print(kategoriye_gore_adet)
```

**Çıktı:**
```
Kategori
Elektronik     60
Kitap         120
Kırtasiye     700
Name: Adet, dtype: int64
```

Benzer şekilde, her kategorideki ortalama ürün fiyatını da bulabiliriz:

```python
# 'Kategori'ye göre grupla, 'Fiyat' sütununun ortalamasını al ('mean()')
kategoriye_gore_ortalama_fiyat = df_satislar.groupby('Kategori')['Fiyat'].mean()
print(kategoriye_gore_ortalama_fiyat)
```

**Çıktı:**
```
Kategori
Elektronik    7750.0
Kitap           80.0
Kırtasiye       12.5
Name: Fiyat, dtype: float64
```

`agg()` fonksiyonu ile birden fazla agregasyon işlemini aynı anda yapabiliriz:

```python
# Her kategori için hem toplam adedi hem de ortalama fiyatı bulalım
agg_sonuclar = df_satislar.groupby('Kategori').agg({
    'Adet': 'sum',      # Adet sütunu için toplam
    'Fiyat': 'mean'    # Fiyat sütunu için ortalama
})
print(agg_sonuclar)
```

**Çıktı:**
```
            Adet   Fiyat
Kategori                  
Elektronik    60  7750.0
Kitap        120    80.0
Kırtasiye    700    12.5
```

### İki DataFrame'i Birleştirme (`merge` ve `concat`)

Analizlerimizde genellikle veriler farklı tablolarda veya dosyalarda bulunur. Bu verileri anlamlı bir şekilde bir araya getirmek için `merge` ve `concat` fonksiyonlarını kullanırız.

**`concat()`: DataFrame'leri Alt Alta veya Yan Yana Birleştirme**

`concat`, DataFrame'leri basitçe eksen boyunca (satır veya sütun) birleştirir. SQL'deki `UNION` işlemine benzer.

```python
# İki küçük DataFrame oluşturalım
df1 = pd.DataFrame({'A': ['A0', 'A1'], 'B': ['B0', 'B1']})
df2 = pd.DataFrame({'A': ['A2', 'A3'], 'B': ['B2', 'B3']})

# Alt alta birleştirelim (varsayılan davranış)
alt_alta = pd.concat([df1, df2])
print("Alt Alta Birleştirme:")
print(alt_alta)

# Yan yana birleştirelim (axis=1)
yan_yana = pd.concat([df1, df2], axis=1)
print("\nYan Yana Birleştirme:")
print(yan_yana)
```

**Çıktı:**
```
Alt Alta Birleştirme:
    A   B
0  A0  B0
1  A1  B1
0  A2  B2
1  A3  B3

Yan Yana Birleştirme:
    A   B   A   B
0  A0  B0  A2  B2
1  A1  B1  A3  B3
```
**Not:** Alt alta birleştirme yapıldığında indekslerin tekrarlandığına dikkat edin. Bunu düzeltmek için `pd.concat([df1, df2], ignore_index=True)` kullanılabilir.

**`merge()`: Ortak Sütunlara Göre Akıllı Birleştirme**

`merge`, SQL'deki `JOIN` işlemlerine çok benzer. İki DataFrame'i ortak bir sütun veya indekse göre birleştirir.

Örnek için iki yeni DataFrame oluşturalım:

```python
df_personel = pd.DataFrame({
    'calisan_id': [1, 2, 3, 4],
    'isim': ['Ali', 'Veli', 'Ayşe', 'Fatma'],
    'departman_id': [101, 102, 101, 103]
})

df_departman = pd.DataFrame({
    'id': [101, 102, 104],
    'departman_adi': ['IT', 'İK', 'Pazarlama']
})

print("Personel Tablosu:")
print(df_personel)
print("\nDepartman Tablosu:")
print(df_departman)
```

**Çıktı:**
```
Personel Tablosu:
   calisan_id   isim  departman_id
0           1    Ali           101
1           2   Veli           102
2           3   Ayşe           101
3           4  Fatma           103

Departman Tablosu:
    id departman_adi
0  101            IT
1  102            İK
2  104     Pazarlama
```

Şimdi bu iki tabloyu birleştirerek her çalışanın hangi departman adında çalıştığını bulalım.

```python
# 'df_personel'deki 'departman_id' ile 'df_departman'daki 'id' sütunlarını eşleştir
birlesik_df = pd.merge(df_personel, df_departman, left_on='departman_id', right_on='id')
print(birlesik_df)
```

**Çıktı:**
```
   calisan_id  isim  departman_id   id departman_adi
0           1   Ali           101  101            IT
1           3  Ayşe           101  101            IT
2           2  Veli           102  102            İK
```

**Önemli Noktalar:**
- `merge` işlemi varsayılan olarak **iç birleştirme (inner join)** yapar. Yani sadece her iki tabloda da eşleşen kayıtları getirir. (Personel 4-Fatma ve Departman 'Pazarlama' sonuçta yer almadı).
- `how` parametresi ile birleştirme türünü değiştirebiliriz: `how='left'`, `how='right'`, `how='outer'`.
- `left_on` ve `right_on` ile birleştirilecek sütunların adları farklıysa belirtilir. Eğer aynıysa `on='sutun_adi'` kullanılabilir.

**`concat` vs `merge` - Ne Zaman Hangisini Kullanmalı?**
- Eğer iki tablonun yapısı aynıysa ve onları sadece alt alta veya yan yana eklemek istiyorsanız **`concat`** kullanın.
- Eğer iki tabloyu ortak bir anahtar (ID, kod vb.) üzerinden birleştirerek zenginleştirmek istiyorsanız **`merge`** kullanın.

---

## 5. Pratik Bir Örnek (Mini Proje)

Şimdiye kadar öğrendiğimiz tüm konuları bir araya getirerek, baştan sona basit bir veri analizi senaryosu gerçekleştirelim. Bu mini proje, teorik bilgilerin pratikte nasıl kullanıldığını görmenizi sağlayacak.

**Senaryo:** Elimizde bir e-ticaret sitesine ait birkaç günlük satış verileri var. Bu verileri kullanarak aşağıdaki soruları yanıtlamaya çalışacağız:
1. Veri setinde eksik bilgi var mı? Varsa nasıl başa çıkmalıyız?
2. Her bir satış işleminden ne kadar gelir elde edildiğini hesaplayın.
3. En çok gelir getiren ürün hangisidir?
4. Kategorilere göre toplam satılan ürün adedi nedir?

### Adım 1: Veriyi Yükleme ve İlk Bakış

Öncelikle `mini_proje_satislar.csv` adlı veri setimizi yükleyelim ve içeriğine hızlıca bir göz atalım.

```python
import pandas as pd

# Veriyi yükle
df = pd.read_csv("mini_proje_satislar.csv")

# Verinin ilk 5 satırını göster
print("Veri Setinin İlk Hali:")
print(df.head())

# Veri hakkında genel bilgi al
print("\nVeri Seti Bilgileri:")
df.info()
```

**Çıktı:**
```
Veri Setinin İlk Hali:
        Tarih Urun_Adi     Kategori  Birim_Fiyat  Satilan_Adet
0  2023-10-01   Laptop   Elektronik      25000.0           5.0
1  2023-10-01    Mouse   Elektronik        300.0          20.0
2  2023-10-02  Kitap A        Kitap        120.0          15.0
3  2023-10-02   Klavye   Elektronik        750.0          10.0
4  2023-10-03  Kitap B        Kitap          NaN           8.0

Veri Seti Bilgileri:
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 9 entries, 0 to 8
Data columns (total 5 columns):
 #   Column        Non-Null Count  Dtype  
---  ------        --------------  -----  
 0   Tarih         9 non-null      object 
 1   Urun_Adi      9 non-null      object 
 2   Kategori      9 non-null      object 
 3   Birim_Fiyat   8 non-null      float64
 4   Satilan_Adet  8 non-null      float64
dtypes: float64(2), object(3)
memory usage: 488.0+ bytes
```

**İlk Gözlemler:**
- `Birim_Fiyat` sütununda 1 eksik veri var (8 non-null).
- `Satilan_Adet` sütununda 1 eksik veri var (8 non-null).
- `Tarih` sütunu metin (`object`) olarak görünüyor, bunu daha sonra tarih formatına çevirebiliriz (bu proje için gerekli değil).
- `Satilan_Adet` ondalıklı sayı (`float64`) olarak görünüyor, bunu tamsayıya çevirmek daha mantıklı olacaktır.

### Adım 2: Veri Temizleme ve Hazırlama

Şimdi tespit ettiğimiz eksik verilerle ilgilenelim ve yeni `Toplam_Gelir` sütunumuzu oluşturalım.

```python
# Eksik Satilan_Adet değerini 0 ile dolduralım (satılmamış kabul edelim)
df["Satilan_Adet"].fillna(0, inplace=True)

# Eksik Birim_Fiyat değerini, aynı ürünün diğer satışlarındaki fiyatla doldurabiliriz.
# Ancak burada daha basit bir yöntem olarak ortalama fiyat ile dolduralım.
ortalama_fiyat = df["Birim_Fiyat"].mean()
df["Birim_Fiyat"].fillna(ortalama_fiyat, inplace=True)

# Satilan_Adet sütununu tamsayıya çevirelim
df["Satilan_Adet"] = df["Satilan_Adet"].astype(int)

# Toplam_Gelir sütununu oluşturalım
df["Toplam_Gelir"] = df["Birim_Fiyat"] * df["Satilan_Adet"]

print("Temizlenmiş ve Hazırlanmış Veri:")
print(df)

print("\nTemizlenmiş Veri Bilgileri:")
df.info()
```

**Çıktı:**
```
Temizlenmiş ve Hazırlanmış Veri:
        Tarih Urun_Adi     Kategori   Birim_Fiyat  Satilan_Adet  Toplam_Gelir
0  2023-10-01   Laptop   Elektronik  25000.000000             5     125000.00
1  2023-10-01    Mouse   Elektronik    300.000000            20       6000.00
2  2023-10-02  Kitap A        Kitap    120.000000            15       1800.00
3  2023-10-02   Klavye   Elektronik    750.000000            10       7500.00
4  2023-10-03  Kitap B        Kitap   6435.000000             8      51480.00
5  2023-10-03   Laptop   Elektronik  25000.000000             3      75000.00
6  2023-10-04   Defter    Kırtasiye     50.000000            50       2500.00
7  2023-10-04    Kalem    Kırtasiye     10.000000           100       1000.00
8  2023-10-04    Mouse   Elektronik    300.000000             0          0.00

Temizlenmiş Veri Bilgileri:
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 9 entries, 0 to 8
Data columns (total 6 columns):
 #   Column        Non-Null Count  Dtype  
---  ------        --------------  -----  
 0   Tarih         9 non-null      object 
 1   Urun_Adi      9 non-null      object 
 2   Kategori      9 non-null      object 
 3   Birim_Fiyat   9 non-null      float64
 4   Satilan_Adet  9 non-null      int64  
 5   Toplam_Gelir  9 non-null      float64
dtypes: float64(2), int64(1), object(3)
memory usage: 560.0+ bytes
```
Artık veri setimiz temiz ve analize hazır!

### Adım 3: Analiz ve Soruları Yanıtlama

Şimdi `groupby` gibi güçlü fonksiyonları kullanarak sorularımızı yanıtlayalım.

**Soru 1: En çok gelir getiren ürün hangisidir?**

Bunun için ürün bazında `Toplam_Gelir` sütununu gruplayıp toplamamız gerekiyor.

```python
urun_bazinda_gelir = df.groupby("Urun_Adi")["Toplam_Gelir"].sum()

# Sonuçları büyükten küçüğe sıralayalım
urun_bazinda_gelir = urun_bazinda_gelir.sort_values(ascending=False)

print("Ürün Bazında Toplam Gelirler:")
print(urun_bazinda_gelir)

print(f"\nEn çok gelir getiren ürün: {urun_bazinda_gelir.index[0]}")
```

**Çıktı:**
```
Ürün Bazında Toplam Gelirler:
Urun_Adi
Laptop     200000.0
Kitap B     51480.0
Klavye       7500.0
Mouse        6000.0
Defter       2500.0
Kitap A      1800.0
Kalem        1000.0
Name: Toplam_Gelir, dtype: float64

En çok gelir getiren ürün: Laptop
```

**Soru 2: Kategorilere göre toplam satılan ürün adedi nedir?**

Bu sefer `Kategori` sütununa göre gruplayıp `Satilan_Adet` sütununu toplayacağız.

```python
kategori_bazinda_adet = df.groupby("Kategori")["Satilan_Adet"].sum()

print("Kategori Bazında Toplam Satılan Adet:")
print(kategori_bazinda_adet)
```

**Çıktı:**
```
Kategori Bazında Toplam Satılan Adet:
Kategori
Elektronik     38
Kitap          23
Kırtasiye     150
Name: Satilan_Adet, dtype: int64
```

### Sonuç ve Bulgular

Bu basit analiz sonucunda şunları öğrendik:
- Toplamda en çok geliri **Laptop** ürünü getirmiştir.
- Satılan ürün adedi bazında en popüler kategori **Kırtasiye**'dir.
- Veri temizleme adımları (eksik verileri doldurma, tip dönüştürme) doğru analiz yapabilmek için kritik öneme sahiptir.

Bu mini proje, Pandas'ın temel fonksiyonlarını kullanarak ham veriden nasıl anlamlı sonuçlar çıkarabileceğimizin küçük bir örneğidir.

---

## Sonuç

Bu atölye dokümanında, Pandas kütüphanesinin temellerini ve veri bilimi projelerinde nasıl kullanılacağını öğrendiniz. Pandas'ın ne olduğundan başlayarak, temel veri yapıları olan Series ve DataFrame'i tanıdınız. Veriyi nasıl yükleyeceğinizi, seçeceğinizi, filtreleyeceğinizi ve manipüle edeceğinizi öğrendiniz. Eksik verilerle başa çıkma teknikleri, gruplama ve birleştirme gibi ileri seviye konulara giriş yaptınız. Son olarak, tüm bu bilgileri bir araya getirerek gerçek bir veri analizi senaryosunu baştan sona tamamladınız.

Pandas, veri biliminin vazgeçilmez araçlarından biridir ve bu dokümanda öğrendikleriniz, daha karmaşık analizler yapmak için sağlam bir temel oluşturacaktır. Bundan sonraki adımınız, farklı veri setleri üzerinde pratik yapmak ve Pandas'ın daha gelişmiş özelliklerini keşfetmek olmalıdır.

**Önerilen Sonraki Adımlar:**
- Kendi veri setlerinizle pratik yapın.
- Pandas'ın resmi dokümanlarını inceleyin.
- Veri görselleştirme için Matplotlib veya Seaborn kütüphanelerini öğrenin.
- Daha büyük veri setleriyle çalışarak performans optimizasyonunu keşfedin.

Başarılar dileriz!

---

## Kaynaklar

Bu doküman hazırlanırken aşağıdaki kaynaklardan yararlanılmıştır:

- [Pandas Resmi Dokümanları](https://pandas.pydata.org/docs/)
- [Python for Data Analysis (Wes McKinney)](https://wesmckinney.com/book/)
- [Pandas User Guide](https://pandas.pydata.org/docs/user_guide/index.html)

---

