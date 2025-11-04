# Python OOP Soruları ve Çözümleri

Bu doküman, nesne yönelimli programlama (OOP) kavramlarını kullanarak problem çözme becerisini geliştirmeye yönelik olarak hazırlanmıştır ve üç ana bölümden oluşmaktadır.

## Bölüm 1: Sorular

### Kolay Seviye Sorular

#### 1. Öğrenci Sınıfı
**Problem Tanımı:** Bir öğrencinin adı, öğrenci numarası, notları ve not ortalaması gibi temel bilgilerini yöneten bir sınıf oluşturun. Sınıf, yeni not ekleme, ortalama hesaplama ve bilgileri gösterme metodlarına sahip olmalıdır.

**Girdi Formatı:** Öğrenci bilgileri (isim, öğrenci numarası) ve not listesi.

**Çıktı Formatı:** Öğrenci bilgileri ve ortalama not.

**Kısıtlamalar:** Notlar 0-100 aralığında olmalıdır, negatif veya 100'den büyük notlar kabul edilmemelidir.

**Örnek Senaryolar:**
- Girdi: Ad="Ali", No="12345", Notlar=[85, 90, 78]
- Çıktı: "Öğrenci: Ali (12345), Notlar: [85, 90, 78], Ortalama: 84.33"

#### 2. Hesap Makinesi Sınıfı
**Problem Tanımı:** Temel matematik işlemlerini gerçekleştiren bir hesap makinesi sınıfı oluşturun. Sınıf toplama, çıkarma, çarpma, bölme ve bellek işlemlerini desteklemelidir.

**Girdi Formatı:** İki sayı ve işlem tipi.

**Çıktı Formatı:** İşlemin sonucu.

**Kısıtlamalar:** Sıfıra bölme durumunda hata döndürülmelidir.

**Örnek Senaryolar:**
- Girdi: `HesapMakinesi().topla(10, 5)`
- Çıktı: `15`
- Girdi: `HesapMakinesi().bol(10, 0)`
- Çıktı: `Hata: Sıfıra bölme mümkün değil!`

#### 3. Kitap Sınıfı
**Problem Tanımı:** Bir kitabın başlığı, yazarı, sayfa sayısı ve okunma durumu gibi özelliklerini yöneten bir sınıf oluşturun. Sınıf kitap okuma, sayfa atlama ve kitap bilgilerini gösterme metodlarına sahip olmalıdır.

**Girdi Formatı:** Kitap bilgileri (başlık, yazar, sayfa sayısı).

**Çıktı Formatı:** Kitap bilgileri ve okunma durumu.

**Kısıtlamalar:** Sayfa sayısı negatif olamaz, okunan sayfa sayısı toplam sayfa sayısını geçemez.

**Örnek Senaryolar:**
- Girdi: Başlık="Python", Yazar="Ali", Sayfa=300
- Çıktı: "Python by Ali - 300 sayfa, 0 sayfa okundu"

#### 4. Banka Hesabı Sınıfı
**Problem Tanımı:** Bir banka hesabının hesap numarası, sahibi adı, bakiye ve işlem geçmişi bilgilerini yöneten bir sınıf oluşturun. Sınıf para yatırma, para çekme ve bakiye sorgulama metodlarına sahip olmalıdır.

**Girdi Formatı:** Hesap bilgileri (numara, sahip, başlangıç bakiyesi) ve işlem tutarları.

**Çıktı Formatı:** Güncel bakiye ve işlem geçmişi.

**Kısıtlamalar:** Çekilen tutar mevcut bakiyeden fazla olamaz.

**Örnek Senaryolar:**
- Girdi: Hesap No="12345", Sahip="Ahmet", Başlangıç=1000, Yatır=500, Çek=300
- Çıktı: "Bakiye: 1200 TL, Son işlem: +500 TL"

#### 5. Geometrik Şekil Sınıfı
**Problem Tanımı:** Dikdörtgen ve daire şekillerinin alan ve çevre hesaplamalarını gerçekleştiren bir sınıf hiyerarşisi oluşturun. Temel şekil sınıfından kalıtım alan Dikdörtgen ve Daire sınıfları oluşturun.

**Girdi Formatı:** Şekil boyutları (genişlik, yükseklik veya yarıçap).

**Çıktı Formatı:** Şeklin alanı ve çevresi.

**Kısıtlamalar:** Negatif boyutlar kabul edilmemelidir.

**Örnek Senaryolar:**
- Girdi: Dikdörtgen(5, 3)
- Çıktı: "Alan: 15, Çevre: 16"
- Girdi: Daire(4)
- Çıktı: "Alan: 50.27, Çevre: 25.13"

### Orta Seviye Sorular

#### 6. Çalışan Yönetim Sistemi
**Problem Tanımı:** Farklı türde çalışanları (normal çalışan, yönetici, mühendis) yöneten bir sistem oluşturun. Her çalışan türü için farklı maaş hesaplama ve bilgi gösterme metodları olmalıdır. Yönetici için ekip büyüklüğü, mühendis için proje sayısı özelliği bulunmalıdır.

**Girdi Formatı:** Çalışan türü, kişisel bilgiler ve ilgili metrikler.

**Çıktı Formatı:** Çalışan bilgileri ve hesaplanan maaş.

**Kısıtlamalar:** Maaş hesaplamaları çalışan türüne göre farklı kurallar içermelidir.

**Örnek Senaryolar:**
- Girdi: NormalÇalışan("Ali", 5000, "IT")
- Çıktı: "Ali - IT Departmanı, Maaş: 5000 TL"
- Girdi: Yönetici("Mehmet", 8000, "IT", 5)
- Çıktı: "Mehmet - IT Departmanı, Yönetici, Ekip: 5 kişi, Maaş: 9500 TL"

#### 7. Kütüphane Yönetim Sistemi
**Problem Tanımı:** Kitap, üye ve kütüphane yönetimi için bir sistem oluşturun. Kitaplar ödünç verilebilir, üyeler kitap alabilir ve kütüphane işlemlerini takip edebilir. Her kitap ve üye için durum takibi yapılmalıdır.

**Girdi Formatı:** Kitap bilgileri, üye bilgileri ve ödünç verme/gerialma işlemleri.

**Çıktı Formatı:** Güncel durum bilgileri ve kütüphane istatistikleri.

**Kısıtlamalar:** Aynı anda bir kitap sadece bir üyede olabilir, üye maksimum 3 kitap alabilir.

**Örnek Senaryolar:**
- Girdi: Kitap("Python", "Ali"), Üye("Ahmet"), Ödünç Ver
- Çıktı: "Python kitabı Ahmet'e verildi, Kütüphanede kalan: 2 kitap"

