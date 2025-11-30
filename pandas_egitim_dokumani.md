# 🐼 Pandas ile Veri Analizi - Kapsamlı Eğitim Dokümanı

> **3 Saatlik Veri Bilimi Atölyesi** | MiniMax Agent tarafından hazırlanmıştır

---

## 📚 İçindekiler

1. [🚀 Pandas'a Giriş ve Kurulum](#1-pandas-a-giriş-ve-kurulum)
2. [📊 Temel Veri Yapıları: Series ve DataFrame](#2-temel-veri-yapıları-series-ve-dataframe)
3. [📁 Veri Okuma/Yazma İşlemleri](#3-veri-okuma-yazma-işlemleri)
4. [🛠️ Veri Manipülasyonu ve Temizleme](#4-veri-manipülasyonu-ve-temizleme)
5. [🔍 Veri Filtreleme ve Seçme](#5-veri-filtreleme-ve-seçme)
6. [📈 Temel İstatistiksel Analizler](#6-temel-istatistiksel-analizler)
7. [📋 Gruplandırma ve Pivot Tablolar](#7-gruplandırma-ve-pivot-tablolar)
8. [💼 Pratik Uygulama Projesi](#8-pratik-uygulama-projesi)
9. [📝 Pandas Cheat Sheet](#9-pandas-cheat-sheet)
10. [🔗 Kaynaklar ve Ek Materyaller](#10-kaynaklar-ve-ek-materyaller)

---

## 🎯 Hedef Kitle

Bu doküman aşağıdaki özelliklere sahip katılımcılar için tasarlanmıştır:

- ✅ **Temel Python bilgisi** (değişkenler, döngüler, fonksiyonlar)
- 🆕 **Pandas'a yeni başlıyor** veya hiç bilmiyor
- 📊 **Veri analizi/veri bilimi** alanına ilgi duyuyor
- 👥 **15-20 kişilik grup** ortamı

## 🎓 Öğretim Yaklaşımı

Bu doküman **sarmal öğrenme metodolojisi** ile tasarlanmıştır:
- 📈 **Kademeli derinleştirme**: Basit kavramlardan karmaşık analizlere
- 🔄 **Tekrar ve pekiştirme**: Önceki konuları yeni örneklerle güçlendirme
- 🧩 **Parçalı öğrenme**: Her kavramı adım adım öğrenme

---

# 1. 🚀 Pandas'a Giriş ve Kurulum

## 🤔 Pandas Nedir?

**Pandas** (Python Data Analysis Library), Python programlama dilinde veri analizi ve manipülasyonu için geliştirilmiş güçlü bir kütüphanedir. 

### 🌟 Pandas'ın Temel Avantajları:
- 📊 **Veri yapıları**: Series ve DataFrame ile esnek veri saklama
- 🔄 **Veri dönüştürme**: Kolay veri temizleme ve manipülasyon
- 📁 **Dosya formatları**: CSV, Excel, JSON, SQL gibi çoklu format desteği
- 📈 **Analiz araçları**: İstatistiksel analiz ve görselleştirme desteği
- ⚡ **Performans**: NumPy tabanlı hızlı işlemler

## 💻 Kurulum

### Anaconda ile Kurulum (Önerilen)
```bash
# Anaconda ile Pandas otomatik gelir
conda install pandas
```

### pip ile Kurulum
```bash
pip install pandas
```

### Kurulum Kontrolü
```python
import pandas as pd
print(pd.__version__)
# Çıktı: 2.1.3 (veya güncel versiyon)
```

## 📚 Temel İmport ve Kısaltmalar

```python
# Standart import şekli
import pandas as pd
import numpy as np

# Görselleştirme kütüphaneleri (opsiyonel)
import matplotlib.pyplot as plt
import seaborn as sns

# Pandas ayarları
pd.set_option('display.max_columns', None)  # Tüm sütunları göster
pd.set_option('display.width', None)        # Genişlik sınırı yok
```

## 🔧 İlk Pandas Kodu

```python
# Basit bir veri seti oluşturma
import pandas as pd

# Basit bir sözlük
veri = {
    'isim': ['Ali', 'Ayşe', 'Mehmet', 'Fatma'],
    'yaş': [25, 30, 35, 28],
    'şehir': ['İstanbul', 'Ankara', 'İzmir', 'Bursa']
}

# DataFrame oluşturma
df = pd.DataFrame(veri)
print(df)
```

**Çıktı:**
```
     isim  yaş     şehir
0     Ali   25  İstanbul
1    Ayşe   30    Ankara
2  Mehmet   35     İzmir
3   Fatma   28     Bursa
```

## ⚠️ Dikkat Edilmesi Gerekenler

> **💡 İpucu**: Pandas'ı her zaman `pd` kısaltması ile import edin. Bu endüstri standardıdır.

> **⚠️ Uyarı**: Büyük veri setleri ile çalışırken bellek kullanımına dikkat edin.

## 🚨 Sık Yapılan Hatalar

| Hata | Açıklama | Çözüm |
|------|----------|-------|
| `ModuleNotFoundError: No module named 'pandas'` | Pandas kurulu değil | `pip install pandas` komutu ile kurun |
| `AttributeError: module 'pandas' has no attribute 'DataFrame'` | Yanlış import | `import pandas as pd` şeklinde import edin |
| `KeyError: 'column_name'` | Olmayan sütuna erişim | `df.columns` ile sütun isimlerini kontrol edin |

## 🎯 Egzersizler

### Egzersiz 1: Kurulum Kontrolü
```python
# 1. Pandas'ı import edin ve versiyonunu yazdırın
# 2. NumPy'ı da import edin
# 3. Basit bir DataFrame oluşturun

# Çözüm alanı:

```

### Egzersiz 2: İlk DataFrame
```python
# Aşağıdaki bilgilerle bir DataFrame oluşturun:
# Ürün isimleri: ['Laptop', 'Mouse', 'Klavye']
# Fiyatlar: [5000, 50, 150]
# Stok: [10, 100, 50]

# Çözüm alanı:

```

---

# 2. 📊 Temel Veri Yapıları: Series ve DataFrame

Pandas'ın iki temel veri yapısı vardır: **Series** (1 boyutlu) ve **DataFrame** (2 boyutlu). Bu yapıları anlamak, Pandas'ta etkili çalışmanın temelidir.

## 📈 Series - 1 Boyutlu Veri Yapısı

**Series**, etiketli (indexli) bir boyutlu veri yapısıdır. Bir Excel sütunu veya Python listesi gibi düşünebilirsiniz.

### Series Oluşturma Yöntemleri

#### 1️⃣ Liste ile Series Oluşturma
```python
import pandas as pd

# Basit liste ile Series
sayilar = pd.Series([10, 20, 30, 40, 50])
print(sayilar)
```

**Çıktı:**
```
0    10
1    20
2    30
3    40
4    50
dtype: int64
```

#### 2️⃣ Index ile Series Oluşturma
```python
# Özel index ile Series
şehir_nufus = pd.Series([15000000, 5500000, 4300000], 
                       index=['İstanbul', 'Ankara', 'İzmir'])
print(şehir_nufus)
```

**Çıktı:**
```
İstanbul    15000000
Ankara       5500000
İzmir        4300000
dtype: int64
```

#### 3️⃣ Sözlük ile Series Oluşturma
```python
# Sözlükten Series
notlar = pd.Series({
    'Matematik': 85,
    'Fizik': 90,
    'Kimya': 75,
    'Biyoloji': 88
})
print(notlar)
```

**Çıktı:**
```
Matematik    85
Fizik        90
Kimya        75
Biyoloji     88
dtype: int64
```

### Series Temel İşlemleri

```python
# Series üzerinde temel işlemler
print(f"Ortalama: {notlar.mean()}")           # Ortalama: 84.5
print(f"Maksimum: {notlar.max()}")            # Maksimum: 90
print(f"Minimum ders: {notlar.idxmin()}")     # Minimum ders: Kimya
print(f"Eleman sayısı: {notlar.count()}")     # Eleman sayısı: 4

# İndexleme ve dilimlemek
print(f"Matematik notu: {notlar['Matematik']}")  # Matematik notu: 85
print(f"İlk iki ders: \n{notlar[:2]}")           # İlk iki dersi göster
```

## 📋 DataFrame - 2 Boyutlu Veri Yapısı

**DataFrame**, satır ve sütunları olan tablo benzeri veri yapısıdır. Excel tablosu veya SQL veritabanı tablosu gibi düşünebilirsiniz.

### DataFrame Oluşturma Yöntemleri

#### 1️⃣ Sözlük ile DataFrame Oluşturma
```python
# Sözlükten DataFrame oluşturma
ogrenci_bilgileri = {
    'isim': ['Ali', 'Ayşe', 'Mehmet', 'Fatma', 'Kemal'],
    'yaş': [22, 23, 21, 24, 22],
    'şehir': ['İstanbul', 'Ankara', 'İzmir', 'Bursa', 'Antalya'],
    'not_ortalaması': [3.2, 3.8, 2.9, 3.5, 3.0]
}

df_ogrenci = pd.DataFrame(ogrenci_bilgileri)
print(df_ogrenci)
```

**Çıktı:**
```
     isim  yaş     şehir  not_ortalaması
0     Ali   22  İstanbul            3.2
1    Ayşe   23    Ankara            3.8
2  Mehmet   21     İzmir            2.9
3   Fatma   24     Bursa            3.5
4   Kemal   22   Antalya            3.0
```

#### 2️⃣ Liste listesi ile DataFrame
```python
# İç içe liste ile DataFrame
veri = [
    ['Laptop', 'Teknoloji', 5000, 25],
    ['Kitap', 'Eğitim', 50, 100],
    ['Mouse', 'Teknoloji', 100, 75],
    ['Kalem', 'Eğitim', 5, 200]
]

sutun_isimleri = ['ürün', 'kategori', 'fiyat', 'stok']
df_urun = pd.DataFrame(veri, columns=sutun_isimleri)
print(df_urun)
```

**Çıktı:**
```
    ürün   kategori  fiyat  stok
0  Laptop  Teknoloji   5000    25
1   Kitap     Eğitim     50   100
2   Mouse  Teknoloji    100    75
3   Kalem     Eğitim      5   200
```

#### 3️⃣ NumPy array ile DataFrame
```python
import numpy as np

# NumPy array ile DataFrame
rastgele_veri = np.random.randint(1, 100, size=(4, 3))
df_rastgele = pd.DataFrame(rastgele_veri, 
                          columns=['A', 'B', 'C'],
                          index=['Satır1', 'Satır2', 'Satır3', 'Satır4'])
print(df_rastgele)
```

### DataFrame Temel Bilgiler

```python
# DataFrame hakkında temel bilgiler
print("DataFrame Şekli:", df_ogrenci.shape)           # (5, 4)
print("Sütun İsimleri:", df_ogrenci.columns.tolist()) # ['isim', 'yaş', 'şehir', 'not_ortalaması']
print("Index:", df_ogrenci.index.tolist())            # [0, 1, 2, 3, 4]
print("Veri Tipleri:\n", df_ogrenci.dtypes)

# İlk ve son satırlar
print("İlk 3 satır:\n", df_ogrenci.head(3))
print("Son 2 satır:\n", df_ogrenci.tail(2))

# Temel istatistikler
print("Sayısal sütunlar özeti:\n", df_ogrenci.describe())
```

### DataFrame Sütun İşlemleri

```python
# Sütun seçme
print("Sadece isimler:\n", df_ogrenci['isim'])
print("Birden fazla sütun:\n", df_ogrenci[['isim', 'not_ortalaması']])

# Yeni sütun ekleme
df_ogrenci['geçme_durumu'] = df_ogrenci['not_ortalaması'] >= 3.0
df_ogrenci['yaş_grubu'] = df_ogrenci['yaş'].apply(lambda x: 'Genç' if x < 23 else 'Yaşlı')

print("Güncellenmiş DataFrame:\n", df_ogrenci)
```

## ⚠️ Dikkat Edilmesi Gerekenler

> **💡 Index Önemli**: Pandas'ta her satır ve sütunun bir index'i vardır. Bu index'ler veri erişimi için kritiktir.

> **🔍 Veri Tipleri**: DataFrame'de her sütun farklı veri tipinde olabilir (int, float, string, boolean).

> **⚡ Bellek**: Büyük DataFrame'ler oluştururken bellek kullanımına dikkat edin.

## 🚨 Sık Yapılan Hatalar

| Hata | Açıklama | Çözüm |
|------|----------|-------|
| `KeyError: 'sütun_adı'` | Olmayan sütuna erişim | `df.columns` ile sütun isimlerini kontrol edin |
| `ValueError: arrays must all be same length` | Farklı uzunlukta listeler | Tüm listelerin aynı uzunlukta olduğundan emin olun |
| `AttributeError: 'Series' object has no attribute 'shape'` | Series ile DataFrame karışıklığı | Series için `len()`, DataFrame için `shape` kullanın |
| Index karışıklığı | Yanlış index kullanımı | `reset_index()` ile index'i sıfırlayın |

## 🎯 Egzersizler

### Egzersiz 1: Series Oluşturma
```python
# 1. Türkiye'nin 5 büyük şehrinin nüfusunu içeren bir Series oluşturun
# 2. Bu Series'in ortalamasını, maksimumunu ve minimum değerini bulun
# 3. En kalabalık şehri yazdırın

# Çözüm alanı:

```

### Egzersiz 2: DataFrame Oluşturma
```python
# Aşağıdaki bilgilerle bir "çalışan" DataFrame'i oluşturun:
# - İsim: ['Ahmet', 'Zeynep', 'Ozan', 'Elif']
# - Departman: ['IT', 'HR', 'Finans', 'IT']  
# - Maaş: [7500, 6000, 8000, 7000]
# - Tecrübe (yıl): [3, 5, 7, 2]

# 1. DataFrame'i oluşturun
# 2. Ortalama maaşı hesaplayın
# 3. IT departmanında kaç kişi çalıştığını bulun
# 4. 5+ yıl tecrübesi olan çalışanları listeleyin

# Çözüm alanı:

```

### Egzersiz 3: İleri İşlemler
```python
# Yukarıdaki çalışan DataFrame'ini kullanarak:
# 1. "maaş_seviyesi" sütunu ekleyin (7000'den fazla ise "Yüksek", altında ise "Düşük")
# 2. Departmanlara göre ortalama maaşı hesaplayın
# 3. En deneyimli çalışanın bilgilerini yazdırın

# Çözüm alanı:

```

---# 3. 📁 Veri Okuma/Yazma İşlemleri

Gerçek dünyada veriler genellikle dosyalarda saklanır. Pandas, çeşitli dosya formatlarından veri okuma ve yazma konusunda güçlü yeteneklere sahiptir.

## 📄 CSV (Comma Separated Values) İşlemleri

CSV, veri analizinde en yaygın kullanılan dosya formatlarından biridir.

### CSV Dosyası Okuma

#### 1️⃣ Basit CSV Okuma
```python
import pandas as pd

# Basit CSV okuma
df = pd.read_csv('dosya_yolu.csv')
print(df.head())
```

#### 2️⃣ Gelişmiş CSV Okuma Parametreleri
```python
# Detaylı parametrelerle CSV okuma
df = pd.read_csv(
    'satislar.csv',
    sep=',',                    # Ayırıcı karakter
    encoding='utf-8',           # Karakter kodlaması
    index_col=0,               # İlk sütunu index olarak kullan
    header=0,                  # Hangi satırı sütun ismi olarak kullan
    skiprows=1,                # İlk 1 satırı atla
    nrows=1000,               # Sadece ilk 1000 satırı oku
    usecols=['tarih', 'fiyat', 'miktar'],  # Sadece belirtilen sütunları oku
    dtype={'miktar': int},     # Belirli sütunlar için veri tipi
    na_values=['N/A', 'null', '']  # Boş değer olarak kabul edilecekler
)
print(df.info())
```

#### 3️⃣ Örnek CSV Verisi Oluşturup Okuma
```python
import pandas as pd
import numpy as np

# Örnek veri oluşturma
np.random.seed(42)
ornek_veri = {
    'tarih': pd.date_range('2024-01-01', periods=100),
    'ürün': np.random.choice(['Laptop', 'Mouse', 'Klavye'], 100),
    'satış_miktarı': np.random.randint(1, 20, 100),
    'birim_fiyat': np.random.randint(50, 5000, 100),
    'satış_temsilcisi': np.random.choice(['Ali', 'Ayşe', 'Mehmet'], 100)
}

df_satış = pd.DataFrame(ornek_veri)

# CSV olarak kaydet
df_satış.to_csv('satışlar.csv', index=False, encoding='utf-8')
print("CSV dosyası oluşturuldu!")

# Kaydedilen dosyayı oku
df_okunan = pd.read_csv('satışlar.csv')
print("Okunan veri:")
print(df_okunan.head())
print(f"Shape: {df_okunan.shape}")
```

### CSV Dosyası Yazma

```python
# DataFrame'i CSV olarak kaydetme
df_satış.to_csv(
    'çıktı_dosyası.csv',
    index=False,               # Index'i yazma
    sep=',',                   # Ayırıcı
    encoding='utf-8',          # Karakter kodlaması
    float_format='%.2f',       # Float sayılar için format
    date_format='%Y-%m-%d'     # Tarih formatı
)

# Sadece belirli sütunları kaydetme
df_satış[['ürün', 'satış_miktarı']].to_csv('özet_satış.csv', index=False)
```

## 📊 Excel İşlemleri

Excel dosyaları iş dünyasında çok yaygındır. Pandas bu formatla da etkili çalışabilir.

### Excel Dosyası Okuma

#### 1️⃣ Basit Excel Okuma
```python
# Excel dosyası okuma
df = pd.read_excel('dosya.xlsx')
print(df.head())
```

#### 2️⃣ Çoklu Sayfa ile Excel Okuma
```python
# Belirli bir sayfayı okuma
df_sayfa1 = pd.read_excel('çoklu_sayfa.xlsx', sheet_name='Sayfa1')

# Tüm sayfaları okuma
tüm_sayfalar = pd.read_excel('çoklu_sayfa.xlsx', sheet_name=None)
print("Sayfa isimleri:", tüm_sayfalar.keys())

# Birden fazla sayfayı seçme
seçili_sayfalar = pd.read_excel('çoklu_sayfa.xlsx', sheet_name=['Sayfa1', 'Sayfa2'])
```

#### 3️⃣ Gelişmiş Excel Okuma
```python
# Detaylı parametrelerle Excel okuma
df = pd.read_excel(
    'raporlar.xlsx',
    sheet_name='Satışlar',     # Sayfa adı
    header=1,                  # 2. satırı başlık olarak kullan
    skiprows=2,               # İlk 2 satırı atla
    usecols='A:D',            # A'dan D'ye kadar sütunları oku
    nrows=50,                 # İlk 50 satırı oku
    dtype={'ID': str},        # ID sütununu string olarak oku
    converters={'Tarih': pd.to_datetime}  # Tarih dönüştürücüsü
)
```

### Excel Dosyası Yazma

```python
# DataFrame'i Excel olarak kaydetme
df_satış.to_excel('satış_raporu.xlsx', index=False, sheet_name='Satışlar')

# Çoklu sayfa ile Excel oluşturma
with pd.ExcelWriter('detaylı_rapor.xlsx') as writer:
    df_satış.to_excel(writer, sheet_name='Ham_Veri', index=False)
    df_özet = df_satış.groupby('ürün')['satış_miktarı'].sum()
    df_özet.to_excel(writer, sheet_name='Özet')
    
print("Çoklu sayfalı Excel dosyası oluşturuldu!")
```

## 🔧 Encoding Sorunları ve Çözümleri

Türkçe karakterler ile çalışırken encoding sorunları yaşayabilirsiniz.

### Yaygın Encoding Problemleri

```python
# Problem: Türkçe karakterler yanlış görünüyor
# Çözüm 1: Farklı encoding'ler deneyin
encodings = ['utf-8', 'latin-1', 'cp1254', 'iso-8859-9']

for enc in encodings:
    try:
        df = pd.read_csv('türkçe_veri.csv', encoding=enc)
        print(f"{enc} ile başarılı!")
        print(df.head())
        break
    except UnicodeDecodeError:
        print(f"{enc} çalışmadı, sonrakini deniyorum...")
```

### Güvenli Okuma Fonksiyonu

```python
def güvenli_oku(dosya_yolu, **kwargs):
    """
    Farklı encoding'leri deneyerek güvenli dosya okuma
    """
    encodings = ['utf-8', 'latin-1', 'cp1254', 'iso-8859-9']
    
    for encoding in encodings:
        try:
            df = pd.read_csv(dosya_yolu, encoding=encoding, **kwargs)
            print(f"✅ {encoding} ile başarıyla okundu")
            return df
        except UnicodeDecodeError:
            print(f"❌ {encoding} çalışmadı")
            continue
    
    raise ValueError("Hiçbir encoding çalışmadı!")

# Kullanım
df = güvenli_oku('problemli_dosya.csv')
```

## 📋 Diğer Dosya Formatları

### JSON İşlemleri
```python
# JSON okuma ve yazma
df.to_json('veri.json', orient='records', lines=True, force_ascii=False)
df_json = pd.read_json('veri.json', lines=True)
```

### Parquet İşlemleri (Büyük veriler için)
```python
# Parquet formatı - büyük veriler için ideal
df.to_parquet('veri.parquet', index=False)
df_parquet = pd.read_parquet('veri.parquet')
```

## ⚠️ Dikkat Edilmesi Gerekenler

> **🔤 Encoding**: Türkçe karakterler için `utf-8` encoding kullanın.

> **📊 Büyük Dosyalar**: Büyük dosyalar için `chunksize` parametresini kullanın.

> **💾 Bellek**: Excel dosyaları CSV'lerden daha fazla bellek kullanır.

## 🚨 Sık Yapılan Hatalar

| Hata | Açıklama | Çözüm |
|------|----------|-------|
| `UnicodeDecodeError` | Yanlış encoding | Farklı encoding'leri deneyin (`utf-8`, `latin-1`) |
| `FileNotFoundError` | Dosya bulunamadı | Dosya yolunu kontrol edin |
| `ParserError` | CSV format hatası | `error_bad_lines=False` parametresi ekleyin |
| `xlrd` hatası | Excel kütüphanesi eksik | `pip install openpyxl` komutu çalıştırın |
| `MemoryError` | Dosya çok büyük | `chunksize` parametresi kullanın |

### Büyük Dosyalar için Chunk İşleme

```python
# Büyük dosyaları parça parça okuma
def büyük_dosya_işle(dosya_yolu, chunk_boyutu=10000):
    """
    Büyük CSV dosyasını parça parça işleme
    """
    sonuçlar = []
    
    for chunk in pd.read_csv(dosya_yolu, chunksize=chunk_boyutu):
        # Her parça üzerinde işlem yapın
        işlenmiş_chunk = chunk.groupby('kategori')['fiyat'].mean()
        sonuçlar.append(işlenmiş_chunk)
    
    # Tüm parçaları birleştir
    final_sonuç = pd.concat(sonuçlar).groupby(level=0).mean()
    return final_sonuç

# Kullanım
sonuç = büyük_dosya_işle('çok_büyük_dosya.csv')
```

## 🎯 Egzersizler

### Egzersiz 1: CSV İşlemleri
```python
# 1. Aşağıdaki veriyi CSV olarak kaydedin:
müşteriler = {
    'ad': ['Ahmet Yılmaz', 'Zeynep Kaya', 'Ozan Demir'],
    'şehir': ['İstanbul', 'Ankara', 'İzmir'],
    'yaş': [28, 35, 31],
    'gelir': [45000, 52000, 48000]
}

# 2. Kaydedilen dosyayı tekrar okuyun
# 3. Sadece 'ad' ve 'gelir' sütunlarını içeren yeni bir CSV oluşturun

# Çözüm alanı:

```

### Egzersiz 2: Excel İşlemleri
```python
# 1. Yukarıdaki müşteri verisini Excel olarak kaydedin
# 2. İki farklı sayfa oluşturun: 'MüşteriLista' ve 'Özet'
# 3. Özet sayfasında şehirlere göre ortalama geliri gösterin

# Çözüm alanı:

```

### Egzersiz 3: Hata Yönetimi
```python
# 1. Var olmayan bir dosyayı okumaya çalışın ve hatayı yakalayın
# 2. Try-except bloğu kullanarak güvenli dosya okuma fonksiyonu yazın
# 3. Fonksiyonunuzu test edin

# Çözüm alanı:

```

---# 4. 🛠️ Veri Manipülasyonu ve Temizleme

Gerçek dünyadan gelen veriler nadiren temiz ve analiz için hazır olur. Bu bölümde verileri temizleme ve manipüle etme tekniklerini öğreneceğiz.

## 🕳️ Eksik Veri (Missing Data) Yönetimi

Eksik veriler, veri analizinde en yaygın karşılaşılan problemlerden biridir.

### Eksik Veri Tespiti

```python
import pandas as pd
import numpy as np

# Eksik veriler içeren örnek dataset
veri_ham = {
    'ad': ['Ali', 'Ayşe', 'Mehmet', None, 'Fatma', 'Kemal'],
    'yaş': [25, 30, None, 22, 28, None],
    'maaş': [5000, np.nan, 7000, 4500, None, 6200],
    'şehir': ['İstanbul', 'Ankara', 'İzmir', 'Bursa', None, 'Antalya'],
    'deneyim': [2, 5, None, 1, 3, 8]
}

df = pd.DataFrame(veri_ham)
print("Ham veri:")
print(df)

# Eksik veri kontrolü
print("\nEksik veri sayısı (sütun bazında):")
print(df.isnull().sum())

print("\nEksik veri oranları:")
print((df.isnull().sum() / len(df)) * 100)

# Eksik veri olan satırları göster
print("\nEksik veri içeren satırlar:")
print(df[df.isnull().any(axis=1)])
```

### Eksik Veri ile Çalışma Yöntemleri

#### 1️⃣ Eksik Veriyi Silme
```python
# Eksik veri içeren satırları silme
df_temiz_satır = df.dropna()
print("Eksik satırlar silindikten sonra:")
print(df_temiz_satır)

# Eksik veri içeren sütunları silme
df_temiz_sütun = df.dropna(axis=1)
print("Eksik sütunlar silindikten sonra:")
print(df_temiz_sütun)

# Belirli sütunlarda eksik veri varsa satırı sil
df_seçici_sil = df.dropna(subset=['ad', 'yaş'])
print("Ad veya yaş eksik olan satırlar silindi:")
print(df_seçici_sil)
```

#### 2️⃣ Eksik Veriyi Doldurma
```python
# Sabit değer ile doldurma
df_dolu = df.fillna(0)
print("0 ile doldurulmuş:")
print(df_dolu)

# Farklı sütunlar için farklı değerler
df_akıllı_dolu = df.fillna({
    'ad': 'Bilinmeyen',
    'yaş': df['yaş'].mean(),  # Ortalama ile doldur
    'maaş': df['maaş'].median(),  # Medyan ile doldur
    'şehir': 'Belirtilmemiş',
    'deneyim': 0
})
print("Akıllı doldurma:")
print(df_akıllı_dolu)

# Forward fill (önceki değeri kopyala)
df_ffill = df.fillna(method='ffill')
print("Forward fill:")
print(df_ffill)

# Backward fill (sonraki değeri kopyala)
df_bfill = df.fillna(method='bfill')
print("Backward fill:")
print(df_bfill)
```

#### 3️⃣ İleri Seviye Eksik Veri İşleme
```python
# İnterpolasyon ile doldurma
df_interpolated = df.copy()
df_interpolated['yaş'] = df_interpolated['yaş'].interpolate()
df_interpolated['deneyim'] = df_interpolated['deneyim'].interpolate()
print("İnterpolasyon ile doldurulmuş:")
print(df_interpolated[['yaş', 'deneyim']])

# Gruplara göre ortalama ile doldurma
# Örnek: Şehirlere göre ortalama maaş ile doldurma
df_grup_dolu = df.copy()
df_grup_dolu['maaş'] = df_grup_dolu.groupby('şehir')['maaş'].transform(
    lambda x: x.fillna(x.mean())
)
```

## 🔄 Veri Tipleri Dönüşümü

Doğru veri tipleri, analiz performansı ve doğruluğu için kritiktir.

### Veri Tipi Kontrolü ve Dönüştürme

```python
# Mevcut veri tiplerini kontrol et
print("Mevcut veri tipleri:")
print(df.dtypes)
print("\nDetaylı bilgi:")
print(df.info())

# Veri tipi dönüştürme örnekleri
df_dönüştürülmüş = df.copy()

# String'i sayıya dönüştürme (hatalı veriler varsa)
df_dönüştürülmüş['yaş'] = pd.to_numeric(df_dönüştürülmüş['yaş'], errors='coerce')

# Object'i category'e dönüştürme (bellek tasarrufu)
df_dönüştürülmüş['şehir'] = df_dönüştürülmüş['şehir'].astype('category')

# String'i datetime'a dönüştürme
tarih_verisi = pd.Series(['2024-01-01', '2024-02-15', '2024-03-20'])
df_dönüştürülmüş['başlangıç_tarihi'] = pd.to_datetime(tarih_verisi)

print("Dönüştürülmüş veri tipleri:")
print(df_dönüştürülmüş.dtypes)
```

### Gelişmiş Veri Tipi İşlemleri

```python
# Sayısal veriyi kategorik veye dönüştürme
df['yaş_grubu'] = pd.cut(df['yaş'], 
                        bins=[0, 25, 35, float('inf')], 
                        labels=['Genç', 'Orta Yaş', 'Yaşlı'])

# Boolean sütun oluşturma
df['yüksek_maaş'] = df['maaş'] > df['maaş'].median()

print("Yeni sütunlar eklenmiş DataFrame:")
print(df[['ad', 'yaş', 'yaş_grubu', 'maaş', 'yüksek_maaş']])
```

## 🔄 Duplikasyon Yönetimi

Tekrarlanan veriler analizleri bozabilir.

### Duplikasyon Tespiti ve Temizleme

```python
# Duplikasyon içeren örnek veri
duplikasyon_verisi = pd.DataFrame({
    'id': [1, 2, 3, 2, 4, 3, 5],
    'ad': ['Ali', 'Ayşe', 'Mehmet', 'Ayşe', 'Fatma', 'Mehmet', 'Kemal'],
    'departman': ['IT', 'HR', 'Finance', 'HR', 'IT', 'Finance', 'Marketing'],
    'maaş': [5000, 6000, 7000, 6000, 5500, 7000, 4800]
})

print("Duplikasyon içeren veri:")
print(duplikasyon_verisi)

# Duplikasyon kontrolü
print(f"\nTam duplikasyon sayısı: {duplikasyon_verisi.duplicated().sum()}")
print("Duplikasyon olan satırlar:")
print(duplikasyon_verisi[duplikasyon_verisi.duplicated()])

# Belirli sütunlara göre duplikasyon kontrolü
print(f"\nAd bazında duplikasyon: {duplikasyon_verisi.duplicated(subset=['ad']).sum()}")

# Duplikasyonları temizleme
df_benzersiz = duplikasyon_verisi.drop_duplicates()
print("\nDuplikasyonlar silindikten sonra:")
print(df_benzersiz)

# İlk değeri koru, diğerlerini sil
df_ilk_koru = duplikasyon_verisi.drop_duplicates(subset=['ad'], keep='first')
print("\nAd bazında ilk değerleri koruyarak:")
print(df_ilk_koru)

# Son değeri koru
df_son_koru = duplikasyon_verisi.drop_duplicates(subset=['ad'], keep='last')
print("\nAd bazında son değerleri koruyarak:")
print(df_son_koru)
```

## 📊 Sütun İşlemleri

### Sütun Ekleme, Silme ve Düzenleme

```python
# Yeni sütun ekleme yöntemleri
df_işlem = df.copy()

# Basit sütun ekleme
df_işlem['yeni_sütun'] = 'varsayılan_değer'

# Hesaplanan sütun ekleme
df_işlem['maaş_deneyim_oranı'] = df_işlem['maaş'] / (df_işlem['deneyim'] + 1)

# Apply fonksiyonu ile sütun ekleme
df_işlem['maaş_kategorisi'] = df_işlem['maaş'].apply(
    lambda x: 'Yüksek' if x > 6000 else 'Orta' if x > 4000 else 'Düşük'
)

# Sütun silme
df_işlem = df_işlem.drop(['yeni_sütun'], axis=1)

# Sütun adı değiştirme
df_işlem = df_işlem.rename(columns={
    'ad': 'çalışan_adı',
    'maaş': 'aylık_gelir'
})

print("İşlenmiş DataFrame:")
print(df_işlem.head())
```

### String İşlemleri

```python
# String sütunları ile çalışma
örnek_metinler = pd.DataFrame({
    'isim': ['  Ali Yılmaz  ', 'AYŞE KAYA', 'mehmet demir', 'Fatma ÖZTÜRK'],
    'email': ['ali@email.com', 'ayse@FIRMA.COM', 'mehmet123@gmail.com', 'fatma.ozturk@work.net'],
    'telefon': ['0555-123-45-67', '(0212) 345 67 89', '05551234567', '+90 533 123 45 67']
})

print("Ham string verisi:")
print(örnek_metinler)

# String temizleme işlemleri
temiz_metinler = örnek_metinler.copy()

# Boşlukları temizleme
temiz_metinler['isim'] = temiz_metinler['isim'].str.strip()

# Büyük/küçük harf dönüşümleri
temiz_metinler['isim_title'] = temiz_metinler['isim'].str.title()
temiz_metinler['email_lower'] = temiz_metinler['email'].str.lower()

# String değiştirme
temiz_metinler['telefon_temiz'] = temiz_metinler['telefon'].str.replace(r'[^\d]', '', regex=True)

# String bölme
temiz_metinler[['ad', 'soyad']] = temiz_metinler['isim'].str.split(n=1, expand=True)

print("Temizlenmiş string verisi:")
print(temiz_metinler)
```

## ⚠️ Dikkat Edilmesi Gerekenler

> **🎯 Stratejik Karar**: Eksik veriyi silmek mi yoksa doldurmak mı? Veri setinizin boyutuna ve eksik veri oranına göre karar verin.

> **📊 Veri Tipi Optimizasyonu**: Kategorik veriler için 'category' tipini kullanın, bellek tasarrufu sağlar.

> **🔍 Duplikasyon Kontrolü**: Her veri temizleme işleminden sonra duplikasyon kontrolü yapın.

## 🚨 Sık Yapılan Hatalar

| Hata | Açıklama | Çözüm |
|------|----------|-------|
| `TypeError: can't multiply sequence` | String'i sayı ile çarpmaya çalışma | Veri tipini kontrol edin: `pd.to_numeric()` |
| `ValueError: cannot convert string to float` | String'i float'a dönüştürme hatası | `errors='coerce'` parametresi kullanın |
| Eksik değerlerin gözden kaçması | NaN değerlerinin fark edilmemesi | `df.isnull().sum()` ile düzenli kontrol |
| Duplikasyon kontrolsüzlüğü | Duplikaları fark etmeme | Her veri işleminden sonra `duplicated()` kontrolü |
| Yanlış veri tipi | Object tipinde sayısal veri | `dtypes` kontrolü yapın ve gerekirse dönüştürün |

### Pratik Temizleme Fonksiyonu

```python
def veri_temizle(df, eksik_strateji='drop', duplikasyon_temizle=True):
    """
    Kapsamlı veri temizleme fonksiyonu
    """
    print(f"📊 Başlangıç boyutu: {df.shape}")
    
    # 1. Duplikasyonları temizle
    if duplikasyon_temizle:
        başlangıç_boyut = len(df)
        df = df.drop_duplicates()
        print(f"🔄 Duplikasyon temizleme: {başlangıç_boyut - len(df)} satır silindi")
    
    # 2. Eksik verileri işle
    if eksik_strateji == 'drop':
        başlangıç_boyut = len(df)
        df = df.dropna()
        print(f"🕳️ Eksik veri temizleme: {başlangıç_boyut - len(df)} satır silindi")
    elif eksik_strateji == 'fill':
        for col in df.columns:
            if df[col].dtype in ['int64', 'float64']:
                df[col].fillna(df[col].median(), inplace=True)
            else:
                df[col].fillna(df[col].mode().iloc[0] if not df[col].mode().empty else 'Unknown', inplace=True)
        print("🔧 Eksik veriler dolduruldu")
    
    # 3. String sütunları temizle
    string_columns = df.select_dtypes(include=['object']).columns
    for col in string_columns:
        if df[col].dtype == 'object':
            try:
                df[col] = df[col].str.strip()  # Boşlukları temizle
            except:
                pass
    
    print(f"✅ Final boyut: {df.shape}")
    print(f"📈 Temizlik oranı: %{(1 - len(df)/len(df)) * 100:.1f}")
    
    return df

# Kullanım örneği
# temiz_df = veri_temizle(ham_df, eksik_strateji='fill')
```

## 🎯 Egzersizler

### Egzersiz 1: Eksik Veri Yönetimi
```python
# Aşağıdaki problematik veriyi temizleyin:
problematik_veri = pd.DataFrame({
    'id': [1, 2, 3, 4, 5, 6],
    'isim': ['Ali', None, 'Mehmet', 'Ayşe', '', 'Fatma'],
    'yaş': [25, 30, None, 35, 40, 45],
    'maaş': [5000, None, 7000, 6000, None, 8000],
    'departman': ['IT', 'HR', None, 'Finance', 'IT', 'HR']
})

# 1. Eksik verileri tespit edin
# 2. İsim sütunundaki boş string'i NaN'a çevirin
# 3. Sayısal sütunları ortalama ile, kategorik sütunları mod ile doldurun
# 4. Sonuçları karşılaştırın

# Çözüm alanı:

```

### Egzersiz 2: Duplikasyon Temizleme
```python
# Duplikasyon içeren müşteri verisini temizleyin:
müşteri_verisi = pd.DataFrame({
    'müşteri_id': [101, 102, 103, 102, 104, 103, 105],
    'ad': ['Ali Yılmaz', 'Ayşe Kaya', 'Mehmet Öz', 'Ayşe Kaya', 'Fatma Er', 'Mehmet Öz', 'Kemal As'],
    'email': ['ali@email.com', 'ayse@email.com', 'mehmet@email.com', 'ayse@email.com', 'fatma@email.com', 'mehmet@email.com', 'kemal@email.com'],
    'telefon': ['5551234567', '5559876543', '5555555555', '5559876543', '5553333333', '5555555555', '5551111111']
})

# 1. Tam duplikasyonları bulun
# 2. Email bazında duplikasyonları bulun  
# 3. Her email için en son kaydı tutun
# 4. Sonuç tablosunu gösterin

# Çözüm alanı:

```

### Egzersiz 3: Veri Tipi Dönüşümü
```python
# Ham veriyi düzgün tiplere dönüştürün:
ham_veri = pd.DataFrame({
    'tarih': ['2024-01-01', '2024-02-15', '2024-03-20'],
    'fiyat': ['100.50', '200,75', '150.25'],  # Virgüllü decimal
    'miktar': ['10', '20', '15'],
    'aktif': ['Evet', 'Hayır', 'Evet'],
    'kategori': ['A', 'B', 'A']
})

# 1. Tarih sütununu datetime'a çevirin
# 2. Fiyat sütunundaki virgülü nokta yapın ve float'a çevirin
# 3. Miktar'ı integer'a çevirin
# 4. Aktif'i boolean'a çevirin (Evet=True, Hayır=False)
# 5. Kategori'yi category tipine çevirin

# Çözüm alanı:

```

---# 5. 🔍 Veri Filtreleme ve Seçme

Büyük veri setlerinden istediğiniz kısmı seçmek, veri analizinin temel taşıdır. Pandas'ta bu işlemler için güçlü araçlar mevcuttur.

## 🎯 Temel İndexleme ve Seçim

### Örnek Veri Seti

```python
import pandas as pd
import numpy as np

# Kapsamlı örnek veri seti
np.random.seed(42)
çalışan_verisi = pd.DataFrame({
    'ad': ['Ali Yılmaz', 'Ayşe Kaya', 'Mehmet Öz', 'Fatma Er', 'Kemal As', 
           'Zeynep Ak', 'Ozan Demir', 'Elif Şen', 'Murat Can', 'Selin Kor'],
    'yaş': [28, 32, 45, 29, 38, 26, 41, 35, 31, 27],
    'departman': ['IT', 'HR', 'Finance', 'IT', 'Marketing', 'HR', 'Finance', 'IT', 'Marketing', 'HR'],
    'maaş': [7500, 6500, 9500, 7000, 8200, 6000, 9800, 7800, 8500, 6200],
    'deneyim_yıl': [3, 7, 15, 2, 10, 1, 18, 8, 6, 2],
    'performans_puanı': [85, 92, 78, 88, 95, 82, 89, 91, 87, 84],
    'uzaktan_çalışma': [True, False, True, True, False, True, False, True, False, True]
})

print("Çalışan veri seti:")
print(çalışan_verisi)
print(f"\nVeri boyutu: {çalışan_verisi.shape}")
```

### Sütun Seçme İşlemleri

```python
# Tek sütun seçme
print("Sadece isimler:")
print(çalışan_verisi['ad'])

# Birden fazla sütun seçme
print("\nİsim, departman ve maaş:")
print(çalışan_verisi[['ad', 'departman', 'maaş']])

# Sütun sırasını değiştirerek seçme
print("\nÖzel sıralama:")
seçilen_sütunlar = ['maaş', 'ad', 'departman']
print(çalışan_verisi[seçilen_sütunlar])

# Belirli koşula göre sütunları seçme
sayısal_sütunlar = çalışan_verisi.select_dtypes(include=[np.number]).columns
print(f"\nSayısal sütunlar: {sayısal_sütunlar.tolist()}")
print(çalışan_verisi[sayısal_sütunlar])
```

### Satır Seçme İşlemleri

```python
# Index ile seçme
print("İlk üç çalışan:")
print(çalışan_verisi[:3])

print("\nSon iki çalışan:")
print(çalışan_verisi[-2:])

print("\n2. ve 4. çalışanlar:")
print(çalışan_verisi.iloc[[1, 3]])

# Belirli satır aralığı
print("\n3. ile 6. çalışanlar arası:")
print(çalışan_verisi[2:6])
```

## 🔍 Boolean İndexleme

Boolean indexleme, koşullu filtreleme için en güçlü araçtır.

### Basit Boolean Filtreleme

```python
# Tek koşul
print("Maaşı 8000'den fazla olanlar:")
yüksek_maaş = çalışan_verisi['maaş'] > 8000
print(çalışan_verisi[yüksek_maaş])

# Şıkça kullanılan tek satırda yazım
print("\nIT departmanı çalışanları:")
print(çalışan_verisi[çalışan_verisi['departman'] == 'IT'])

# String kontrolleri
print("\nAdında 'A' harfi geçenler:")
print(çalışan_verisi[çalışan_verisi['ad'].str.contains('A')])
```

### Çoklu Koşul Filtreleme

```python
# AND koşulu (&)
print("IT'de çalışan VE maaşı 7500'den fazla olanlar:")
it_yüksek_maaş = (çalışan_verisi['departman'] == 'IT') & (çalışan_verisi['maaş'] > 7500)
print(çalışan_verisi[it_yüksek_maaş])

# OR koşulu (|)
print("\nHR'da çalışan VEYA uzaktan çalışanlar:")
hr_veya_uzak = (çalışan_verisi['departman'] == 'HR') | (çalışan_verisi['uzaktan_çalışma'] == True)
print(çalışan_verisi[hr_veya_uzak])

# NOT koşulu (~)
print("\nIT departmanında olmayanlar:")
it_olmayanlar = ~(çalışan_verisi['departman'] == 'IT')
print(çalışan_verisi[it_olmayanlar])

# Karmaşık koşul örneği
print("\nYaşı 30-40 arası, performans puanı 85'den yüksek, IT veya Finance'ta çalışanlar:")
karmaşık_filtre = (
    (çalışan_verisi['yaş'] >= 30) & 
    (çalışan_verisi['yaş'] <= 40) &
    (çalışan_verisi['performans_puanı'] > 85) &
    (çalışan_verisi['departman'].isin(['IT', 'Finance']))
)
print(çalışan_verisi[karmaşık_filtre])
```

### Gelişmiş Boolean İşlemleri

```python
# isin() ile çoklu değer kontrolü
print("HR, IT veya Finance departmanlarında çalışanlar:")
seçili_departmanlar = ['HR', 'IT', 'Finance']
print(çalışan_verisi[çalışan_verisi['departman'].isin(seçili_departmanlar)])

# between() ile aralık kontrolü
print("\nMaaşı 7000-8500 arasında olanlar:")
print(çalışan_verisi[çalışan_verisi['maaş'].between(7000, 8500)])

# String işlemleri ile filtreleme
print("\nAdı 'A' ile başlayanlar:")
print(çalışan_verisi[çalışan_verisi['ad'].str.startswith('A')])

print("\nSoyadında 'er' geçenler:")
print(çalışan_verisi[çalışan_verisi['ad'].str.contains('er', case=False)])
```

## 📍 loc ve iloc Kullanımı

`loc` ve `iloc` daha hassas veri seçimi için kullanılır.

### iloc - Pozisyon Bazlı Seçim

```python
# iloc[satır, sütun] formatında çalışır
print("2. satır, 3. sütun:")
print(çalışan_verisi.iloc[1, 2])

print("\nİlk 3 satır, ilk 4 sütun:")
print(çalışan_verisi.iloc[:3, :4])

print("\nSon 2 satır, son 3 sütun:")
print(çalışan_verisi.iloc[-2:, -3:])

# Belirli satır ve sütunları seçme
print("\n1., 3., 5. satırlar ve 0., 2., 4. sütunlar:")
print(çalışan_verisi.iloc[[0, 2, 4], [0, 2, 4]])

# Tüm satırlar, belirli sütunlar
print("\nTüm satırlar, 2. ve 4. sütunlar:")
print(çalışan_verisi.iloc[:, [1, 3]])
```

### loc - Etiket Bazlı Seçim

```python
# Sütun adları ile seçim
print("Belirli satırlar ve sütunlar:")
print(çalışan_verisi.loc[:3, ['ad', 'departman', 'maaş']])

# Boolean indexleme ile loc kullanımı
print("\nIT çalışanlarının ad ve maaş bilgileri:")
it_çalışanları = çalışan_verisi['departman'] == 'IT'
print(çalışan_verisi.loc[it_çalışanları, ['ad', 'maaş']])

# Index'i sütun olarak ayarlayarak loc kullanımı
df_isim_index = çalışan_verisi.set_index('ad')
print("\nAli Yılmaz'ın bilgileri:")
print(df_isim_index.loc['Ali Yılmaz'])

# Çoklu index seçimi
print("\nBelirli kişilerin maaş bilgileri:")
seçili_kişiler = ['Ali Yılmaz', 'Ayşe Kaya', 'Mehmet Öz']
print(df_isim_index.loc[seçili_kişiler, 'maaş'])
```

## 🔎 query() Fonksiyonu

`query()` fonksiyonu, SQL benzeri bir söz dizimi ile filtreleme yapar.

### Basit Query Örnekleri

```python
# Basit koşullar
print("Maaşı 7500'den büyük olanlar (query ile):")
print(çalışan_verisi.query('maaş > 7500'))

print("\nIT departmanı çalışanları (query ile):")
print(çalışan_verisi.query('departman == "IT"'))

# Çoklu koşullar
print("\nYaşı 30'dan büyük VE performans puanı 85'den yüksek olanlar:")
print(çalışan_verisi.query('yaş > 30 and performans_puanı > 85'))

print("\nHR çalışanları VEYA uzaktan çalışanlar:")
print(çalışan_verisi.query('departman == "HR" or uzaktan_çalışma == True'))
```

### Gelişmiş Query Kullanımı

```python
# Değişken kullanımı
min_maaş = 7000
max_yaş = 35

print(f"Maaşı {min_maaş}'den fazla ve yaşı {max_yaş}'den küçük olanlar:")
print(çalışan_verisi.query('maaş > @min_maaş and yaş < @max_yaş'))

# Liste ile kontrol
hedef_departmanlar = ['IT', 'Finance']
print("IT veya Finance departmanlarında çalışanlar:")
print(çalışan_verisi.query('departman in @hedef_departmanlar'))

# String işlemleri
print("Adında 'e' harfi geçenler:")
print(çalışan_verisi.query('ad.str.contains("e", case=False)'))

# Aralık kontrolü
print("Deneyimi 5-15 yıl arası olanlar:")
print(çalışan_verisi.query('5 <= deneyim_yıl <= 15'))
```

## 📊 Örnekleme (Sampling)

Büyük veri setlerinden rastgele örnekler almak için.

```python
# Rastgele örnekleme
print("Rastgele 3 çalışan:")
print(çalışan_verisi.sample(n=3, random_state=42))

# Yüzdelik örnekleme
print("\nVerinin %30'u:")
print(çalışan_verisi.sample(frac=0.3, random_state=42))

# Stratified sampling (gruplar arası dengeli örnekleme)
print("\nHer departmandan 2'şer kişi:")
dengeli_örnek = çalışan_verisi.groupby('departman').apply(
    lambda x: x.sample(min(len(x), 2), random_state=42)
).reset_index(drop=True)
print(dengeli_örnek)
```

## ⚠️ Dikkat Edilmesi Gerekenler

> **🔗 Parantez Kullanımı**: Çoklu Boolean koşullarda mutlaka parantez kullanın: `(kondisyon1) & (kondisyon2)`

> **🔍 loc vs iloc**: `loc` etiket bazlı, `iloc` pozisyon bazlıdır. Karıştırmayın!

> **⚡ Performans**: Büyük veriler için `query()` daha hızlı olabilir.

## 🚨 Sık Yapılan Hatalar

| Hata | Açıklama | Çözüm |
|------|----------|-------|
| `ValueError: The truth value is ambiguous` | Boolean koşullarda parantez eksikliği | `(df['A'] > 5) & (df['B'] < 10)` şeklinde yazın |
| `KeyError: 'sütun_adı'` | Olmayan sütuna erişim | `df.columns` ile sütun listesini kontrol edin |
| `TypeError: cannot use & with these operands` | and/or kullanımı yerine &/\| kullanımı | Boolean işlemlerde `&`, `|`, `~` kullanın |
| `IndexError: single positional indexer is out-of-bounds` | iloc ile yanlış index | Index sınırlarını kontrol edin |
| `SettingWithCopyWarning` | Kopyalama uyarısı | `.copy()` ile açık kopya oluşturun |

### Güvenli Filtreleme Fonksiyonu

```python
def güvenli_filtrele(df, koşul_dict):
    """
    Güvenli filtreleme fonksiyonu
    
    Parametreler:
    df: DataFrame
    koşul_dict: {'sütun': {'operator': 'değer'}} formatında koşullar
    
    Örnek: güvenli_filtrele(df, {'yaş': {'>=': 25}, 'departman': {'==': 'IT'}})
    """
    filtreli_df = df.copy()
    
    for sütun, koşullar in koşul_dict.items():
        if sütun not in df.columns:
            print(f"⚠️ Uyarı: '{sütun}' sütunu bulunamadı!")
            continue
            
        for operator, değer in koşullar.items():
            try:
                if operator == '==':
                    filtreli_df = filtreli_df[filtreli_df[sütun] == değer]
                elif operator == '!=':
                    filtreli_df = filtreli_df[filtreli_df[sütun] != değer]
                elif operator == '>':
                    filtreli_df = filtreli_df[filtreli_df[sütun] > değer]
                elif operator == '>=':
                    filtreli_df = filtreli_df[filtreli_df[sütun] >= değer]
                elif operator == '<':
                    filtreli_df = filtreli_df[filtreli_df[sütun] < değer]
                elif operator == '<=':
                    filtreli_df = filtreli_df[filtreli_df[sütun] <= değer]
                elif operator == 'in':
                    filtreli_df = filtreli_df[filtreli_df[sütun].isin(değer)]
                    
            except Exception as e:
                print(f"❌ Hata: {sütun} sütununda {operator} {değer} koşulu uygulanamadı: {e}")
                
    print(f"📊 Filtreleme tamamlandı: {len(df)} → {len(filtreli_df)} satır")
    return filtreli_df

# Kullanım örneği
sonuç = güvenli_filtrele(çalışan_verisi, {
    'yaş': {'>=': 30},
    'departman': {'in': ['IT', 'Finance']},
    'maaş': {'>': 7000}
})
```

## 🎯 Egzersizler

### Egzersiz 1: Basit Filtreleme
```python
# Yukarıdaki çalışan_verisi DataFrame'ini kullanarak:
# 1. Yaşı 30'dan büyük çalışanları bulun
# 2. Marketing departmanında çalışanları listeleyin
# 3. Performans puanı 90'dan yüksek olanları gösterin
# 4. Uzaktan çalışmayanları filtreleyin

# Çözüm alanı:

```

### Egzersiz 2: Karmaşık Filtreleme
```python
# Aşağıdaki koşulları sağlayan çalışanları bulun:
# 1. Yaşı 25-40 arasında VE
# 2. Maaşı departman ortalamasından yüksek VE
# 3. Deneyimi 5+ yıl VEYA performans puanı 90+

# İpucu: Departman ortalaması için groupby().transform() kullanabilirsiniz

# Çözüm alanı:

```

### Egzersiz 3: loc/iloc Pratiği
```python
# 1. iloc kullanarak ilk 5 satır, son 3 sütunu seçin
# 2. loc kullanarak IT departmanı çalışanlarının ad ve maaş bilgilerini alın
# 3. Query kullanarak deneyimi 5+ yıl olanları filtrelein
# 4. Her departmandan rastgele 1 çalışan seçin

# Çözüm alanı:

```

### Egzersiz 4: Filtreleme Kombinasyonları
```python
# Aşağıdaki gereksinimleri karşılayan bir filtreleme sistemi oluşturun:
# 1. Kullanıcı departman seçebilsin
# 2. Minimum ve maksimum maaş belirleyebilsin
# 3. Uzaktan çalışma durumunu filtreleybilsin
# 4. Sonuçları performans puanına göre sıralayabilsin

# Fonksiyon imzası:
def çalışan_filtrele(df, departmanlar=None, min_maaş=0, max_maaş=float('inf'), 
                    uzaktan_çalışma=None, sıralama='performans_puanı'):
    """
    Çok kriterli çalışan filtreleme fonksiyonu
    """
    # Kodunuzu buraya yazın
    pass

# Test edin:
# sonuç = çalışan_filtrele(çalışan_verisi, departmanlar=['IT', 'HR'], min_maaş=7000, uzaktan_çalışma=True)

# Çözüm alanı:

```

---# 6. 📈 Temel İstatistiksel Analizler

İstatistiksel analiz, veriyi anlamak ve içgörü elde etmek için hayati önem taşır. Pandas, temel istatistiksel hesaplamalar için zengin araçlar sunar.

## 📊 Örnek Veri Seti

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# Satış veri seti oluşturalım
np.random.seed(42)
n = 1000

satış_verisi = pd.DataFrame({
    'tarih': pd.date_range('2024-01-01', periods=n, freq='D'),
    'ürün_kategorisi': np.random.choice(['Elektronik', 'Giyim', 'Kitap', 'Ev Eşyası', 'Spor'], n),
    'satış_miktarı': np.random.poisson(lam=10, size=n),
    'birim_fiyat': np.random.gamma(shape=2, scale=50, size=n),
    'müşteri_yaşı': np.random.normal(loc=35, scale=12, size=n),
    'satış_temsilcisi': np.random.choice(['Ali', 'Ayşe', 'Mehmet', 'Fatma', 'Kemal'], n),
    'bölge': np.random.choice(['İstanbul', 'Ankara', 'İzmir', 'Antalya'], n),
    'sezon': np.random.choice(['İlkbahar', 'Yaz', 'Sonbahar', 'Kış'], n)
})

# Türetilmiş sütunlar
satış_verisi['toplam_gelir'] = satış_verisi['satış_miktarı'] * satış_verisi['birim_fiyat']
satış_verisi['ay'] = satış_verisi['tarih'].dt.month
satış_verisi['haftanın_günü'] = satış_verisi['tarih'].dt.day_name()

print("Satış veri seti:")
print(satış_verisi.head())
print(f"Veri boyutu: {satış_verisi.shape}")
```

## 🔍 describe() - Temel İstatistiklerin Özeti

`describe()` fonksiyonu, sayısal veriler için temel istatistikleri özetler.

### Sayısal Veriler için describe()

```python
# Tüm sayısal sütunlar için özet istatistikler
print("Sayısal sütunlar için özet istatistikler:")
print(satış_verisi.describe())

# Belirli sütunlar için
print("\nSadece gelir ve müşteri yaşı için:")
print(satış_verisi[['toplam_gelir', 'müşteri_yaşı']].describe())

# Yüzdelik dilimler özelleştirme
print("\nDetaylı yüzdelik dilimler:")
print(satış_verisi['toplam_gelir'].describe(percentiles=[.1, .25, .5, .75, .9, .95]))
```

### Kategorik Veriler için describe()

```python
# Kategorik veriler için özet
print("Kategorik sütunlar için özet:")
print(satış_verisi.describe(include='object'))

# Belirli bir kategorik sütun için detay
print("\nÜrün kategorisi detayları:")
print(satış_verisi['ürün_kategorisi'].describe())
```

### Manuel İstatistik Hesapları

```python
# Temel istatistikleri manuel olarak hesaplama
toplam_gelir = satış_verisi['toplam_gelir']

print("Manuel istatistikler:")
print(f"Ortalama: {toplam_gelir.mean():.2f}")
print(f"Medyan: {toplam_gelir.median():.2f}")
print(f"Standart sapma: {toplam_gelir.std():.2f}")
print(f"Varyans: {toplam_gelir.var():.2f}")
print(f"Minimum: {toplam_gelir.min():.2f}")
print(f"Maksimum: {toplam_gelir.max():.2f}")
print(f"Çeyreklik açıklığı (IQR): {toplam_gelir.quantile(0.75) - toplam_gelir.quantile(0.25):.2f}")
print(f"Çarpıklık: {toplam_gelir.skew():.2f}")
print(f"Basıklık: {toplam_gelir.kurtosis():.2f}")
```

## 📊 value_counts() - Frekans Analizi

`value_counts()` kategorik verilerin dağılımını analiz eder.

### Basit Frekans Analizi

```python
# Ürün kategorilerinin dağılımı
print("Ürün kategori dağılımı:")
kategori_dağılım = satış_verisi['ürün_kategorisi'].value_counts()
print(kategori_dağılım)

# Yüzdelik dağılım
print("\nYüzdelik dağılım:")
print(satış_verisi['ürün_kategorisi'].value_counts(normalize=True) * 100)

# Bölge dağılımı
print("\nBölge dağılımı:")
print(satış_verisi['bölge'].value_counts().sort_values(ascending=False))
```

### Gelişmiş Frekans Analizi

```python
# Birden fazla sütun için cross-tabulation
print("Bölge ve ürün kategorisi cross-tabulation:")
çapraz_tablo = pd.crosstab(satış_verisi['bölge'], satış_verisi['ürün_kategorisi'])
print(çapraz_tablo)

# Yüzdelik cross-tabulation
print("\nYüzdelik dağılım (satır bazlı):")
yüzdelik_tablo = pd.crosstab(satış_verisi['bölge'], satış_verisi['ürün_kategorisi'], 
                           normalize='index') * 100
print(yüzdelik_tablo.round(2))

# Sayısal veriyi kategorik hale getirip frekans analizi
satış_verisi['gelir_kategori'] = pd.cut(satış_verisi['toplam_gelir'], 
                                       bins=5, 
                                       labels=['Çok Düşük', 'Düşük', 'Orta', 'Yüksek', 'Çok Yüksek'])
print("\nGelir kategori dağılımı:")
print(satış_verisi['gelir_kategori'].value_counts().sort_index())
```

## 🔗 Korelasyon Analizi

Korelasyon, değişkenler arasındaki ilişkiyi ölçer.

### Temel Korelasyon

```python
# Sayısal sütunlar için korelasyon matrisi
sayısal_sütunlar = ['satış_miktarı', 'birim_fiyat', 'müşteri_yaşı', 'toplam_gelir', 'ay']
korelasyon_matrisi = satış_verisi[sayısal_sütunlar].corr()

print("Korelasyon matrisi:")
print(korelasyon_matrisi.round(3))

# Belirli bir sütunla diğerleri arasındaki korelasyon
print("\nToplam gelir ile diğer değişkenler arası korelasyon:")
gelir_korelasyon = satış_verisi[sayısal_sütunlar].corr()['toplam_gelir'].sort_values(ascending=False)
print(gelir_korelasyon)

# En yüksek korelasyonları bulma
def güçlü_korelasyonları_bul(df, eşik=0.5):
    """Eşikten yüksek korelasyonları bulan fonksiyon"""
    corr_matrix = df.corr()
    güçlü_korelasyonlar = []
    
    for i in range(len(corr_matrix.columns)):
        for j in range(i+1, len(corr_matrix.columns)):
            if abs(corr_matrix.iloc[i, j]) > eşik:
                güçlü_korelasyonlar.append({
                    'değişken1': corr_matrix.columns[i],
                    'değişken2': corr_matrix.columns[j],
                    'korelasyon': corr_matrix.iloc[i, j]
                })
    
    return pd.DataFrame(güçlü_korelasyonlar).sort_values('korelasyon', key=abs, ascending=False)

güçlü_kor = güçlü_korelasyonları_bul(satış_verisi[sayısal_sütunlar], eşik=0.3)
print("\nGüçlü korelasyonlar (>0.3):")
print(güçlü_kor)
```

### Korelasyon Görselleştirme

```python
# Korelasyon ısı haritası oluşturma
import matplotlib.pyplot as plt
import seaborn as sns

plt.figure(figsize=(10, 8))
sns.heatmap(korelasyon_matrisi, annot=True, cmap='coolwarm', center=0, 
            square=True, linewidths=0.5, fmt='.3f')
plt.title('Korelasyon Isı Haritası')
plt.tight_layout()
plt.savefig('/workspace/korelasyon_haritasi.png', dpi=150, bbox_inches='tight')
print("Korelasyon ısı haritası kaydedildi: /workspace/korelasyon_haritasi.png")
```

## 🏢 Gruplandırma İstatistikleri

Kategorik değişkenlere göre grup istatistikleri.

### Basit Gruplandırma

```python
# Ürün kategorisine göre ortalama satış
print("Kategori bazında ortalama satış miktarı:")
kategori_ortalaması = satış_verisi.groupby('ürün_kategorisi')['satış_miktarı'].mean()
print(kategori_ortalaması.sort_values(ascending=False))

# Bölgelere göre toplam gelir
print("\nBölge bazında toplam gelir:")
bölge_gelir = satış_verisi.groupby('bölge')['toplam_gelir'].sum()
print(bölge_gelir.sort_values(ascending=False))

# Satış temsilcisine göre performans
print("\nSatış temsilcisi performansı:")
temsilci_performans = satış_verisi.groupby('satış_temsilcisi').agg({
    'toplam_gelir': ['sum', 'mean', 'count'],
    'satış_miktarı': 'mean'
}).round(2)
print(temsilci_performans)
```

### Çok Seviyeli Gruplandırma

```python
# Bölge ve kategoriye göre analiz
print("Bölge-Kategori bazında analiz:")
çok_grup = satış_verisi.groupby(['bölge', 'ürün_kategorisi']).agg({
    'toplam_gelir': ['count', 'mean', 'sum'],
    'satış_miktarı': 'mean'
}).round(2)

print(çok_grup)

# En iyi performans gösteren kombinasyonlar
en_iyi_kombinasyonlar = çok_grup['toplam_gelir']['sum'].sort_values(ascending=False).head(10)
print("\nEn yüksek gelir getiren bölge-kategori kombinasyonları:")
print(en_iyi_kombinasyonlar)
```

## 📋 Pivot Tablolar

Pivot tablolar, verileri özetlemek için güçlü bir araçtır.

### Basit Pivot Tablo

```python
# Bölge ve kategori pivot tablosu
pivot_gelir = satış_verisi.pivot_table(
    values='toplam_gelir',
    index='bölge',
    columns='ürün_kategorisi',
    aggfunc='sum',
    fill_value=0
)

print("Gelir Pivot Tablosu:")
print(pivot_gelir.round(2))

# Satış miktarı pivot tablosu
pivot_miktar = satış_verisi.pivot_table(
    values='satış_miktarı',
    index='bölge',
    columns='ürün_kategorisi',
    aggfunc='mean',
    fill_value=0
)

print("\nOrtalama Satış Miktarı Pivot Tablosu:")
print(pivot_miktar.round(2))
```

### Gelişmiş Pivot Analizi

```python
# Çok fonksiyonlu pivot tablo
çoklu_pivot = satış_verisi.pivot_table(
    values=['toplam_gelir', 'satış_miktarı'],
    index=['bölge', 'sezon'],
    columns='ürün_kategorisi',
    aggfunc={'toplam_gelir': 'sum', 'satış_miktarı': 'mean'},
    fill_value=0,
    margins=True  # Toplam satırı ve sütunu ekler
)

print("Çoklu Pivot Tablosu (ilk 10 satır):")
print(çoklu_pivot.head(10))

# Zaman serisi pivot analizi
satış_verisi['ay_adı'] = satış_verisi['tarih'].dt.strftime('%B')
aylık_trend = satış_verisi.pivot_table(
    values='toplam_gelir',
    index='ay_adı',
    columns='ürün_kategorisi',
    aggfunc='sum'
)

print("\nAylık gelir trendi:")
print(aylık_trend.fillna(0).round(2))
```

## 🎯 İstatistiksel Testler ve Analizler

### Outlier (Aykırı Değer) Tespiti

```python
def aykırı_değerleri_bul(series, method='IQR'):
    """
    Aykırı değerleri tespit eden fonksiyon
    """
    if method == 'IQR':
        Q1 = series.quantile(0.25)
        Q3 = series.quantile(0.75)
        IQR = Q3 - Q1
        alt_sınır = Q1 - 1.5 * IQR
        üst_sınır = Q3 + 1.5 * IQR
        
        aykırı_değerler = series[(series < alt_sınır) | (series > üst_sınır)]
        
    elif method == 'z-score':
        z_scores = np.abs((series - series.mean()) / series.std())
        aykırı_değerler = series[z_scores > 3]
    
    return aykırı_değerler

# Toplam gelirde aykırı değerler
aykırı_gelir = aykırı_değerleri_bul(satış_verisi['toplam_gelir'], method='IQR')
print(f"Toplam gelirde {len(aykırı_gelir)} aykırı değer tespit edildi")
print(f"Aykırı değer oranı: %{len(aykırı_gelir)/len(satış_verisi)*100:.2f}")

print("\nAykırı değerlerin özeti:")
print(aykırı_gelir.describe())
```

### Dağılım Analizi

```python
# Dağılım istatistikleri
print("Toplam gelir dağılım analizi:")
gelir = satış_verisi['toplam_gelir']

print(f"Ortalama: {gelir.mean():.2f}")
print(f"Medyan: {gelir.median():.2f}")
print(f"Mod: {gelir.mode().iloc[0]:.2f}")
print(f"Standart sapma: {gelir.std():.2f}")
print(f"Çarpıklık: {gelir.skew():.2f}")
print(f"Basıklık: {gelir.kurtosis():.2f}")

# Çarpıklık yorumu
if gelir.skew() > 0.5:
    print("→ Dağılım sağa çarpık (pozitif çarpıklık)")
elif gelir.skew() < -0.5:
    print("→ Dağılım sola çarpık (negatif çarpıklık)")
else:
    print("→ Dağılım yaklaşık simetrik")
```

## ⚠️ Dikkat Edilmesi Gerekenler

> **📊 Medyan vs Ortalama**: Aykırı değerler varsa medyan daha güvenilir bir merkezi eğilim ölçüsüdür.

> **🔗 Korelasyon ≠ Nedensellik**: Yüksek korelasyon, nedensellik anlamına gelmez.

> **📈 Normallik**: Çoğu istatistiksel test, verilerin normal dağıldığını varsayar.

## 🚨 Sık Yapılan Hatalar

| Hata | Açıklama | Çözüm |
|------|----------|-------|
| Aykırı değerleri görmezden gelme | Analizleri çarpıtabilir | Aykırı değer analizi yapın |
| Yanlış agregasyon fonksiyonu | sum yerine mean kullanmak | Analiz amacına uygun fonksiyon seçin |
| Eksik değerlerle istatistik | NaN değerler hesaplamaları bozar | `dropna()` veya `fillna()` kullanın |
| Kategorik veriye sayısal analiz | Anlamsız sonuçlar | Veri tiplerini kontrol edin |
| Küçük örneklem hatası | İstatistikler güvenilir olmayabilir | Yeterli veri olduğundan emin olun |

## 🎯 Egzersizler

### Egzersiz 1: Temel İstatistikler
```python
# Yukarıdaki satış_verisi DataFrame'ini kullanarak:
# 1. Her ürün kategorisi için ortalama birim fiyat hesaplayın
# 2. En yüksek ve en düşük toplam gelirli günleri bulun
# 3. Müşteri yaşlarının dağılım istatistiklerini hesaplayın
# 4. Hangi ay en çok satış yapıldığını bulun

# Çözüm alanı:

```

### Egzersiz 2: Korelasyon Analizi
```python
# 1. Satış miktarı ile müşteri yaşı arasındaki korelasyonu hesaplayın
# 2. 0.3'ten yüksek korelasyonları listeleyin
# 3. En güçlü pozitif ve negatif korelasyonları bulun
# 4. Korelasyon matrisini görselleştirin

# Çözüm alanı:

```

### Egzersiz 3: Pivot Analizi
```python
# 1. Satış temsilcisi ve bölgelere göre toplam gelir pivot tablosu oluşturun
# 2. Sezonlara göre ortalama satış miktarını analiz edin
# 3. Her bölgenin en çok gelir getiren kategorisini bulun
# 4. Haftanın günlerine göre satış trendini analiz edin

# Çözüm alanı:

```

### Egzersiz 4: Kapsamlı Analiz
```python
# Aşağıdaki soruları yanıtlayacak kapsamlı bir analiz yapın:
# 1. Hangi faktörler toplam geliri en çok etkiliyor?
# 2. En karlı bölge-kategori kombinasyonu hangisi?
# 3. Sezonsal trendler var mı?
# 4. Satış temsilcilerinin performansları nasıl?
# 5. Aykırı değerler analizi nasıl ürünleri etkiliyor?

# Fonksiyon yazarak analizinizi organize edin:
def kapsamlı_satış_analizi(df):
    """
    Kapsamlı satış verisi analizi
    """
    print("📊 KAPSAMLI SATIŞ ANALİZİ RAPORU")
    print("="*50)
    
    # Analizlerinizi buraya yazın
    
    return None

# kapsamlı_satış_analizi(satış_verisi)

# Çözüm alanı:

```

---# 7. 📋 Gruplandırma ve Pivot Tablolar

Veri analizinde en güçlü araçlardan biri gruplandırmadır. Pandas'ın `groupby()` fonksiyonu ve pivot tablolar, verileri kategorilere ayırıp analiz etmenizi sağlar.

## 👥 groupby() Temelleri

### Basit Gruplandırma

```python
import pandas as pd
import numpy as np

# Şirket çalışanları veri seti
np.random.seed(42)
çalışanlar = pd.DataFrame({
    'ad': ['Ali', 'Ayşe', 'Mehmet', 'Fatma', 'Kemal', 'Zeynep', 'Ozan', 'Elif', 'Murat', 'Selin',
           'Can', 'Deniz', 'Emre', 'Gül', 'Hakan', 'İrem', 'Jale', 'Kaan', 'Lale', 'Mine'],
    'departman': np.random.choice(['IT', 'HR', 'Finance', 'Marketing', 'Sales'], 20),
    'şehir': np.random.choice(['İstanbul', 'Ankara', 'İzmir', 'Bursa'], 20),
    'yaş': np.random.randint(22, 55, 20),
    'maaş': np.random.randint(4000, 12000, 20),
    'deneyim_yıl': np.random.randint(0, 20, 20),
    'performans_notu': np.random.randint(60, 100, 20)
})

print("Çalışan veri seti:")
print(çalışanlar.head(10))
```

### Tek Sütuna Göre Gruplandırma

```python
# Departmana göre gruplandırma
print("Departmana göre ortalama maaş:")
dept_ortalama = çalışanlar.groupby('departman')['maaş'].mean()
print(dept_ortalama.sort_values(ascending=False))

print("\nDepartmana göre çalışan sayısı:")
dept_sayı = çalışanlar.groupby('departman').size()
print(dept_sayı.sort_values(ascending=False))

# Birden fazla istatistik
print("\nDepartman bazında detaylı istatistikler:")
dept_detay = çalışanlar.groupby('departman')['maaş'].agg(['count', 'mean', 'std', 'min', 'max'])
print(dept_detay.round(2))
```

### Çoklu Sütuna Göre Gruplandırma

```python
# Departman ve şehre göre gruplandırma
print("Departman-Şehir bazında ortalama maaş:")
çoklu_grup = çalışanlar.groupby(['departman', 'şehir'])['maaş'].mean()
print(çoklu_grup.sort_values(ascending=False))

# Unstack ile pivot benzeri görünüm
print("\nPivot benzeri görünüm:")
pivot_görünüm = çalışanlar.groupby(['departman', 'şehir'])['maaş'].mean().unstack(fill_value=0)
print(pivot_görünüm.round(0))
```

## 🔢 Aggregation (Toplama) Fonksiyonları

### Temel Aggregation

```python
# Birden fazla sütun için aggregation
print("Departman bazında çoklu istatistikler:")
dept_agg = çalışanlar.groupby('departman').agg({
    'maaş': ['mean', 'std', 'count'],
    'yaş': ['mean', 'min', 'max'],
    'deneyim_yıl': ['mean', 'sum'],
    'performans_notu': ['mean', 'std']
}).round(2)

print(dept_agg)

# Sütun isimlerini düzenleme
dept_agg.columns = ['_'.join(col).strip() for col in dept_agg.columns.values]
print("\nDüzenlenmiş sütun isimleri ile:")
print(dept_agg.head())
```

### Özel Aggregation Fonksiyonları

```python
# Özel fonksiyonlar tanımlama
def maaş_aralığı(series):
    return series.max() - series.min()

def performans_kategorisi(series):
    if series.mean() >= 85:
        return 'Mükemmel'
    elif series.mean() >= 75:
        return 'İyi'
    else:
        return 'Geliştirilmeli'

# Özel fonksiyonları kullanma
print("Departman bazında özel metrikler:")
özel_metrikler = çalışanlar.groupby('departman').agg({
    'maaş': ['mean', maaş_aralığı],
    'performans_notu': ['mean', performans_kategorisi]
}).round(2)

print(özel_metrikler)

# Lambda fonksiyonları ile
print("\nLambda fonksiyonları ile:")
lambda_agg = çalışanlar.groupby('departman').agg({
    'maaş': [lambda x: x.max() - x.min(), lambda x: len(x[x > x.median()])],
    'yaş': lambda x: x.quantile(0.75)
}).round(2)

print(lambda_agg)
```

### Named Aggregation (Pandas 0.25+)

```python
# Daha temiz aggregation söz dizimi
print("Named aggregation ile temiz söz dizimi:")
temiz_agg = çalışanlar.groupby('departman').agg(
    ortalama_maaş=('maaş', 'mean'),
    medyan_maaş=('maaş', 'median'),
    çalışan_sayısı=('ad', 'count'),
    min_yaş=('yaş', 'min'),
    max_yaş=('yaş', 'max'),
    ortalama_performans=('performans_notu', 'mean')
).round(2)

print(temiz_agg)
```

## 🔄 Transform ve Apply

### Transform İşlemleri

```python
# Transform - grup bazlı hesaplamalar
print("Her çalışanın departman ortalamasından farkı:")

# Departman ortalamasını hesapla ve her satıra ekle
çalışanlar['dept_ortalama_maaş'] = çalışanlar.groupby('departman')['maaş'].transform('mean')
çalışanlar['maaş_farkı'] = çalışanlar['maaş'] - çalışanlar['dept_ortalama_maaş']

print(çalışanlar[['ad', 'departman', 'maaş', 'dept_ortalama_maaş', 'maaş_farkı']].head())

# Z-score hesaplama (standartlaştırma)
çalışanlar['maaş_z_score'] = çalışanlar.groupby('departman')['maaş'].transform(
    lambda x: (x - x.mean()) / x.std()
)

print("\nDepartman içi maaş z-score'ları:")
print(çalışanlar[['ad', 'departman', 'maaş', 'maaş_z_score']].round(2))
```

### Apply İşlemleri

```python
# Apply - her grup için özel fonksiyon
def departman_analizi(grup):
    """Her departman için detaylı analiz"""
    analiz = pd.Series({
        'çalışan_sayısı': len(grup),
        'ortalama_maaş': grup['maaş'].mean(),
        'maaş_std': grup['maaş'].std(),
        'deneyimli_çalışan_oranı': len(grup[grup['deneyim_yıl'] > 5]) / len(grup),
        'yüksek_performans_oranı': len(grup[grup['performans_notu'] > 85]) / len(grup),
        'en_genç': grup['yaş'].min(),
        'en_yaşlı': grup['yaş'].max()
    })
    return analiz

print("Departman bazında detaylı analiz:")
dept_analiz = çalışanlar.groupby('departman').apply(departman_analizi).round(3)
print(dept_analiz)
```

## 🏆 En İyi Performans Gösterenleri Bulma

```python
# Her departmanın en yüksek maaşlı çalışanı
print("Her departmanın en yüksek maaşlı çalışanı:")
en_yüksek_maaş = çalışanlar.loc[çalışanlar.groupby('departman')['maaş'].idxmax()]
print(en_yüksek_maaş[['ad', 'departman', 'maaş']])

# Her şehrin en deneyimli çalışanı
print("\nHer şehrin en deneyimli çalışanı:")
en_deneyimli = çalışanlar.loc[çalışanlar.groupby('şehir')['deneyim_yıl'].idxmax()]
print(en_deneyimli[['ad', 'şehir', 'deneyim_yıl']])

# Top N seçimi - her departmanın en iyi 2 performans göstereni
print("\nHer departmanın en iyi 2 performans göstereni:")
top_performans = çalışanlar.groupby('departman').apply(
    lambda x: x.nlargest(2, 'performans_notu')
).reset_index(drop=True)

print(top_performans[['ad', 'departman', 'performans_notu']])
```

## 📊 Gelişmiş Pivot Tablo İşlemleri

### Çoklu Değerli Pivot Tablolar

```python
# Satış verisi örneği
np.random.seed(42)
satışlar = pd.DataFrame({
    'tarih': pd.date_range('2024-01-01', periods=500, freq='D'),
    'satış_temsilcisi': np.random.choice(['Ali', 'Ayşe', 'Mehmet', 'Fatma'], 500),
    'bölge': np.random.choice(['İstanbul', 'Ankara', 'İzmir'], 500),
    'ürün': np.random.choice(['Laptop', 'Mouse', 'Klavye', 'Monitor'], 500),
    'miktar': np.random.randint(1, 20, 500),
    'fiyat': np.random.randint(50, 2000, 500)
})

satışlar['toplam_satış'] = satışlar['miktar'] * satışlar['fiyat']
satışlar['ay'] = satışlar['tarih'].dt.month
satışlar['çeyrek'] = satışlar['tarih'].dt.quarter

print("Satış verisi:")
print(satışlar.head())
```

### Çok Boyutlu Pivot Tablolar

```python
# Çok katmanlı pivot tablo
print("Temsilci-Bölge-Ürün bazında satış analizi:")
çok_boyut_pivot = satışlar.pivot_table(
    values=['toplam_satış', 'miktar'],
    index=['satış_temsilcisi', 'bölge'],
    columns='ürün',
    aggfunc={'toplam_satış': 'sum', 'miktar': 'sum'},
    fill_value=0,
    margins=True
)

print(çok_boyut_pivot)

# Zaman serisi pivot
print("\nAylık satış trendi (temsilci bazında):")
aylık_pivot = satışlar.pivot_table(
    values='toplam_satış',
    index='satış_temsilcisi',
    columns='ay',
    aggfunc='sum',
    fill_value=0
)

print(aylık_pivot)
```

### Gelişmiş Cross-tabulation

```python
# Detaylı cross-tabulation
print("Bölge-Ürün cross-tabulation:")
cross_tab = pd.crosstab(
    satışlar['bölge'], 
    satışlar['ürün'], 
    values=satışlar['toplam_satış'], 
    aggfunc='sum',
    margins=True,
    normalize='index'  # Satır bazında normalleştirme
)

print(cross_tab.round(2))

# Chi-square test ile
from scipy.stats import chi2_contingency
chi2_tab = pd.crosstab(satışlar['bölge'], satışlar['ürün'])
chi2, p_value, dof, expected = chi2_contingency(chi2_tab)

print(f"\nChi-square test sonucu:")
print(f"Chi-square: {chi2:.2f}")
print(f"P-value: {p_value:.4f}")
print(f"Bölge ve ürün tercihi arasında anlamlı ilişki: {'Var' if p_value < 0.05 else 'Yok'}")
```

## 🔧 Pratik Groupby Teknikleri

### Koşullu Gruplama

```python
# Yaş gruplarına göre gruplama
çalışanlar['yaş_grubu'] = pd.cut(çalışanlar['yaş'], 
                               bins=[0, 30, 40, 50, 100], 
                               labels=['Genç', 'Orta Yaş', 'Deneyimli', 'Kıdemli'])

print("Yaş gruplarına göre maaş analizi:")
yaş_grup_analiz = çalışanlar.groupby('yaş_grubu')['maaş'].describe()
print(yaş_grup_analiz)

# Performans kategorilerine göre gruplama
çalışanlar['performans_kategori'] = pd.cut(çalışanlar['performans_notu'],
                                         bins=[0, 70, 85, 100],
                                         labels=['Gelişim Gerekli', 'İyi', 'Mükemmel'])

print("\nPerformans kategorilerine göre maaş dağılımı:")
perf_maaş = çalışanlar.groupby('performans_kategori')['maaş'].mean()
print(perf_maaş)
```

### Rolling ve Expanding İşlemler

```python
# Zaman serisi için rolling işlemler
aylık_satış = satışlar.groupby('tarih')['toplam_satış'].sum().reset_index()
aylık_satış = aylık_satış.set_index('tarih').sort_index()

# 7 günlük hareketli ortalama
aylık_satış['7_gun_ortalama'] = aylık_satış['toplam_satış'].rolling(window=7).mean()

# 30 günlük hareketli ortalama
aylık_satış['30_gun_ortalama'] = aylık_satış['toplam_satış'].rolling(window=30).mean()

# Expanding (kümülatif) ortalama
aylık_satış['kümülatif_ortalama'] = aylık_satış['toplam_satış'].expanding().mean()

print("Zaman serisi analizi (son 10 gün):")
print(aylık_satış.tail(10).round(2))
```

## ⚠️ Dikkat Edilmesi Gerekenler

> **🔍 Grup Boyutları**: Çok küçük gruplar yanıltıcı istatistikler üretebilir.

> **📊 Aggregation Seçimi**: Amacanıza uygun aggregation fonksiyonu seçin (mean, median, sum vs).

> **⚡ Performans**: Çok büyük verilerle groupby işlemleri zaman alabilir.

## 🚨 Sık Yapılan Hatalar

| Hata | Açıklama | Çözüm |
|------|----------|-------|
| `KeyError` during groupby | Olmayan sütuna göre gruplama | Sütun adlarını kontrol edin |
| Yanlış aggregation fonksiyonu | Kategorik veriye mean uygulamak | Veri tipine uygun fonksiyon seçin |
| MultiIndex karmaşası | Çoklu grup sonrası karışıklık | `reset_index()` kullanın |
| Missing values sorunları | NaN değerler groupby'ı etkiliyor | Önceden temizleyin veya `dropna=False` |
| Transform vs Aggregation | Karıştırılması | Transform: aynı boyut, Agg: özetlenmiş |

### Pratik Groupby Yardımcı Fonksiyonu

```python
def akıllı_groupby_analizi(df, grup_sütunu, hedef_sütun, analiz_tipi='full'):
    """
    Akıllı groupby analizi yapan fonksiyon
    """
    print(f"📊 {grup_sütunu} bazında {hedef_sütun} analizi")
    print("="*50)
    
    # Temel istatistikler
    if analiz_tipi in ['full', 'basic']:
        basic_stats = df.groupby(grup_sütunu)[hedef_sütun].describe()
        print("Temel istatistikler:")
        print(basic_stats.round(2))
        print("\n")
    
    # Dağılım analizi
    if analiz_tipi in ['full', 'distribution']:
        dist_analysis = df.groupby(grup_sütunu)[hedef_sütun].agg([
            'count', 'mean', 'median', 'std', 
            lambda x: x.quantile(0.25),
            lambda x: x.quantile(0.75),
            'skew'
        ]).round(3)
        
        dist_analysis.columns = ['Count', 'Mean', 'Median', 'Std', 'Q25', 'Q75', 'Skewness']
        print("Dağılım analizi:")
        print(dist_analysis)
        print("\n")
    
    # Outlier analizi
    if analiz_tipi in ['full', 'outliers']:
        def outlier_count(series):
            Q1, Q3 = series.quantile([0.25, 0.75])
            IQR = Q3 - Q1
            lower_bound = Q1 - 1.5 * IQR
            upper_bound = Q3 + 1.5 * IQR
            return len(series[(series < lower_bound) | (series > upper_bound)])
        
        outliers = df.groupby(grup_sütunu)[hedef_sütun].apply(outlier_count)
        print("Grup bazında aykırı değer sayıları:")
        print(outliers)
        print("\n")
    
    # Grup karşılaştırması
    if analiz_tipi == 'full':
        group_comparison = df.groupby(grup_sütunu)[hedef_sütun].mean().sort_values(ascending=False)
        print("Grup sıralaması (ortalamaya göre):")
        print(group_comparison)
    
    return None

# Kullanım örneği
# akıllı_groupby_analizi(çalışanlar, 'departman', 'maaş', 'full')
```

## 🎯 Egzersizler

### Egzersiz 1: Temel Groupby İşlemleri
```python
# Yukarıdaki çalışanlar DataFrame'ini kullanarak:
# 1. Her şehirdeki ortalama yaşı hesaplayın
# 2. Departman bazında maksimum ve minimum maaşları bulun
# 3. Hem departman hem şehire göre ortalama performans notunu hesaplayın
# 4. Her departmandaki çalışan sayısını ve toplam maaş giderini bulun

# Çözüm alanı:

```

### Egzersiz 2: İleri Seviye Aggregation
```python
# 1. Her departman için şu metrikleri hesaplayın:
#    - Ortalama maaş
#    - Maaş standart sapması  
#    - En deneyimli çalışanın yaşı
#    - Performans notu 80'in üzerinde olan çalışan oranı
#    - Maaş aralığı (max - min)

# 2. Named aggregation kullanarak temiz bir tablo oluşturun

# Çözüm alanı:

```

### Egzersiz 3: Transform ve Apply Uygulamaları
```python
# 1. Her çalışan için departman içindeki maaş sıralamasını hesaplayın
# 2. Departman ortalamasından ne kadar sapıldığını hesaplayın (z-score)
# 3. Her departmanın en yüksek performanslı 3 çalışanını bulun
# 4. Her şehirdeki en deneyimli ve en genç çalışanları listeleyin

# Çözüm alanı:

```

### Egzersiz 4: Karmaşık Pivot ve Cross-Tab
```python
# Satışlar DataFrame'ini kullanarak:
# 1. Çeyrek-Bölge-Ürün bazında toplam satış pivot tablosu oluşturun
# 2. Satış temsilcilerinin aylık performans trendini gösterin
# 3. Hangi bölge-ürün kombinasyonu en karlı?
# 4. Cross-tabulation ile bölge ve ürün tercihi arasında anlamlı ilişki var mı?

# Çözüm alanı:

```

---# 8. 💼 Pratik Uygulama Projesi

Bu bölümde, şimdiye kadar öğrendiğiniz tüm Pandas tekniklerini gerçek bir veri analizi projesinde uygulayacağız.

## 🎯 Proje: E-ticaret Satış Analizi

### 📋 Proje Açıklaması

Bir e-ticaret şirketinin 2024 yılı satış verilerini analiz edeceğiz. Amacımız:
- Satış performansını değerlendirmek
- Müşteri segmentasyonu yapmak  
- Ürün performansı analizi
- Sezonsal trendleri belirlemek
- İş geliştirme önerileri sunmak

### 📊 Veri Seti Oluşturma

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from datetime import datetime, timedelta
import warnings
warnings.filterwarnings('ignore')

# Veri seti oluşturma
np.random.seed(42)

# Temel parametreler
num_orders = 10000
start_date = datetime(2024, 1, 1)
end_date = datetime(2024, 12, 31)

# Tarih aralığı oluşturma
date_range = pd.date_range(start_date, end_date)

# E-ticaret veri seti oluşturma
print("🔄 E-ticaret veri seti oluşturuluyor...")

eticaret_data = pd.DataFrame({
    'siparis_id': range(1, num_orders + 1),
    'tarih': np.random.choice(date_range, num_orders),
    'musteri_id': np.random.randint(1001, 5000, num_orders),
    'urun_kategori': np.random.choice([
        'Elektronik', 'Giyim', 'Ev & Yaşam', 'Kitap', 'Spor', 
        'Kozmetik', 'Oyuncak', 'Otomotiv'
    ], num_orders, p=[0.2, 0.15, 0.15, 0.1, 0.1, 0.1, 0.1, 0.1]),
    
    'urun_adi': np.random.choice([
        'Laptop', 'Telefon', 'Kulaklık', 'Tişört', 'Pantolon', 
        'Ayakkabı', 'Kitap', 'Oyun', 'Parfüm', 'Saat'
    ], num_orders),
    
    'adet': np.random.choice([1, 2, 3, 4, 5], num_orders, p=[0.5, 0.25, 0.15, 0.07, 0.03]),
    
    'birim_fiyat': np.random.gamma(shape=2, scale=100, size=num_orders),
    
    'musteri_yas': np.random.normal(35, 15, num_orders),
    
    'sehir': np.random.choice([
        'İstanbul', 'Ankara', 'İzmir', 'Bursa', 'Antalya', 
        'Adana', 'Konya', 'Kayseri'
    ], num_orders, p=[0.3, 0.15, 0.12, 0.08, 0.08, 0.07, 0.1, 0.1]),
    
    'odeme_yontem': np.random.choice([
        'Kredi Kartı', 'Banka Kartı', 'Nakit', 'Havale'
    ], num_orders, p=[0.6, 0.25, 0.1, 0.05]),
    
    'kargo_ucreti': np.random.choice([0, 15, 25, 35], num_orders, p=[0.4, 0.3, 0.2, 0.1])
})

# Türetilmiş sütunlar
eticaret_data['toplam_fiyat'] = eticaret_data['adet'] * eticaret_data['birim_fiyat']
eticaret_data['toplam_odeme'] = eticaret_data['toplam_fiyat'] + eticaret_data['kargo_ucreti']

# Yaş grubunu float olan değerleri integer'a çevirme
eticaret_data['musteri_yas'] = eticaret_data['musteri_yas'].astype(int)
eticaret_data['musteri_yas'] = eticaret_data['musteri_yas'].clip(18, 80)  # 18-80 yaş arası

# Tarih sütunundan ek bilgiler
eticaret_data['ay'] = eticaret_data['tarih'].dt.month
eticaret_data['gun'] = eticaret_data['tarih'].dt.day
eticaret_data['hafta'] = eticaret_data['tarih'].dt.isocalendar().week
eticaret_data['haftanin_gunu'] = eticaret_data['tarih'].dt.day_name()
eticaret_data['ceyrek'] = eticaret_data['tarih'].dt.quarter

print("✅ Veri seti başarıyla oluşturuldu!")
print(f"📊 Toplam sipariş sayısı: {len(eticaret_data):,}")
print(f"📅 Tarih aralığı: {eticaret_data['tarih'].min()} - {eticaret_data['tarih'].max()}")
print("\n🔍 Veri setinin ilk 5 satırı:")
print(eticaret_data.head())
```

## 🧹 Adım 1: Veri Temizleme ve Ön İnceleme

```python
print("=" * 60)
print("🧹 ADIM 1: VERİ TEMİZLEME VE ÖN İNCELEME")
print("=" * 60)

# 1.1 Temel bilgileri inceleme
print("📊 Veri seti genel bilgileri:")
print(f"Boyut: {eticaret_data.shape}")
print(f"Sütun sayısı: {len(eticaret_data.columns)}")
print(f"Satır sayısı: {len(eticaret_data)}")

print("\n🔍 Veri tipleri:")
print(eticaret_data.dtypes)

# 1.2 Eksik veri kontrolü
print("\n🕳️ Eksik veri kontrolü:")
eksik_veriler = eticaret_data.isnull().sum()
print(eksik_veriler[eksik_veriler > 0])

if eksik_veriler.sum() == 0:
    print("✅ Hiç eksik veri yok!")
else:
    print(f"⚠️ Toplam eksik veri: {eksik_veriler.sum()}")

# 1.3 Duplikasyon kontrolü
duplikasyon_sayisi = eticaret_data.duplicated().sum()
print(f"\n🔄 Duplikasyon kontrolü: {duplikasyon_sayisi} adet")

if duplikasyon_sayisi > 0:
    print("🧹 Duplikasyonlar temizleniyor...")
    eticaret_data = eticaret_data.drop_duplicates()
    print(f"✅ {duplikasyon_sayisi} duplikasyon temizlendi!")

# 1.4 Sayısal sütunlar için temel istatistikler
print("\n📈 Sayısal sütunlar için temel istatistikler:")
sayisal_sutunlar = ['adet', 'birim_fiyat', 'toplam_fiyat', 'toplam_odeme', 'musteri_yas']
print(eticaret_data[sayisal_sutunlar].describe().round(2))

# 1.5 Kategorik sütunlar için özet
print("\n📊 Kategorik sütunlar dağılımı:")
kategorik_sutunlar = ['urun_kategori', 'sehir', 'odeme_yontem']
for sutun in kategorik_sutunlar:
    print(f"\n{sutun}:")
    print(eticaret_data[sutun].value_counts().head())
```

## 📊 Adım 2: Keşifsel Veri Analizi (EDA)

```python
print("\n" + "=" * 60)
print("📊 ADIM 2: KEŞİFSEL VERİ ANALİZİ")
print("=" * 60)

# 2.1 Satış performansı özeti
print("💰 GENEL SATIŞ PERFORMANSI")
print("-" * 30)

toplam_gelir = eticaret_data['toplam_odeme'].sum()
ortalama_siparis = eticaret_data['toplam_odeme'].mean()
siparis_sayisi = len(eticaret_data)
benzersiz_musteri = eticaret_data['musteri_id'].nunique()

print(f"💵 Toplam Gelir: ₺{toplam_gelir:,.2f}")
print(f"📦 Toplam Sipariş: {siparis_sayisi:,}")
print(f"👥 Benzersiz Müşteri: {benzersiz_musteri:,}")
print(f"💰 Ortalama Sipariş Değeri: ₺{ortalama_siparis:.2f}")
print(f"🔄 Müşteri Başına Ortalama Sipariş: {siparis_sayisi/benzersiz_musteri:.1f}")

# 2.2 En çok satan kategori analizi
print("\n🏆 EN ÇOK SATAN KATEGORİLER")
print("-" * 30)

kategori_performans = eticaret_data.groupby('urun_kategori').agg({
    'toplam_odeme': 'sum',
    'siparis_id': 'count',
    'musteri_id': 'nunique'
}).round(2)

kategori_performans.columns = ['Toplam_Gelir', 'Siparis_Sayisi', 'Musteri_Sayisi']
kategori_performans['Ortalama_Siparis'] = (kategori_performans['Toplam_Gelir'] / 
                                          kategori_performans['Siparis_Sayisi']).round(2)

kategori_performans = kategori_performans.sort_values('Toplam_Gelir', ascending=False)
print(kategori_performans)

# En performanslı kategori
en_iyi_kategori = kategori_performans.index[0]
print(f"\n🥇 En başarılı kategori: {en_iyi_kategori}")
print(f"   💰 Gelir: ₺{kategori_performans.loc[en_iyi_kategori, 'Toplam_Gelir']:,.2f}")

# 2.3 Şehir bazında analiz
print("\n🏙️ ŞEHİR BAZINDA PERFORMANS")
print("-" * 30)

sehir_analiz = eticaret_data.groupby('sehir').agg({
    'toplam_odeme': ['sum', 'mean', 'count'],
    'musteri_id': 'nunique'
}).round(2)

sehir_analiz.columns = ['Toplam_Gelir', 'Ort_Siparis_Degeri', 'Siparis_Sayisi', 'Musteri_Sayisi']
sehir_analiz = sehir_analiz.sort_values('Toplam_Gelir', ascending=False)
print(sehir_analiz.head())

# 2.4 Ödeme yöntemi analizi
print("\n💳 ÖDEME YÖNTEMİ ANALİZİ")
print("-" * 30)

odeme_analiz = eticaret_data.groupby('odeme_yontem').agg({
    'toplam_odeme': ['sum', 'mean', 'count'],
    'musteri_id': 'nunique'
}).round(2)

odeme_analiz.columns = ['Toplam_Gelir', 'Ort_Siparis_Degeri', 'Siparis_Sayisi', 'Musteri_Sayisi']
print(odeme_analiz.sort_values('Toplam_Gelir', ascending=False))
```

## 📈 Adım 3: Zaman Serisi Analizi

```python
print("\n" + "=" * 60)
print("📈 ADIM 3: ZAMAN SERİSİ ANALİZİ")
print("=" * 60)

# 3.1 Aylık satış trendi
print("📅 AYLIK SATIŞ TRENDİ")
print("-" * 25)

aylik_satış = eticaret_data.groupby('ay').agg({
    'toplam_odeme': ['sum', 'count'],
    'musteri_id': 'nunique'
}).round(2)

aylik_satış.columns = ['Toplam_Gelir', 'Siparis_Sayisi', 'Musteri_Sayisi']

# Ay isimlerini ekleme
ay_isimleri = ['Ocak', 'Şubat', 'Mart', 'Nisan', 'Mayıs', 'Haziran',
               'Temmuz', 'Ağustos', 'Eylül', 'Ekim', 'Kasım', 'Aralık']
aylik_satış['Ay_Adi'] = [ay_isimleri[i-1] for i in aylik_satış.index]

print(aylik_satış[['Ay_Adi', 'Toplam_Gelir', 'Siparis_Sayisi']])

# En iyi ve en kötü aylar
en_iyi_ay = aylik_satış.loc[aylik_satış['Toplam_Gelir'].idxmax(), 'Ay_Adi']
en_kotu_ay = aylik_satış.loc[aylik_satış['Toplam_Gelir'].idxmin(), 'Ay_Adi']

print(f"\n🏆 En başarılı ay: {en_iyi_ay}")
print(f"📉 En düşük performans: {en_kotu_ay}")

# 3.2 Çeyrek bazında analiz
print("\n📊 ÇEYREK BAZINDA PERFORMANS")
print("-" * 30)

ceyrek_analiz = eticaret_data.groupby('ceyrek').agg({
    'toplam_odeme': ['sum', 'mean'],
    'siparis_id': 'count',
    'musteri_id': 'nunique'
}).round(2)

ceyrek_analiz.columns = ['Toplam_Gelir', 'Ort_Siparis_Degeri', 'Siparis_Sayisi', 'Musteri_Sayisi']
print(ceyrek_analiz)

# 3.3 Haftanın günlerine göre analiz
print("\n📅 HAFTANIN GÜNLERİNE GÖRE ANALİZ")
print("-" * 35)

# Türkçe gün isimleri mapping
gun_mapping = {
    'Monday': 'Pazartesi',
    'Tuesday': 'Salı', 
    'Wednesday': 'Çarşamba',
    'Thursday': 'Perşembe',
    'Friday': 'Cuma',
    'Saturday': 'Cumartesi',
    'Sunday': 'Pazar'
}

eticaret_data['gun_tr'] = eticaret_data['haftanin_gunu'].map(gun_mapping)

gunluk_analiz = eticaret_data.groupby('gun_tr').agg({
    'toplam_odeme': ['sum', 'mean'],
    'siparis_id': 'count'
}).round(2)

gunluk_analiz.columns = ['Toplam_Gelir', 'Ort_Siparis_Degeri', 'Siparis_Sayisi']

# Haftanın günlerini doğru sırada gösterme
gun_sirasi = ['Pazartesi', 'Salı', 'Çarşamba', 'Perşembe', 'Cuma', 'Cumartesi', 'Pazar']
gunluk_analiz = gunluk_analiz.reindex(gun_sirasi)

print(gunluk_analiz)

en_yoğun_gun = gunluk_analiz['Siparis_Sayisi'].idxmax()
print(f"\n📈 En yoğun gün: {en_yoğun_gun}")
```

## 👥 Adım 4: Müşteri Segmentasyonu

```python
print("\n" + "=" * 60)
print("👥 ADIM 4: MÜŞTERİ SEGMENTASYONU")
print("=" * 60)

# 4.1 Müşteri bazında analiz
print("🔍 MÜŞTERİ ANALİZİ HAZIRLANIYOR...")

musteri_analiz = eticaret_data.groupby('musteri_id').agg({
    'toplam_odeme': ['sum', 'mean', 'count'],
    'tarih': ['min', 'max'],
    'urun_kategori': lambda x: x.nunique()
}).round(2)

# Sütun isimlerini düzenleme
musteri_analiz.columns = [
    'Toplam_Harcama', 'Ort_Siparis_Degeri', 'Siparis_Sayisi',
    'Ilk_Siparis', 'Son_Siparis', 'Farkli_Kategori'
]

# Müşteri değerini hesaplama (Customer Lifetime Value - basit versiyon)
musteri_analiz['CLV'] = (musteri_analiz['Toplam_Harcama'] * 
                        musteri_analiz['Siparis_Sayisi'] / 100).round(2)

# Müşteri yaş segmentasyonu
musteri_yas = eticaret_data.groupby('musteri_id')['musteri_yas'].first()
musteri_analiz['Yas'] = musteri_yas

# Yaş gruplarını oluşturma
musteri_analiz['Yas_Grubu'] = pd.cut(
    musteri_analiz['Yas'], 
    bins=[0, 25, 35, 50, 100], 
    labels=['Z Kuşağı (18-25)', 'Milenyum (26-35)', 'X Kuşağı (36-50)', 'Baby Boomer (50+)']
)

print("\n📊 MÜŞTERI SEGMENTASYONU SONUÇLARI")
print("-" * 35)

# Yaş grubu analizi
yas_grubu_analiz = musteri_analiz.groupby('Yas_Grubu').agg({
    'Toplam_Harcama': ['count', 'mean', 'sum'],
    'Siparis_Sayisi': 'mean',
    'CLV': 'mean'
}).round(2)

print("Yaş Grubu Bazında Analiz:")
print(yas_grubu_analiz)

# En değerli müşteriler (Top 5)
print("\n🏆 EN DEĞERLİ MÜŞTERİLER (Top 5)")
print("-" * 30)
top_musteriler = musteri_analiz.nlargest(5, 'Toplam_Harcama')
print(top_musteriler[['Toplam_Harcama', 'Siparis_Sayisi', 'Ort_Siparis_Degeri', 'Yas_Grubu']])

# RFM Analizi (Basitleştirilmiş)
print("\n📊 RFM ANALİZİ (Recency, Frequency, Monetary)")
print("-" * 45)

# Recency: Son siparişten bu yana geçen gün sayısı
max_tarih = eticaret_data['tarih'].max()
musteri_analiz['Recency'] = (max_tarih - musteri_analiz['Son_Siparis']).dt.days

# Frequency: Sipariş sıklığı (zaten var)
# Monetary: Toplam harcama (zaten var)

# RFM skorlarını hesaplama (1-5 arası)
musteri_analiz['R_Score'] = pd.qcut(musteri_analiz['Recency'], 5, labels=range(5,0,-1))
musteri_analiz['F_Score'] = pd.qcut(musteri_analiz['Siparis_Sayisi'], 5, labels=range(1,6))
musteri_analiz['M_Score'] = pd.qcut(musteri_analiz['Toplam_Harcama'], 5, labels=range(1,6))

# RFM segmentleri
def rfm_segment(row):
    if row['R_Score'] >= 4 and row['F_Score'] >= 4 and row['M_Score'] >= 4:
        return 'Champions'
    elif row['R_Score'] >= 3 and row['F_Score'] >= 3:
        return 'Loyal Customers'
    elif row['R_Score'] >= 3 and row['M_Score'] >= 3:
        return 'Potential Loyalists'
    elif row['R_Score'] <= 2:
        return 'At Risk'
    else:
        return 'Others'

musteri_analiz['RFM_Segment'] = musteri_analiz.apply(rfm_segment, axis=1)

segment_dagılım = musteri_analiz['RFM_Segment'].value_counts()
print("Müşteri Segment Dağılımı:")
print(segment_dagılım)
print(f"\nSegment Yüzdelik Dağılımı:")
print((segment_dagılım / len(musteri_analiz) * 100).round(1))
```

## 🎯 Adım 5: Ürün Performans Analizi

```python
print("\n" + "=" * 60)
print("🎯 ADIM 5: ÜRÜN PERFORMANS ANALİZİ")
print("=" * 60)

# 5.1 Ürün kategori detay analizi
print("📦 ÜRÜN KATEGORİ DETAY ANALİZİ")
print("-" * 30)

urun_performans = eticaret_data.groupby('urun_kategori').agg({
    'toplam_odeme': ['sum', 'mean', 'count'],
    'adet': ['sum', 'mean'],
    'musteri_id': 'nunique',
    'birim_fiyat': 'mean'
}).round(2)

# Sütun isimlerini düzenleme
urun_performans.columns = [
    'Toplam_Gelir', 'Ort_Siparis_Degeri', 'Siparis_Sayisi',
    'Toplam_Adet', 'Ort_Adet', 'Musteri_Sayisi', 'Ort_Birim_Fiyat'
]

# Pazar payı hesaplama
urun_performans['Pazar_Payı_%'] = (urun_performans['Toplam_Gelir'] / 
                                   urun_performans['Toplam_Gelir'].sum() * 100).round(1)

# Karlılık göstergesi (basit)
urun_performans['Karlilik_Skoru'] = (
    urun_performans['Ort_Siparis_Degeri'] * urun_performans['Siparis_Sayisi'] / 
    urun_performans['Siparis_Sayisi'].sum()
).round(2)

urun_performans = urun_performans.sort_values('Toplam_Gelir', ascending=False)
print(urun_performans)

# 5.2 En popüler ürünler
print(f"\n🏆 EN POPÜLER ÜRÜNLER")
print("-" * 20)

urun_popülerlik = eticaret_data.groupby('urun_adi').agg({
    'siparis_id': 'count',
    'adet': 'sum',
    'toplam_odeme': 'sum'
}).round(2)

urun_popülerlik.columns = ['Siparis_Sayisi', 'Toplam_Adet', 'Toplam_Gelir']
urun_popülerlik = urun_popülerlik.sort_values('Siparis_Sayisi', ascending=False)

print("Sipariş sayısına göre top 10:")
print(urun_popülerlik.head(10))

# 5.3 Kategori çapraz analizi
print(f"\n🔄 KATEGORİ ÇAPRAZ ANALİZ")
print("-" * 25)

# Kategorilerin şehirlere göre dağılımı
kategori_sehir = pd.crosstab(
    eticaret_data['urun_kategori'], 
    eticaret_data['sehir'], 
    values=eticaret_data['toplam_odeme'], 
    aggfunc='sum'
).fillna(0)

print("Kategori-Şehir bazında gelir dağılımı:")
print(kategori_sehir.round(0))

# Her şehrin en çok tercih ettiği kategori
print(f"\nHer şehrin en çok tercih ettiği kategoriler:")
for sehir in kategori_sehir.columns:
    en_popüler = kategori_sehir[sehir].idxmax()
    gelir = kategori_sehir.loc[en_popüler, sehir]
    print(f"{sehir}: {en_popüler} (₺{gelir:,.0f})")
```

## 📋 Adım 6: Öneriler ve Sonuçlar

```python
print("\n" + "=" * 60)
print("📋 ADIM 6: ÖNERILER VE SONUÇLAR")
print("=" * 60)

# 6.1 Ana bulgular özeti
print("🔍 ANA BULGULAR")
print("-" * 15)

print(f"💰 Toplam Gelir: ₺{toplam_gelir:,.2f}")
print(f"📦 Toplam Sipariş: {siparis_sayisi:,}")
print(f"👥 Toplam Müşteri: {benzersiz_musteri:,}")
print(f"💵 Ortalama Sipariş Değeri: ₺{ortalama_siparis:.2f}")

# En başarılı performanslar
print(f"\n🏆 EN BAŞARILIFLAR:")
print(f"   📊 Kategori: {en_iyi_kategori}")
print(f"   🏙️ Şehir: {sehir_analiz.index[0]}")
print(f"   📅 Ay: {en_iyi_ay}")
print(f"   📆 Gün: {en_yoğun_gun}")
print(f"   💳 Ödeme: {odeme_analiz.index[0]}")

# Müşteri segmentasyonu özetleri
print(f"\n👥 MÜŞTERİ SEGMENTLERİ:")
for segment in segment_dagılım.index:
    yuzde = (segment_dagılım[segment] / len(musteri_analiz) * 100)
    print(f"   • {segment}: %{yuzde:.1f} ({segment_dagılım[segment]} müşteri)")

# 6.2 İş geliştirme önerileri
print(f"\n📈 İŞ GELİŞTİRME ÖNERİLERİ")
print("-" * 25)

print("1. 🎯 PAZARLAMA STRATEJİLERİ:")
print(f"   • {en_iyi_kategori} kategorisine özel kampanyalar düzenleyin")
print(f"   • {en_yoğun_gun} günleri için özel promosyonlar planlayın")
print(f"   • {sehir_analiz.index[0]} şehrine yoğunlaşın (en yüksek gelir)")

print("\n2. 👥 MÜŞTERİ YÖNETİMİ:")
champions_oran = segment_dagılım.get('Champions', 0) / len(musteri_analiz) * 100
print(f"   • Champions müşterileri (%{champions_oran:.1f}) için VIP programı başlatın")
print("   • 'At Risk' segmentindeki müşteriler için geri kazanım kampanyası yapın")
print("   • Potential Loyalists'ları Champions'a dönüştürmeye odaklanın")

print("\n3. 📦 ÜRÜN YÖNETİMİ:")
en_az_satan_kategori = kategori_performans.index[-1]
print(f"   • {en_az_satan_kategori} kategorisinin performansını iyileştirin")
print("   • Popüler ürünlerin stoklarını artırın")
print("   • Çapraz satış fırsatlarını değerlendirin")

print("\n4. 🚚 OPERASYONEL İYİLEŞTİRMELER:")
print("   • Ücretsiz kargo eşik değerini optimize edin")
print("   • Peak günlerde (özellikle hafta sonları) kapasiteyi artırın")
print("   • Mobil ödeme seçeneklerini geliştirin")

# 6.3 KPI takibi önerileri
print(f"\n📊 TAKİP EDİLMESİ GEREKEN KPI'LAR")
print("-" * 35)

print("• Aylık gelir büyümesi")
print("• Müşteri kazanım maliyeti (CAC)")
print("• Müşteri yaşam değeri (CLV)")
print("• Sepet terk etme oranı")
print("• Müşteri memnuniyet skoru")
print("• Kategori bazında pazar payı değişimi")

print(f"\n✅ ANALİZ TAMAMLANDI!")
print("📊 Detaylı raporlar ve görselleştirmeler için ek analizler yapılabilir.")
```

## 🎯 Proje Değerlendirme Soruları

### Analitik Düşünme Soruları

1. **Veri Kalitesi**: Hangi veri kalitesi sorunlarıyla karşılaştık ve nasıl çözdük?

2. **Trend Analizi**: Aylık satış trendlerinde gözlemlenen pattern'lar ne anlama geliyor?

3. **Müşteri Davranışları**: RFM analizinden çıkan segmentler işletme için ne ifade ediyor?

4. **Ürün Performansı**: Hangi kategoriler beklenenden farklı performans gösterdi?

5. **Coğrafi Dağılım**: Şehirler arası performans farkları neyin göstergesi?

### Teknik Beceri Değerlendirmesi

Bu projede kullandığımız Pandas teknikleri:
- ✅ DataFrame oluşturma ve manipülasyonu
- ✅ Veri temizleme ve preprocessing
- ✅ Groupby ve aggregation işlemleri
- ✅ Pivot tablo analizi
- ✅ Zaman serisi işlemleri
- ✅ Boolean indexleme ve filtreleme
- ✅ Veri tipi dönüşümleri
- ✅ İstatistiksel analiz
- ✅ Korelasyon analizi
- ✅ Segmentasyon teknikleri

### İleri Seviye Geliştirmeler

Bu projeyi şu yönlerle geliştirebilirsiniz:

1. **Görselleştirme**: Matplotlib/Seaborn ile grafikler
2. **Makine Öğrenimi**: Müşteri segmentasyonu için clustering
3. **Tahminleme**: Gelecek satış tahminleri
4. **Dashboard**: Streamlit/Plotly ile interaktif panel
5. **Otomasyon**: Raporlama süreçlerini otomatikleştirme

---

**🎓 Tebrikler!** Bu kapsamlı projede gerçek dünya veri analizi deneyimi yaşadınız. Pandas'ın gücünü keşfederek, veriyi anlamlı bilgiye dönüştürmeyi öğrendiniz.

---# 9. 📝 Pandas Cheat Sheet

Hızlı referans için en çok kullanılan Pandas komutları ve ipuçları.

## 🚀 Temel İmport ve Kurulum

```python
import pandas as pd
import numpy as np

# Pandas ayarları
pd.set_option('display.max_columns', None)
pd.set_option('display.width', None)
pd.set_option('display.max_rows', 100)
```

## 📊 DataFrame Oluşturma

```python
# Sözlükten DataFrame
df = pd.DataFrame({'A': [1, 2], 'B': [3, 4]})

# Liste listesinden DataFrame
df = pd.DataFrame([[1, 2], [3, 4]], columns=['A', 'B'])

# CSV'den okuma
df = pd.read_csv('dosya.csv', encoding='utf-8')

# Excel'den okuma
df = pd.read_excel('dosya.xlsx', sheet_name='Sayfa1')
```

## 🔍 Veri Keşfi

```python
# Temel bilgiler
df.shape                    # (satır, sütun)
df.info()                   # Detaylı bilgi
df.describe()               # İstatistikler
df.head()                   # İlk 5 satır
df.tail()                   # Son 5 satır
df.columns                  # Sütun isimleri
df.dtypes                   # Veri tipleri

# Eksik veri kontrolü
df.isnull().sum()           # Sütun bazında eksik sayı
df.isnull().any()           # Eksik veri var mı?

# Duplikasyon kontrolü
df.duplicated().sum()       # Duplikasyon sayısı
```

## 🎯 Veri Seçme

```python
# Sütun seçme
df['sütun']                 # Tek sütun (Series)
df[['sütun1', 'sütun2']]   # Birden fazla sütun

# Satır seçme
df.iloc[0]                  # İlk satır
df.iloc[0:5]               # İlk 5 satır
df.iloc[-1]                # Son satır

# Label bazlı seçim
df.loc[0, 'sütun']         # Belirli satır-sütun
df.loc[:, 'A':'C']         # Sütun aralığı

# Koşullu seçim
df[df['A'] > 5]            # Koşullu filtreleme
df[(df['A'] > 5) & (df['B'] < 10)]  # Çoklu koşul
df.query('A > 5 and B < 10')        # SQL-benzeri
```

## 🧹 Veri Temizleme

```python
# Eksik veri yönetimi
df.dropna()                 # Eksik satırları sil
df.dropna(axis=1)          # Eksik sütunları sil
df.fillna(0)               # 0 ile doldur
df.fillna(df.mean())       # Ortalama ile doldur
df.fillna(method='ffill')  # Önceki değerle doldur

# Duplikasyon
df.drop_duplicates()       # Duplikasyonları sil

# Veri tipi dönüşümü
df['sütun'].astype(int)    # Integer'a çevir
pd.to_numeric(df['sütun'], errors='coerce')  # Sayıya çevir
pd.to_datetime(df['tarih']) # Tarihe çevir

# String işlemleri
df['sütun'].str.upper()    # Büyük harf
df['sütun'].str.lower()    # Küçük harf
df['sütun'].str.strip()    # Boşluk temizle
df['sütun'].str.replace('eski', 'yeni')  # Değiştir
```

## 📈 Gruplandırma ve Aggregation

```python
# Basit gruplandırma
df.groupby('kategori').mean()           # Ortalama
df.groupby('kategori').sum()            # Toplam
df.groupby('kategori').count()          # Sayım
df.groupby('kategori').size()           # Grup boyutu

# Çoklu grup
df.groupby(['kat1', 'kat2']).mean()

# Özel aggregation
df.groupby('kategori').agg({
    'sütun1': 'mean',
    'sütun2': ['sum', 'count']
})

# Transform
df.groupby('kategori')['değer'].transform('mean')
```

## 📋 Pivot ve Reshape

```python
# Pivot tablo
df.pivot_table(values='değer', 
               index='satır', 
               columns='sütun', 
               aggfunc='sum')

# Cross-tabulation
pd.crosstab(df['A'], df['B'])

# Melt (geniş → uzun format)
df.melt(id_vars=['id'], 
        value_vars=['A', 'B'])

# Stack/Unstack
df.stack()                  # Sütunları satır yap
df.unstack()               # Satırları sütun yap
```

## 📊 İstatistikler

```python
# Temel istatistikler
df.mean()                   # Ortalama
df.median()                 # Medyan
df.std()                    # Standart sapma
df.var()                    # Varyans
df.min()                    # Minimum
df.max()                    # Maksimum
df.quantile(0.25)          # Çeyreklik

# Korelasyon
df.corr()                   # Korelasyon matrisi
df['A'].corr(df['B'])      # İki sütun korelasyonu

# Value counts
df['kategori'].value_counts()           # Frekans
df['kategori'].value_counts(normalize=True)  # Yüzdelik
```

## 🕐 Zaman Serileri

```python
# Tarih oluşturma
pd.date_range('2024-01-01', periods=100, freq='D')

# Tarih parçaları
df['tarih'].dt.year         # Yıl
df['tarih'].dt.month        # Ay
df['tarih'].dt.day          # Gün
df['tarih'].dt.dayofweek    # Haftanın günü
df['tarih'].dt.quarter      # Çeyrek

# Resample
df.resample('M').mean()     # Aylık ortalama
df.resample('D').sum()      # Günlük toplam

# Rolling
df['değer'].rolling(7).mean()     # 7 günlük hareketli ortalama
```

## 🔗 Birleştirme İşlemleri

```python
# Concat
pd.concat([df1, df2])              # Dikey birleştirme
pd.concat([df1, df2], axis=1)      # Yatay birleştirme

# Merge (SQL-benzeri join)
pd.merge(df1, df2, on='anahtar')           # Inner join
pd.merge(df1, df2, on='anahtar', how='left')   # Left join
pd.merge(df1, df2, on='anahtar', how='outer')  # Full outer join

# Join (index bazlı)
df1.join(df2)                      # Index'e göre birleştir
```

## 💾 Kaydetme

```python
# CSV kaydetme
df.to_csv('dosya.csv', index=False, encoding='utf-8')

# Excel kaydetme
df.to_excel('dosya.xlsx', index=False, sheet_name='Veri')

# Çoklu sayfa Excel
with pd.ExcelWriter('dosya.xlsx') as writer:
    df1.to_excel(writer, sheet_name='Sayfa1')
    df2.to_excel(writer, sheet_name='Sayfa2')

# Parquet (büyük veriler için)
df.to_parquet('dosya.parquet')

# JSON
df.to_json('dosya.json', orient='records')
```

## ⚡ Performans İpuçları

```python
# Kategorik veriler için bellek tasarrufu
df['sütun'] = df['sütun'].astype('category')

# Veri tipi optimizasyonu
df.select_dtypes(include=['int64']).astype('int32')

# Chunk ile büyük dosya okuma
for chunk in pd.read_csv('büyük_dosya.csv', chunksize=10000):
    process(chunk)

# Query vs Boolean indexing (büyük veriler için query daha hızlı)
df.query('A > 5')  # Hızlı
df[df['A'] > 5]    # Yavaş (büyük veriler için)
```

---

# 10. 🔗 Kaynaklar ve Ek Materyaller

## 📚 Resmi Dokümantasyon

### Pandas Resmi Kaynakları
- **Pandas Dokümantasyonu**: https://pandas.pydata.org/docs/
- **Pandas Getting Started**: https://pandas.pydata.org/docs/getting_started/
- **Pandas User Guide**: https://pandas.pydata.org/docs/user_guide/
- **Pandas API Reference**: https://pandas.pydata.org/docs/reference/

### NumPy (Pandas'ın temel bağımlılığı)
- **NumPy Dokümantasyonu**: https://numpy.org/doc/stable/
- **NumPy Quickstart**: https://numpy.org/doc/stable/user/quickstart.html

## 📖 Önerilen Kitaplar

### Türkçe Kaynaklar
- "Python ile Veri Analizi" - Wes McKinney
- "Pandas ile Veri Manipülasyonu" - çeşitli yazarlar
- "Python Veri Bilimi Kütüphaneleri" - Jake VanderPlas

### İngilizce Kaynaklar
- "Python for Data Analysis" - Wes McKinney (Pandas'ın yaratıcısı)
- "Pandas 1.x Cookbook" - Matt Harrison & Theodore Petrou
- "Effective Pandas" - Matt Harrison
- "Python Data Science Handbook" - Jake VanderPlas

## 🎓 Online Kurslar ve Eğitimler

### Ücretsiz Kaynaklar
- **Kaggle Learn - Pandas**: https://www.kaggle.com/learn/pandas
- **DataCamp Community**: Pandas temel eğitimleri
- **Real Python - Pandas Tutorials**: https://realpython.com/pandas-python-explore-dataset/
- **YouTube**: "Corey Schafer Pandas Series"

### Ücretli Platformlar
- **DataCamp**: Kapsamlı Pandas eğitimleri
- **Coursera**: "Python for Data Science" kursları
- **edX**: MIT ve Harvard'dan veri bilimi kursları
- **Udemy**: Pandas özel kursları

## 💻 Pratik Yapabileceğiniz Platformlar

### Veri Seti Kaynakları
- **Kaggle Datasets**: https://www.kaggle.com/datasets
- **UCI Machine Learning Repository**: https://archive.ics.uci.edu/ml/
- **Google Dataset Search**: https://datasetsearch.research.google.com/
- **TÜİK (Türkiye İstatistik Kurumu)**: https://www.tuik.gov.tr/
- **Veri.gov.tr**: Türkiye açık veri portalı

### Pratik Projeler
1. **COVID-19 veri analizi** (John Hopkins University dataset)
2. **Borsa verilerini analiz etme** (Yahoo Finance API)
3. **E-ticaret satış verisi analizi** (Kaggle'dan)
4. **Film ve dizi veritabanı analizi** (IMDb dataset)
5. **Sosyal medya trend analizi**

## 🛠️ Geliştirme Ortamları

### IDE ve Editörler
- **Jupyter Notebook**: Veri analizi için ideal
- **Jupyter Lab**: Daha gelişmiş notebook ortamı
- **Google Colab**: Ücretsiz bulut tabanlı notebook
- **VS Code**: Python extension ile
- **PyCharm**: Professional Python IDE
- **Spyder**: Bilimsel Python geliştirme ortamı

### Cloud Platformlar
- **Google Colab**: Ücretsiz GPU/TPU erişimi
- **Kaggle Notebooks**: Yarışma odaklı platform
- **Azure Machine Learning Studio**
- **AWS SageMaker**
- **IBM Watson Studio**

## 🚨 Yaygın Hata Mesajları ve Çözümleri

| Hata Mesajı | Nedeni | Çözümü |
|-------------|--------|--------|
| `ModuleNotFoundError: No module named 'pandas'` | Pandas kurulu değil | `pip install pandas` |
| `UnicodeDecodeError` | Karakter encoding sorunu | `pd.read_csv('dosya.csv', encoding='utf-8')` |
| `KeyError: 'sütun_adı'` | Sütun mevcut değil | `df.columns` ile kontrol edin |
| `ValueError: cannot convert string to float` | String'i sayıya çevirme hatası | `pd.to_numeric(df['sütun'], errors='coerce')` |
| `SettingWithCopyWarning` | DataFrame slice üzerinde değişiklik | `.copy()` kullanın |
| `AttributeError: 'Series' object has no attribute 'reshape'` | Series/DataFrame karışıklığı | Tip kontrolü yapın |
| `ValueError: Length mismatch` | Sütun uzunlukları farklı | Uzunlukları eşitleyin |
| `TypeError: unhashable type: 'list'` | Liste'yi dictionary key olarak kullanma | Tuple kullanın |
| `IndexError: single positional indexer is out-of-bounds` | Index sınırları aşımı | Index aralığını kontrol edin |
| `ParserError` | CSV parsing hatası | `error_bad_lines=False` ekleyin |

## 🔧 Troubleshooting Rehberi

### Yaygın Problemler ve Çözümleri

#### 1. Bellek Sorunları
```python
# Problem: MemoryError
# Çözüm: Chunk'lar halinde okuyun
for chunk in pd.read_csv('büyük_dosya.csv', chunksize=10000):
    process(chunk)

# Veri tiplerini optimize edin
df['kategori'] = df['kategori'].astype('category')
df['sayı'] = df['sayı'].astype('int32')  # int64 yerine
```

#### 2. Performans Sorunları
```python
# Problem: Yavaş işlemler
# Çözüm 1: Vectorized işlemler kullanın
df['yeni'] = df['A'] + df['B']  # İyi
df['yeni'] = df.apply(lambda x: x['A'] + x['B'], axis=1)  # Kötü

# Çözüm 2: Query kullanın (büyük veriler için)
df.query('A > 5')  # Hızlı
df[df['A'] > 5]    # Yavaş
```

#### 3. Index Problemleri
```python
# Problem: Index karmaşası
# Çözüm: Reset index
df = df.reset_index(drop=True)

# MultiIndex sorunları
df = df.droplevel(level=0, axis=1)  # Sütun seviyesi sil
```

#### 4. Tarih Sorunları
```python
# Problem: Tarih parsing hataları
# Çözüm: Manuel parsing
df['tarih'] = pd.to_datetime(df['tarih'], format='%d/%m/%Y', errors='coerce')

# Zaman dilimi sorunları
df['tarih'] = df['tarih'].dt.tz_localize('UTC').dt.tz_convert('Europe/Istanbul')
```

## 📱 Mobil ve Web Uygulamaları

### Dashboard ve Görselleştirme
- **Streamlit**: Hızlı web app geliştirme
- **Dash (Plotly)**: İnteraktif dashboard'lar
- **Panel (HoloViz)**: Esnek veri uygulamaları
- **Voilà**: Jupyter notebook'ları web app'e çevirme

### Görselleştirme Kütüphaneleri
```python
# Matplotlib (temel)
import matplotlib.pyplot as plt
df.plot()

# Seaborn (istatistiksel)
import seaborn as sns
sns.heatmap(df.corr())

# Plotly (interaktif)
import plotly.express as px
px.scatter(df, x='A', y='B')

# Altair (grammar of graphics)
import altair as alt
alt.Chart(df).mark_circle().encode(x='A', y='B')
```

## 🎯 Sonraki Adımlar

### İleri Seviye Konular
1. **Pandas ile Makine Öğrenimi entegrasyonu** (scikit-learn)
2. **Büyük veri işleme** (Dask, Modin)
3. **Veritabanı entegrasyonu** (SQLAlchemy)
4. **API'lerle veri çekme** (requests, pandas-datareader)
5. **Web scraping ile veri toplama** (BeautifulSoup, Scrapy)

### Diğer İlgili Kütüphaneler
- **NumPy**: Sayısal hesaplamalar
- **SciPy**: Bilimsel hesaplamalar
- **scikit-learn**: Makine öğrenimi
- **statsmodels**: İstatistiksel modelleme
- **matplotlib/seaborn**: Görselleştirme
- **requests**: HTTP istekleri
- **SQLAlchemy**: Veritabanı ORM

---

## 💡 Son İpuçları

### En İyi Pratikler
1. **📝 Kodunuzu dokümante edin**: Yorumlar ve docstring'ler yazın
2. **🧪 Küçük örneklerle test edin**: Büyük veriler üzerinde çalışmadan önce
3. **💾 Düzenli olarak kaydedin**: Özellikle uzun analiz süreçlerinde
4. **🔍 Veriyi anlayın**: İstatistikleri ve dağılımları inceleyin
5. **⚡ Performansı izleyin**: `%%time` ile kod parçalarını ölçün

### Hata Ayıklama İpuçları
```python
# Debug için kullanışlı komutlar
print(df.shape)                    # Boyut kontrolü
print(df.dtypes)                   # Tip kontrolü
print(df.isnull().sum())           # Eksik veri kontrolü
print(df.describe())               # İstatistik özeti
df.head()                          # Veriyi görme
```

**🎊 Tebrikler!** Bu eğitim dokümanını tamamladınız. Artık Pandas ile güvenli bir şekilde veri analizi yapabilirsiniz!

---