#### 8. Ev Otomasyon Sistemi
**Problem Tanımı:** Akıllı ev cihazlarını (ışık, termostat, güvenlik kamerası) yöneten bir sistem oluşturun. Her cihaz açılıp kapatılabilir, durum bilgisi verebilir ve özel işlevlerini yerine getirebilir. Tüm cihazlar bir ev sistemi tarafından yönetilmelidir.

**Girdi Formatı:** Cihaz türü, konfigürasyon bilgileri ve komutlar.

**Çıktı Formatı:** Cihaz durumu ve gerçekleştirilen işlemler.

**Kısıtlamalar:** Her cihaz türü kendine özgü özellik ve metodlara sahip olmalıdır.

**Örnek Senaryolar:**
- Girdi: Işık("Salon", True), Termostat("Oturma", 22), GüvenlikKamerası("Giriş", True)
- Çıktı: "Salon ışığı açık, Oturma ısısı 22°C, Giriş kamerası aktif"

#### 9. E-ticaret Sepet Sistemi
**Problem Tanımı:** E-ticaret sitesi için ürün, sepet ve sipariş yönetimi oluşturun. Ürünler katalogda bulunabilir, sepete eklenebilir ve sipariş haline getirilebilir. Sepet toplamı, indirim uygulaması ve ödeme durumu takibi olmalıdır.

**Girdi Formatı:** Ürün bilgileri, sepet işlemleri ve sipariş detayları.

**Çıktı Formatı:** Sepet durumu, toplam tutar ve sipariş özeti.

**Kısıtlamalar:** Stok yetersizliğinde uyarı, toplam tutar hesaplaması doğru olmalı.

**Örnek Senaryolar:**
- Girdi: Ürün("Laptop", 5000, 10), Sepete Ekle(2), İndirim Uygula(%10)
- Çıktı: "Sepet Toplamı: 9000 TL, İndirim: 900 TL, Ödenecek: 8100 TL"

#### 10. Veri Analiz Aracı
**Problem Tanımı:** CSV dosyalarını okuyup analiz eden bir sınıf oluşturun. Dosya yükleme, veri temizleme, istatistiksel hesaplamalar ve rapor oluşturma metodları olmalıdır. Eksik değerler, aykırı değerler ve temel istatistiklerle çalışabilmelidir.

**Girdi Formatı:** CSV dosyası yolu ve analiz parametreleri.

**Çıktı Formatı:** Analiz sonuçları ve istatistiksel rapor.

**Kısıtlamalar:** Dosya bulunamazsa hata, sayısal olmayan sütunlar için istatistik hesaplanmamalı.

**Örnek Senaryolar:**
- Girdi: dosya="veri.csv", Analiz Türü="istatistik"
- Çıktı: "Ortalama: 75.5, Medyan: 80, Standart Sapma: 12.3"

### Zor Seviye Sorular

#### 11. Oyun Motoru Sistemi
**Problem Tanımı:** 2D oyunlar için temel bir oyun motoru oluşturun. Oyuncu, düşman, proje, engel gibi game object'leri yönetebilmeli. Fizik motoru, çarpışma tespiti, skor sistemi ve oyun durumu yönetimi olmalıdır. Oyun döngüsü, event handling ve graphics rendering desteklemelidir.

**Girdi Formatı:** Oyun konfigürasyonu, oyuncu komutları ve level tasarımı.

**Çıktı Formatı:** Oyun durumu, skor ve görsel çıktı simülasyonu.

**Kısıtlamalar:** Performans optimizasyonu, memory yönetimi ve extensible tasarım.

**Örnek Senaryolar:**
- Girdi: OyunBaşlat(level1), OyuncuHareket(SAĞ), ProjeAteşEt
- Çıktı: "Skor: 150, Sağlık: 80%, Düşmanlar: 3/5"

#### 12. Dağıtık Hesaplama Sistemi
**Problem Tanımı:** Büyük veri setleri üzerinde paralel hesaplama yapabilen bir sistem oluşturun. Task queue, worker pool, result aggregation ve fault tolerance özelliklerine sahip olmalı. Sistem birden fazla worker ile çalışabilmeli ve task'ları dağıtmalıdır.

**Girdi Formatı:** Büyük veri seti, hesaplama fonksiyonu ve worker sayısı.

**Çıktı Formatı:** Paralel hesaplama sonuçları ve performans metrikleri.

**Kısıtlamalar:** Worker crash durumunda recovery, load balancing ve result consistency.

**Örnek Senaryolar:**
- Girdi: Veri=[1..100000], Fonksiyon=karakök, Worker=4
- Çıktı: "Sonuç: [1.0, 1.41, ...], Süre: 2.3 saniye, Hızlandırma: 3.2x"

#### 13. Mikro Servis Mimarisi
**Problem Tanımı:** RESTful API'ler sunan mikro servis sistemi oluşturun. Servis discovery, load balancing, circuit breaker, rate limiting ve distributed tracing özelliklerine sahip olmalı. Her servis bağımsız deploy edilebilir ve farklı teknolojiler kullanabilir.

**Girdi Formatı:** Servis tanımları, API endpoint'leri ve konfigürasyon.

**Çıktı Formatı:** Çalışan servisler, health check sonuçları ve request/response.

**Kısıtlamalar:** High availability, horizontal scaling ve data consistency.

**Örnek Senaryolar:**
- Girdi: UserService, OrderService, PaymentService konfigürasyonu
- Çıktı: "Tüm servisler sağlıklı, Request latency: 45ms, Error rate: 0.1%"

#### 14. Machine Learning Pipeline
**Problem Tanımı:** End-to-end makine öğrenmesi pipeline'ı oluşturun. Data preprocessing, feature engineering, model training, hyperparameter tuning, cross validation, model evaluation ve production deployment özelliklerine sahip olmalı. Farklı algoritma desteği ve autoML yetenekleri olmalıdır.

**Girdi Formatı:** Ham veri seti, model konfigürasyonu ve deployment ayarları.

**Çıktı Formatı:** Eğitilmiş model, performans metrikleri ve prediction sonuçları.

**Kısıtlamalar:** Model overfitting önleme, reproducibility ve model interpretability.

**Örnek Senaryolar:**
- Girdi: Dataset=iris.csv, Algorithm=RandomForest, CV=5
- Çıktı: "Model accuracy: 95%, Features: sepal_length, petal_width, Production ready: true"

#### 15. Blockchain İmplementasyonu
**Problem Tanımı:** Temel blockchain yapısını oluşturun. Block sınıfı, transaction işleme, proof of work consensus, chain validation ve mining özelliklerine sahip olmalı. Distributed ledger mantığı, Merkle tree yapısı ve immutable record keeping uygulanmalıdır.

**Girdi Formatı:** Transaction listesi, mining difficulty ve consensus rules.

**Çıktı Formatı:** Valid blockchain, block hash'leri ve transaction confirmation status.

**Kısıtlamalar:** Double spending prevention, chain integrity ve consensus mechanism.

**Örnek Senaryolar:**
- Girdi: Transactions=["A->B:10", "C->D:5"], Difficulty=4
- Çıktı: "Chain length: 1, Block hash: 0000f123..., Valid: true"

---

## Bölüm 2: Çözümler

### Kolay Seviye Çözümleri

#### 1. Öğrenci Sınıfı
**Çözüm Mantığı:**
1. `Ogrenci` sınıfı oluştur ve `__init__` metodunda temel bilgileri ayarla.
2. `not_ekle` metodunda notları kontrol et (0-100 arası) ve listeye ekle.
3. `ortalama_hesapla` metodunda notların aritmetik ortalamasını hesapla.
4. `bilgileri_goster` metodunda tüm bilgileri formatla ve göster.
5. Encapsulation prensibini uygula - notları private yap.

**Optimal Çözüm Kodu:**
```python
class Ogrenci:
    def __init__(self, isim, ogrenci_no):
        self.isim = isim
        self.ogrenci_no = ogrenci_no
        self.__notlar = []  # Private attribute
    
    def not_ekle(self, not_degeri):
        """Yeni not ekle (0-100 arası kontrol)"""
        if 0 <= not_degeri <= 100:
            self.__notlar.append(not_degeri)
            print(f"{not_degeri} notu eklendi.")
        else:
            print("Hata: Not 0-100 arasında olmalı!")
    
    def ortalama_hesapla(self):
        """Ortalama hesapla"""
        if not self.__notlar:
            return 0
        return sum(self.__notlar) / len(self.__notlar)
    
    def bilgileri_goster(self):
        """Tüm bilgileri göster"""
        ortalama = self.ortalama_hesapla()
        print(f"Öğrenci: {self.isim} ({self.ogrenci_no})")
        print(f"Notlar: {self.__notlar}")
        print(f"Ortalama: {ortalama:.2f}")
    
    def get_notlar(self):  # Getter metodu
        """Notları okuma (read-only)"""
        return self.__notlar.copy()

# Test
ogr1 = Ogrenci("Ali Veli", "12345")
ogr1.not_ekle(85)
ogr1.not_ekle(90)
ogr1.not_ekle(78)
ogr1.bilgileri_goster()
# Çıktı: Öğrenci: Ali Veli (12345), Notlar: [85, 90, 78], Ortalama: 84.33
```

#### 2. Hesap Makinesi Sınıfı
**Çözüm Mantığı:**
1. `HesapMakinesi` sınıfı oluştur ve başlangıçta bellek değerini 0 yap.
2. Her işlem metodunda (topla, cikar, carp, bol) parametreleri al ve sonucu hesapla.
3. Sıfıra bölme kontrolü yap.
4. Bellek işlemleri için memory metodları ekle.
5. Tüm metodları static olarak işaretle (instance gerektirmez).

**Optimal Çözüm Kodu:**
```python
class HesapMakinesi:
    def __init__(self):
        self.__bellek = 0  # Private memory
    
    @staticmethod
    def topla(a, b):
        """İki sayıyı topla"""
        return a + b
    
    @staticmethod
    def cikar(a, b):
        """İki sayıyı çıkar"""
        return a - b
    
    @staticmethod
    def carp(a, b):
        """İki sayıyı çarp"""
        return a * b
    
    @staticmethod
    def bol(a, b):
        """İki sayıyı böl (sıfıra bölme kontrolü)"""
        if b == 0:
            raise ValueError("Hata: Sıfıra bölme mümkün değil!")
        return a / b
    
    def bellek_kaydet(self, deger):
        """Değeri belleğe kaydet"""
        self.__bellek = deger
    
    def bellek_cagir(self):
        """Bellekten değer çağır"""
        return self.__bellek
    
    def bellek_temizle(self):
        """Belleği temizle"""
        self.__bellek = 0

# Test
calc = HesapMakinesi()
print(calc.topla(10, 5))  # 15
print(calc.bol(10, 2))    # 5.0

try:
    print(calc.bol(10, 0))
except ValueError as e:
    print(e)  # Hata: Sıfıra bölme mümkün değil!
```

#### 3. Kitap Sınıfı
**Çözüm Mantığı:**
1. `Kitap` sınıfı oluştur ve temel özellikleri ayarla.
2. `sayfa_oku` metodunda okunan sayfa sayısını güncelle.
3. `sayfa_atla` metodunda belirli sayıda sayfa atla.
4. `tamamlandi_mi` metodunda okunma durumunu kontrol et.
5. `__str__` metodunu override ederek güzel string representation sağla.

**Optimal Çözüm Kodu:**
```python
class Kitap:
    def __init__(self, baslik, yazar, sayfa_sayisi):
        self.baslik = baslik
        self.yazar = yazar
        self.sayfa_sayisi = sayfa_sayisi
        self.__okunan_sayfa = 0  # Private attribute
    
    def sayfa_oku(self, sayfa_sayisi):
        """Belirli sayıda sayfa oku"""
        if sayfa_sayisi <= 0:
            print("Hata: Sayfa sayısı pozitif olmalı!")
            return
        
        yeni_okunan = self.__okunan_sayfa + sayfa_sayisi
        
        if yeni_okunan > self.sayfa_sayisi:
            self.__okunan_sayfa = self.sayfa_sayisi
            print("Kitap tamamlandı!")
        else:
            self.__okunan_sayfa = yeni_okunan
        
        print(f"{sayfa_sayisi} sayfa okundu. Toplam: {self.__okunan_sayfa}/{self.sayfa_sayisi}")
    
    def sayfa_atla(self, sayfa_sayisi):
        """Belirli sayıda sayfa atla"""
        if sayfa_sayisi <= 0:
            print("Hata: Sayfa sayısı pozitif olmalı!")
            return
        
        yeni_okunan = self.__okunan_sayfa + sayfa_sayisi
        
        if yeni_okunan > self.sayfa_sayisi:
            self.__okunan_sayfa = self.sayfa_sayisi
        else:
            self.__okunan_sayfa = yeni_okunan
    
    def tamamlandi_mi(self):
        """Kitabın tamamlanıp tamamlanmadığını kontrol et"""
        return self.__okunan_sayfa >= self.sayfa_sayisi
    
    def kalan_sayfa(self):
        """Kalan sayfa sayısını hesapla"""
        return self.sayfa_sayisi - self.__okunan_sayfa
    
    def __str__(self):
        durum = "Tamamlandı" if self.tamamlandi_mi() else f"{self.kalan_sayfa()} sayfa kaldı"
        return f"'{self.baslik}' by {self.yazar} - {self.sayfa_sayisi} sayfa ({durum})"

# Test
kitap1 = Kitap("Python Programlama", "Ali Veli", 300)
print(kitap1)  # 'Python Programlama' by Ali Veli - 300 sayfa (300 sayfa kaldı)

kitap1.sayfa_oku(50)
kitap1.sayfa_oku(100)
print(kitap1)  # 'Python Programlama' by Ali Veli - 300 sayfa (150 sayfa kaldı)
```

#### 4. Banka Hesabı Sınıfı
**Çözüm Mantığı:**
1. `BankaHesabi` sınıfı oluştur ve private bakiye özelliği ekle.
2. `para_yatir` metodunda pozitif tutar kontrolü yap.
3. `para_cek` metodunda yetersiz bakiye kontrolü yap.
4. `islem_gecmisi` listesi ile tüm işlemleri kaydet.
5. `bakiye_sorgula` metodu ile güvenli bakiye erişimi sağla.

**Optimal Çözüm Kodu:**
```python
class BankaHesabi:
    def __init__(self, hesap_no, sahip, baslangic_bakiye=0):
        self.hesap_no = hesap_no
        self.sahip = sahip
        self.__bakiye = baslangic_bakiye  # Private attribute
        self.__islem_gecmisi = []  # Private transaction history
    
    def para_yatir(self, tutar):
        """Para yatır"""
        if tutar <= 0:
            print("Hata: Tutar pozitif olmalı!")
            return False
        
        self.__bakiye += tutar
        self.__islem_gecmisi.append(f"+{tutar} TL yatırıldı")
        print(f"{tutar} TL yatırıldı. Yeni bakiye: {self.__bakiye} TL")
        return True
    
    def para_cek(self, tutar):
        """Para çek"""
        if tutar <= 0:
            print("Hata: Tutar pozitif olmalı!")
            return False
        
        if tutar > self.__bakiye:
            print("Hata: Yetersiz bakiye!")
            return False
        
        self.__bakiye -= tutar
        self.__islem_gecmisi.append(f"-{tutar} TL çekildi")
        print(f"{tutar} TL çekildi. Yeni bakiye: {self.__bakiye} TL")
        return True
    
    def bakiye_sorgula(self):
        """Güvenli bakiye sorgulama"""
        return self.__bakiye
    
    def islem_gecmisi_goster(self):
        """İşlem geçmişini göster"""
        print(f"Hesap No: {self.hesap_no} - {self.sahip}")
        print("İşlem Geçmişi:")
        for islem in self.__islem_gecmisi:
            print(f"  {islem}")
        print(f"Güncel Bakiye: {self.__bakiye} TL")

# Test
hesap1 = BankaHesabi("12345", "Ahmet Yılmaz", 1000)
hesap1.para_yatir(500)
hesap1.para_cek(300)
hesap1.para_cek(2000)  # Yetersiz bakiye hatası
hesap1.islem_gecmisi_goster()
# Çıktı: Bakiye: 1200 TL, Son işlem: +500 TL
```

#### 5. Geometrik Şekil Sınıfı
**Çözüm Mantığı:**
1. Temel `Sekil` abstract sınıfı oluştur (ABC kullanarak).
2. `Dikdortgen` ve `Daire` sınıflarını `Sekil`'den kalıtım alarak oluştur.
3. Her alt sınıf kendi `alan_hesapla` ve `cevre_hesapla` metodlarını implement etsin.
4. Encapsulation uygulayarak negatif boyutları engelle.
5. Polymorphism ile farklı şekilleri aynı şekilde kullan.

**Optimal Çözüm Kodu:**
```python
import math
from abc import ABC, abstractmethod

class Sekil(ABC):
    """Abstract temel şekil sınıfı"""
    
    @abstractmethod
    def alan_hesapla(self):
        pass
    
    @abstractmethod
    def cevre_hesapla(self):
        pass

class Dikdortgen(Sekil):
    """Dikdörtgen sınıfı"""
    
    def __init__(self, genislik, yukseklik):
        if genislik <= 0 or yukseklik <= 0:
            raise ValueError("Boyutlar pozitif olmalı!")
        self.genislik = genislik
        self.yukseklik = yukseklik
    
    def alan_hesapla(self):
        return self.genislik * self.yukseklik
    
    def cevre_hesapla(self):
        return 2 * (self.genislik + self.yukseklik)
    
    def __str__(self):
        return f"Dikdörtgen({self.genislik}x{self.yukseklik})"

class Daire(Sekil):
    """Daire sınıfı"""
    
    def __init__(self, yaricap):
        if yaricap <= 0:
            raise ValueError("Yarıçap pozitif olmalı!")
        self.yaricap = yaricap
    
    def alan_hesapla(self):
        return math.pi * (self.yaricap ** 2)
    
    def cevre_hesapla(self):
        return 2 * math.pi * self.yaricap
    
    def __str__(self):
        return f"Daire(r={self.yaricap})"

# Test ve polymorphism
sekiller = [
    Dikdortgen(5, 3),
    Daire(4),
    Dikdortgen(2, 8)
]

print("Şekil Analizi:")
for sekil in sekiller:
    alan = sekil.alan_hesapla()
    cevre = sekil.cevre_hesapla()
    print(f"{sekil}: Alan={alan:.2f}, Çevre={cevre:.2f}")

# Çıktı: 
# Dikdörtgen(5x3): Alan=15.00, Çevre=16.00
# Daire(r=4): Alan=50.27, Çevre=25.13
# Dikdörtgen(2x8): Alan=16.00, Çevre=20.00
```

### Orta Seviye Çözümleri

#### 6. Çalışan Yönetim Sistemi
**Çözüm Mantığı:**
1. Temel `Calisan` abstract sınıfı oluştur.
2. `NormalCalisan`, `Yonetic`, `Muhendis` sınıflarını kalıtım ile oluştur.
3. Her sınıf kendine özgü özellik ve maaş hesaplama metoduna sahip olsun.
4. `maas_hesapla` metodu her sınıfta farklı implementasyona sahip olsun.
5. Polymorphism ile farklı çalışan türlerini tek listede yönet.

**Optimal Çözüm Kodu:**
```python
from abc import ABC, abstractmethod
from datetime import datetime

class Calisan(ABC):
    """Temel çalışan abstract sınıfı"""
    
    def __init__(self, isim, maas, departman):
        self.isim = isim
        self.maas = maas
        self.departman = departman
        self.giris_tarihi = datetime.now()
    
    @abstractmethod
    def maas_hesapla(self):
        """Maaş hesaplama - her çalışan türü için farklı"""
        pass
    
    def bilgileri_goster(self):
        """Temel bilgileri göster"""
        hesaplanan_maas = self.maas_hesapla()
        print(f"İsim: {self.isim}")
        print(f"Departman: {self.departman}")
        print(f"Temel Maaş: {self.maas} TL")
        print(f"Hesaplanan Maaş: {hesaplanan_maas} TL")
        print(f"Çalışma Süresi: {(datetime.now() - self.giris_tarihi).days} gün")
    
    def __str__(self):
        return f"{self.isim} - {self.departman}"

class NormalCalisan(Calisan):
    """Normal çalışan sınıfı"""
    
    def __init__(self, isim, maas, departman):
        super().__init__(isim, maas, departman)
        self.calisma_saati = 40  # haftalık
    
    def maas_hesapla(self):
        """Temel maaş + çalışma saati bonusu"""
        bonus = (self.calisma_saati - 40) * 50  # 40 saati aşan her saat için 50 TL
        return self.maas + max(0, bonus)
    
    def calisma_saati_guncelle(self, yeni_saat):
        """Çalışma saatini güncelle"""
        self.calisma_saati = yeni_saat

class Yonetic(Calisan):
    """Yönetici sınıfı"""
    
    def __init__(self, isim, maas, departman, ekip_buyuklugu):
        super().__init__(isim, maas, departman)
        self.ekip_buyuklugu = ekip_buyuklugu
        self.yonetim_seviyesi = self._belirle_yonetim_seviyesi()
    
    def _belirle_yonetim_seviyesi(self):
        """Ekip büyüklüğüne göre seviye belirle"""
        if self.ekip_buyuklugu >= 10:
            return "Üst Düzey Yönetici"
        elif self.ekip_buyuklugu >= 5:
            return "Orta Düzey Yönetici"
        else:
            return "Alt Düzey Yönetici"
    
    def maas_hesapla(self):
        """Temel maaş + yönetici bonusu"""
        if self.ekip_buyuklugu >= 10:
            bonus_orani = 0.30
        elif self.ekip_buyuklugu >= 5:
            bonus_orani = 0.20
        else:
            bonus_orani = 0.10
        
        return self.maas + (self.maas * bonus_orani)
    
    def ekip_buyuklugu_guncelle(self, yeni_buyukluk):
        """Ekip büyüklüğünü güncelle"""
        self.ekip_buyuklugu = yeni_buyukluk
        self.yonetim_seviyesi = self._belirle_yonetim_seviyesi()

class Muhendis(Calisan):
    """Mühendis sınıfı"""
    
    def __init__(self, isim, maas, departman, uzmanlik_alani, proje_sayisi=0):
        super().__init__(isim, maas, departman)
        self.uzmanlik_alani = uzmanlik_alani
        self.proje_sayisi = proje_sayisi
        self.sertifikalar = []
    
    def maas_hesapla(self):
        """Temel maaş + proje ve sertifika bonusu"""
        proje_bonusu = self.proje_sayisi * 1000
        sertifika_bonusu = len(self.sertifikalar) * 500
        return self.maas + proje_bonusu + sertifika_bonusu
    
    def proje_tamamla(self, proje_adi):
        """Proje tamamla"""
        self.proje_sayisi += 1
        print(f"{proje_adi} projesi tamamlandı. Toplam proje: {self.proje_sayisi}")
    
    def sertifika_ekle(self, sertifika_adi):
        """Sertifika ekle"""
        if sertifika_adi not in self.sertifikalar:
            self.sertifikalar.append(sertifika_adi)
            print(f"{sertifika_adi} sertifikası eklendi.")

# Test ve polymorphism
calisanlar = [
    NormalCalisan("Ali Veli", 5000, "IT"),
    Yonetic("Mehmet Kaya", 8000, "IT", 7),
    Muhendis("Ayşe Demir", 7000, "Yazılım", "Python", 3)
]

print("=== Çalışan Yönetim Sistemi Testi ===")
for calisan in calisanlar:
    print(f"\n{type(calisan).__name__}:")
    calisan.bilgileri_goster()

# Özel işlemler
muhendis = calisanlar[2]
muhendis.sertifika_ekle("AWS Solutions Architect")
muhendis.proje_tamamla("E-ticaret Sistemi")

print(f"\nGüncellenmiş maaş: {muhendis.maas_hesapla()} TL")
# Çıktı: Ali - IT Departmanı, Maaş: 5000 TL
#        Mehmet - IT Departmanı, Yönetici, Ekip: 7 kişi, Maaş: 9600 TL
```

#### 7. Kütüphane Yönetim Sistemi
**Çözüm Mantığı:**
1. `Kitap`, `Uye` ve `Kutuphane` sınıflarını oluştur.
2. Kitap için durum takibi (mevcut, ödünç verilmiş) yap.
3. Üye için alınan kitaplar listesi tut.
4. Kütüphane sınıfı tüm işlemleri koordine etsin.
5. Validation kuralları uygula (stok, üye limiti).

**Optimal Çözüm Kodu:**
```python
from datetime import datetime, timedelta
from enum import Enum

class KitapDurumu(Enum):
    MEVCUT = "Mevcut"
    ODUNC_VERILMIS = "Ödünç Verilmiş"

class Kitap:
    """Kitap sınıfı"""
    
    def __init__(self, baslik, yazar, isbn, sayfa_sayisi=0):
        self.baslik = baslik
        self.yazar = yazar
        self.isbn = isbn
        self.sayfa_sayisi = sayfa_sayisi
        self.durum = KitapDurumu.MEVCUT
        self.odunc_alan_uye = None
        self.odunc_tarihi = None
    
    def odunc_verilebilir_mi(self):
        """Kitabın ödünç verilip verilemeyeceğini kontrol et"""
        return self.durum == KitapDurumu.MEVCUT
    
    def odunc_ver(self, uye):
        """Kitabı üyeye ödünç ver"""
        if not self.odunc_verilebilir_mi():
            return False, "Kitap şu anda mevcut değil!"
        
        self.durum = KitapDurumu.ODUNC_VERILMIS
        self.odunc_alan_uye = uye
        self.odunc_tarihi = datetime.now()
        return True, "Kitap başarıyla ödünç verildi!"
    
    def iade_et(self):
        """Kitabı iade et"""
        if self.durum == KitapDurumu.ODUNC_VERILMIS:
            self.durum = KitapDurumu.MEVCUT
            self.odunc_alan_uye = None
            self.odunc_tarihi = None
            return True
        return False
    
    def __str__(self):
        durum_text = f"{self.durum.value}"
        if self.odunc_alan_uye:
            durum_text += f" (Üye: {self.odunc_alan_uye.isim})"
        return f"'{self.baslik}' by {self.yazar} - {durum_text}"

class Uye:
    """Üye sınıfı"""
    
    def __init__(self, isim, uye_no, maksimum_kitap=3):
        self.isim = isim
        self.uye_no = uye_no
        self.maksimum_kitap = maksimum_kitap
        self.alınan_kitaplar = []
        self.odunc_gecmisi = []
    
    def kitap_alabilir_mi(self):
        """Üyenin yeni kitap alıp alamayacağını kontrol et"""
        return len(self.alınan_kitaplar) < self.maksimum_kitap
    
    def kitap_al(self, kitap):
        """Kitap alma işlemi"""
        if not self.kitap_alabilir_mi():
            return False, "Maksimum kitap sayısına ulaşıldı!"
        
        if not kitap.odunc_verilebilir_mi():
            return False, "Kitap mevcut değil!"
        
        basarili, mesaj = kitap.odunc_ver(self)
        if basarili:
            self.alınan_kitaplar.append(kitap)
            self.odunc_gecmisi.append({
                'kitap': kitap,
                'alma_tarihi': datetime.now(),
                'iade_tarihi': None
            })
        return basarili, mesaj
    
    def kitap_iade_et(self, kitap):
        """Kitap iade etme işlemi"""
        if kitap not in self.alınan_kitaplar:
            return False, "Bu kitap üzerinizde kayıtlı değil!"
        
        if kitap.iade_et():
            self.alınan_kitaplar.remove(kitap)
            # Geçmişteki kaydı güncelle
            for kayit in self.odunc_gecmisi:
                if kayit['kitap'] == kitap and kayit['iade_tarihi'] is None:
                    kayit['iade_tarihi'] = datetime.now()
                    break
            return True, "Kitap başarıyla iade edildi!"
        return False, "İade işlemi başarısız!"

class Kutuphane:
    """Kütüphane yönetim sınıfı"""
    
    def __init__(self, isim):
        self.isim = isim
        self.kitaplar = []
        self.uyeler = []
        self.istatistikler = {
            'toplam_odunc_verilen': 0,
            'aktif_odunc': 0,
            'en_populer_kitap': None
        }
    
    def kitap_ekle(self, kitap):
        """Kütüphaneye kitap ekle"""
        self.kitaplar.append(kitap)
        print(f"'{kitap.baslik}' kütüphaneye eklendi.")
    
    def uye_ekle(self, uye):
        """Kütüphaneye üye ekle"""
        self.uyeler.append(uye)
        print(f"{uye.isim} kütüphaneye üye oldu.")
    
    def kitap_ara(self, arama_metni):
        """Kitap ara"""
        bulunan = []
        for kitap in self.kitaplar:
            if (arama_metni.lower() in kitap.baslik.lower() or 
                arama_metni.lower() in kitap.yazar.lower()):
                bulunan.append(kitap)
        return bulunan
    
    def odunc_verme_islemi(self, kitap_baslik, uye_no):
        """Kitap ödünç verme işlemi"""
        # Kitabı bul
        kitap = None
        for k in self.kitaplar:
            if k.baslik == kitap_baslik:
                kitap = k
                break
        
        # Üyeyi bul
        uye = None
        for u in self.uyeler:
            if u.uye_no == uye_no:
                uye = u
                break
        
        if not kitap or not uye:
            return False, "Kitap veya üye bulunamadı!"
        
        basarili, mesaj = uye.kitap_al(kitap)
        if basarili:
            self.istatistikler['toplam_odunc_verilen'] += 1
            self.istatistikler['aktif_odunc'] += 1
        
        return basarili, mesaj
    
    def iade_islemi(self, kitap_baslik, uye_no):
        """Kitap iade işlemi"""
        # Üyeyi bul
        uye = None
        for u in self.uyeler:
            if u.uye_no == uye_no:
                uye = u
                break
        
        if not uye:
            return False, "Üye bulunamadı!"
        
        # Üyenin kitaplarını ara
        kitap = None
        for k in uye.alınan_kitaplar:
            if k.baslik == kitap_baslik:
                kitap = k
                break
        
        if not kitap:
            return False, "Üzerinizde bu kitap kayıtlı değil!"
        
        basarili, mesaj = uye.kitap_iade_et(kitap)
        if basarili:
            self.istatistikler['aktif_odunc'] -= 1
        
        return basarili, mesaj
    
    def istatistikleri_goster(self):
        """Kütüphane istatistiklerini göster"""
        print(f"\n=== {self.isim} İstatistikleri ===")
        print(f"Toplam Kitap: {len(self.kitaplar)}")
        print(f"Toplam Üye: {len(self.uyeler)}")
        print(f"Toplam Ödünç Verilen: {self.istatistikler['toplam_odunc_verilen']}")
        print(f"Aktif Ödünç: {self.istatistikler['aktif_odunc']}")
        
        mevcut_kitap = len([k for k in self.kitaplar if k.durum == KitapDurumu.MEVCUT])
        print(f"Mevcut Kitap: {mevcut_kitap}")
        print("=" * 30)

# Test
kutuphane = Kutuphane("Atatürk Halk Kütüphanesi")

# Kitaplar ekle
kitap1 = Kitap("Python Programlama", "Ahmet Yılmaz", "978-975-1234-56-7", 300)
kitap2 = Kitap("Veri Bilimi", "Zeynep Kaya", "978-975-1234-57-4", 250)
kitap3 = Kitap("Makine Öğrenmesi", "Mehmet Demir", "978-975-1234-58-1", 400)

kutuphane.kitap_ekle(kitap1)
kutuphane.kitap_ekle(kitap2)
kutuphane.kitap_ekle(kitap3)

# Üyeler ekle
uye1 = Uye("Ali Veli", "U001")
uye2 = Uye("Ayşe Kaya", "U002")

kutuphane.uye_ekle(uye1)
kutuphane.uye_ekle(uye2)

# Ödünç verme işlemleri
print("\n=== Ödünç Verme İşlemleri ===")
basarili, mesaj = kutuphane.odunc_verme_islemi("Python Programlama", "U001")
print(mesaj)

basarili, mesaj = kutuphane.odunc_verme_islemi("Veri Bilimi", "U001")
print(mesaj)

basarili, mesaj = kutuphane.odunc_verme_islemi("Makine Öğrenmesi", "U002")
print(mesaj)

# İade işlemi
print("\n=== İade İşlemi ===")
basarili, mesaj = kutuphane.iade_islemi("Python Programlama", "U001")
print(mesaj)

# İstatistikler
kutuphane.istatistikleri_goster()
# Çıktı: Python kitabı Ahmet'e verildi, Kütüphanede kalan: 2 kitap
```

### Zor Seviye Çözümleri

#### 8. Ev Otomasyon Sistemi
**Çözüm Mantığı:**
1. Abstract `Cihaz` sınıfı oluştur ve temel interface tanımla.
2. `Isik`, `Termostat`, `GuvenlikKamerasi` sınıflarını kalıtım ile oluştur.
3. `EvSistemi` sınıfı tüm cihazları yönetsin.
4. Observer pattern ile cihaz durumu değişikliklerini takip et.
5. Command pattern ile cihaz komutlarını yönet.

**Optimal Çözüm Kodu:**
```python
from abc import ABC, abstractmethod
from enum import Enum
from typing import List, Dict, Callable
import json

class CihazDurumu(Enum):
    KAPALI = 0
    ACIK = 1

class CihazTipi(Enum):
    ISIK = "ışık"
    TERMOSTAT = "termostat"
    KAMERA = "kamera"

class Cihaz(ABC):
    """Abstract cihaz sınıfı"""
    
    def __init__(self, isim: str, konum: str):
        self.isim = isim
        self.konum = konum
        self.__durum = CihazDurumu.KAPALI
        self.observers: List[Callable] = []
    
    @abstractmethod
    def komut_calistir(self, komut: str, parametreler: Dict = None):
        """Cihaz komutunu çalıştır"""
        pass
    
    @abstractmethod
    def durum_bilgisi(self) -> Dict:
        """Cihazın detaylı durum bilgisini döndür"""
        pass
    
    def ac(self):
        """Cihazı aç"""
        if self.__durum == CihazDurumu.KAPALI:
            self.__durum = CihazDurumu.ACIK
            self._bildirim_gonder("cihaz_acildi")
    
    def kapat(self):
        """Cihazı kapat"""
        if self.__durum == CihazDurumu.ACIK:
            self.__durum = CihazDurumu.KAPALI
            self._bildirim_gonder("cihaz_kapatildi")
    
    def durum_al(self) -> CihazDurumu:
        """Cihaz durumunu al"""
        return self.__durum
    
    def observer_ekle(self, callback: Callable):
        """Observer ekle"""
        self.observers.append(callback)
    
    def _bildirim_gonder(self, olay: str):
        """Observer'lara bildirim gönder"""
        for callback in self.observers:
            try:
                callback(self, olay, self.durum_bilgisi())
            except Exception as e:
                print(f"Observer hatası: {e}")
    
    def __str__(self):
        return f"{self.isim} ({self.konum}) - {self.durum_al().name}"

class Isik(Cihaz):
    """Akıllı ışık sınıfı"""
    
    def __init__(self, isim: str, konum: str, maksimum_parlaklik: int = 100):
        super().__init__(isim, konum)
        self.maksimum_parlaklik = maksimum_parlaklik
        self.__parlaklik = 50  # varsayılan
        self.__renk = (255, 255, 255)  # beyaz RGB
        self.otomatik_mod = False
    
    def komut_calistir(self, komut: str, parametreler: Dict = None):
        if parametreler is None:
            parametreler = {}
        
        if komut == "parlaklik_ayarla":
            self.__parlaklik = min(max(parametreler.get('deger', 50), 0), self.maksimum_parlaklik)
            self._bildirim_gonder("parlaklik_degisti")
        
        elif komut == "renk_ayarla":
            self.__renk = tuple(parametreler.get('renk', (255, 255, 255)))
            self._bildirim_gonder("renk_degisti")
        
        elif komut == "otomatik_mod":
            self.otomatik_mod = parametreler.get('aktif', False)
            self._bildirim_gonder("otomatik_mod_degisti")
    
    def durum_bilgisi(self) -> Dict:
        return {
            'tip': CihazTipi.ISIK.value,
            'isim': self.isim,
            'konum': self.konum,
            'durum': self.durum_al().name,
            'parlaklik': self.__parlaklik,
            'renk': f"RGB{self.__renk}",
            'otomatik_mod': self.otomatik_mod
        }
    
    def parlaklik_al(self) -> int:
        return self.__parlaklik
    
    def renk_al(self) -> tuple:
        return self.__renk

class Termostat(Cihaz):
    """Akıllı termostat sınıfı"""
    
    def __init__(self, isim: str, konum: str, min_sicaklik: float = 10, max_sicaklik: float = 35):
        super().__init__(isim, konum)
        self.min_sicaklik = min_sicaklik
        self.max_sicaklik = max_sicaklik
        self.__hedef_sicaklik = 22.0  # varsayılan
        self.__mevcut_sicaklik = 20.0
        self.__nem_orani = 45
        self.programli_mod = False
        self.enerji_tasarruf_modu = False
    
    def komut_calistir(self, komut: str, parametreler: Dict = None):
        if parametreler is None:
            parametreler = {}
        
        if komut == "sicaklik_ayarla":
            yeni_sicaklik = parametreler.get('deger', self.__hedef_sicaklik)
            self.__hedef_sicaklik = max(self.min_sicaklik, min(yeni_sicaklik, self.max_sicaklik))
            self._bildirim_gonder("hedef_sicaklik_degisti")
        
        elif komut == "nem_ayarla":
            self.__nem_orani = parametreler.get('deger', 45)
            self._bildirim_gonder("nem_degisti")
        
        elif komut == "enerji_tasarruf":
            self.enerji_tasarruf_modu = parametreler.get('aktif', False)
            if self.enerji_tasarruf_modu:
                self.__hedef_sicaklik = max(self.__hedef_sicaklik - 2, self.min_sicaklik)
            self._bildirim_gonder("enerji_mod_degisti")
    
    def durum_bilgisi(self) -> Dict:
        return {
            'tip': CihazTipi.TERMOSTAT.value,
            'isim': self.isim,
            'konum': self.konum,
            'durum': self.durum_al().name,
            'hedef_sicaklik': self.__hedef_sicaklik,
            'mevcut_sicaklik': self.__mevcut_sicaklik,
            'nem_orani': self.__nem_orani,
            'programli_mod': self.programli_mod,
            'enerji_tasarruf': self.enerji_tasarruf_modu
        }
    
    def sicaklik_simule_et(self, yeni_sicaklik: float):
        """Mevcut sıcaklığı simüle et (gerçek sensör yerine)"""
        self.__mevcut_sicaklik = yeni_sicaklik
        if abs(self.__mevcut_sicaklik - self.__hedef_sicaklik) < 0.5:
            self._bildirim_gonder("hedef_sicakliga_ulasti")

class GuvenlikKamerasi(Cihaz):
    """Güvenlik kamerası sınıfı"""
    
    def __init__(self, isim: str, konum: str, maksimum_cozunurluk: str = "4K"):
        super().__init__(isim, konum)
        self.maksimum_cozunurluk = maksimum_cozunurluk
        self.__cozunurluk = "1080p"
        self.__kayit_yapiliyor = False
        self.__hareket_algilama = True
        self.__gece_gorusu = False
        self.__kayit_suresi = 0  # saniye
    
    def komut_calistir(self, komut: str, parametreler: Dict = None):
        if parametreler is None:
            parametreler = {}
        
        if komut == "kayit_baslat":
            self.__kayit_yapiliyor = True
            self.__kayit_suresi = 0
            self._bildirim_gonder("kayit_basladi")
        
        elif komut == "kayit_durdur":
            self.__kayit_yapiliyor = False
            self._bildirim_gonder("kayit_durdu")
        
        elif komut == "cozunurluk_degistir":
            yeni_cozunurluk = parametreler.get('cozunurluk', '1080p')
            if yeni_cozunurluk in ["720p", "1080p", "4K"]:
                self.__cozunurluk = yeni_cozunurluk
                self._bildirim_gonder("cozunurluk_degisti")
        
        elif komut == "hareket_algilama":
            self.__hareket_algilama = parametreler.get('aktif', True)
            self._bildirim_gonder("hareket_algilama_degisti")
        
        elif komut == "gece_gorusu":
            self.__gece_gorusu = parametreler.get('aktif', False)
            self._bildirim_gonder("gece_gorusu_degisti")
    
    def durum_bilgisi(self) -> Dict:
        return {
            'tip': CihazTipi.KAMERA.value,
            'isim': self.isim,
            'konum': self.konum,
            'durum': self.durum_al().name,
            'cozunurluk': self.__cozunurluk,
            'kayit_yapiliyor': self.__kayit_yapiliyor,
            'kayit_suresi': self.__kayit_suresi,
            'hareket_algilama': self.__hareket_algilama,
            'gece_gorusu': self.__gece_gorusu
        }
    
    def kayit_suresi_guncelle(self):
        """Kayıt süresini güncelle (simülasyon)"""
        if self.__kayit_yapiliyor:
            self.__kayit_suresi += 1

class EvSistemi:
    """Ev otomasyon sistemi merkezi"""
    
    def __init__(self, ev_adi: str):
        self.ev_adi = ev_adi
        self.cihazlar: Dict[str, Cihaz] = {}
        self.gecmis_kayitları: List[Dict] = []
        self.__kayit_numarasi = 0
    
    def cihaz_ekle(self, cihaz: Cihaz):
        """Sisteme cihaz ekle"""
        self.cihazlar[cihaz.isim] = cihaz
        cihaz.observer_ekle(self._cihaz_durum_degisti)
        print(f"✅ {cihaz} sisteme eklendi")
    
    def cihaz_komut(self, cihaz_adi: str, komut: str, parametreler: Dict = None):
        """Belirli bir cihaza komut gönder"""
        if cihaz_adi not in self.cihazlar:
            return False, f"❌ '{cihaz_adi}' cihazı bulunamadı!"
        
        cihaz = self.cihazlar[cihaz_adi]
        try:
            cihaz.komut_calistir(komut, parametreler)
            return True, f"✅ {komut} komutu {cihaz_adi} cihazına gönderildi"
        except Exception as e:
            return False, f"❌ Hata: {str(e)}"
    
    def tum_cihazlari_ac(self):
        """Tüm cihazları aç"""
        for cihaz in self.cihazlar.values():
            cihaz.ac()
        return True, f"✅ {len(self.cihazlar)} cihaz açıldı"
    
    def tum_cihazlari_kapat(self):
        """Tüm cihazları kapat"""
        for cihaz in self.cihazlar.values():
            cihaz.kapat()
        return True, f"✅ {len(self.cihazlar)} cihaz kapatıldı"
    
    def sistem_durumu(self) -> Dict:
        """Sistemin genel durumunu döndür"""
        acik_cihaz = len([c for c in self.cihazlar.values() if c.durum_al() == CihazDurumu.ACIK])
        
        return {
            'ev_adi': self.ev_adi,
            'toplam_cihaz': len(self.cihazlar),
            'acik_cihaz': acik_cihaz,
            'kapali_cihaz': len(self.cihazlar) - acik_cihaz,
            'cihaz_detaylari': {adi: cihaz.durum_bilgisi() for adi, cihaz in self.cihazlar.items()}
        }
    
    def cihaz_durumu_sorgula(self, cihaz_adi: str) -> Dict:
        """Belirli bir cihazın durumunu sorgula"""
        if cihaz_adi not in self.cihazlar:
            return {"error": f"'{cihaz_adi}' cihazı bulunamadı"}
        
        return self.cihazlar[cihaz_adi].durum_bilgisi()
    
    def _cihaz_durum_degisti(self, cihaz: Cihaz, olay: str, durum: Dict):
        """Cihaz durumu değiştiğinde çağrılır"""
        self.__kayit_numarasi += 1
        kayit = {
            'kayit_no': self.__kayit_numarasi,
            'zaman': datetime.now().isoformat(),
            'cihaz': cihaz.isim,
            'olay': olay,
            'durum': durum
        }
        self.gecmis_kayitları.append(kayit)
        print(f"📝 [{self.__kayit_numarasi}] {cihaz.isim}: {olay} - {durum}")

# Test
if __name__ == "__main__":
    from datetime import datetime
    
    # Ev sistemi oluştur
    ev = EvSistemi("Akıllı Evim")
    
    # Cihazlar oluştur ve ekle
    isik1 = Isik("Salon Işığı", "Salon", 100)
    termostat1 = Termostat("Ana Termostat", "Oturma Odası")
    kamera1 = GuvenlikKamerası("Giriş Kamerası", "Giriş Kapısı")
    
    ev.cihaz_ekle(isik1)
    ev.cihaz_ekle(termostat1)
    ev.cihaz_ekle(kamera1)
    
    print("\n=== Ev Otomasyon Sistemi Testi ===")
    
    # Cihazları aç
    basarili, mesaj = ev.tum_cihazlari_ac()
    print(mesaj)
    
    # Komutlar gönder
    ev.cihaz_komut("Salon Işığı", "parlaklik_ayarla", {"deger": 80})
    ev.cihaz_komut("Ana Termostat", "sicaklik_ayarla", {"deger": 24})
    ev.cihaz_komut("Giriş Kamerası", "kayit_baslat")
    
    # Sistem durumu
    print(f"\n=== Sistem Durumu ===")
    durum = ev.sistem_durumu()
    print(f"Ev: {durum['ev_adi']}")
    print(f"Toplam Cihaz: {durum['toplam_cihaz']}")
    print(f"Açık Cihaz: {durum['acik_cihaz']}")
    
    # Belirli cihaz durumu
    print(f"\n=== Salon Işığı Durumu ===")
    isik_durumu = ev.cihaz_durumu_sorgula("Salon Işığı")
    print(json.dumps(isik_durumu, indent=2, ensure_ascii=False))
    
    # Cihazları kapat
    ev.tum_cihazlari_kapat()
    print(f"\n✅ Test tamamlandı! Toplam {len(ev.gecmis_kayitları)} olay kaydedildi.")
```

---

Bu doküman, Python'un OOP konseptlerini kullanarak gerçek dünya problemlerini çözme becerinizi geliştirmenize yardımcı olmak için hazırlanmıştır. Her seviyedeki sorular, sınıf tasarımı, kalıtım, çok biçimlilik ve kapsülleme kavramlarını derinlemesine anlamanızı sağlar.

---