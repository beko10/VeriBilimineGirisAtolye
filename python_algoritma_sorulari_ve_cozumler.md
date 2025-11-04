# Python Algoritma Soruları ve Çözümleri

Bu doküman, belirtilen konuları kullanarak problem çözme becerisini geliştirmeye yönelik olarak hazırlanmıştır ve iki ana bölümden oluşmaktadır.

## Bölüm 1: Sorular

### Kolay Seviye Sorular

#### 1. Listedeki En Büyük Sayıyı Bulma
**Problem Tanımı:** Verilen bir tamsayı listesindeki en büyük sayıyı bulan bir fonksiyon yazın.

**Girdi Formatı:** Tamsayılardan oluşan bir liste.

**Çıktı Formatı:** Listedeki en büyük tamsayı.

**Kısıtlamalar:** Liste boş olmayacak ve en az bir eleman içerecektir.

**Örnek Senaryolar:**
- Girdi: `[1, 2, 3, 4, 5]`
- Çıktı: `5`
- Girdi: `[-1, -5, -3]`
- Çıktı: `-1`

#### 2. String'i Ters Çevirme
**Problem Tanımı:** Verilen bir string'i ters çeviren bir fonksiyon yazın.

**Girdi Formatı:** Bir string.

**Çıktı Formatı:** Ters çevrilmiş string.

**Kısıtlamalar:** Girdi her zaman bir string olacaktır.

**Örnek Senaryolar:**
- Girdi: `"hello"`
- Çıktı: `"olleh"`
- Girdi: `"Python"`
- Çıktı: `"nohtyP"`

#### 3. Faktöriyel Hesaplama
**Problem Tanımı:** Negatif olmayan bir tamsayının faktöriyelini hesaplayan bir fonksiyon yazın.

**Girdi Formatı:** Negatif olmayan bir tamsayı.

**Çıktı Formatı:** Girdinin faktöriyeli.

**Kısıtlamalar:** Girdi 0 veya pozitif bir tamsayı olacaktır.

**Örnek Senaryolar:**
- Girdi: `5`
- Çıktı: `120`
- Girdi: `0`
- Çıktı: `1`

#### 4. Listedeki Çift Sayıları Filtreleme
**Problem Tanımı:** Verilen bir tamsayı listesindeki yalnızca çift sayıları içeren yeni bir liste döndüren bir fonksiyon yazın.

**Girdi Formatı:** Tamsayılardan oluşan bir liste.

**Çıktı Formatı:** Yalnızca çift tamsayıları içeren yeni bir liste.

**Kısıtlamalar:** Girdi listesi boş olabilir.

**Örnek Senaryolar:**
- Girdi: `[1, 2, 3, 4, 5, 6]`
- Çıktı: `[2, 4, 6]`
- Girdi: `[11, 23, 44]`
- Çıktı: `[44]`

#### 5. İki Listenin Birleşimi ve Tekilleştirilmesi
**Problem Tanımı:** Verilen iki listeyi birleştiren ve tekrar eden elemanları kaldırarak tekil bir liste oluşturan bir fonksiyon yazın.

**Girdi Formatı:** İki tamsayı listesi.

**Çıktı Formatı:** Birleştirilmiş ve tekilleştirilmiş liste.

**Kısıtlamalar:** Girdi listeleri boş olabilir.

**Örnek Senaryolar:**
- Girdi: `[1, 2, 3]`, `[3, 4, 5]`
- Çıktı: `[1, 2, 3, 4, 5]` (sıra önemli değil)
- Girdi: `[]`, `[1, 1, 2]`
- Çıktı: `[1, 2]` (sıra önemli değil)

### Orta Seviye Sorular

#### 6. Palindrom Kontrolü
**Problem Tanımı:** Verilen bir string'in palindrom olup olmadığını kontrol eden bir fonksiyon yazın (tersten okunuşu aynı olan kelime/cümle).

**Girdi Formatı:** Bir string.

**Çıktı Formatı:** `True` veya `False`.

**Kısıtlamalar:** Boşluklar ve büyük/küçük harf duyarlılığı göz ardı edilmelidir.

**Örnek Senaryolar:**
- Girdi: `"A man a plan a canal Panama"`
- Çıktı: `True`
- Girdi: `"hello"`
- Çıktı: `False`

#### 7. İki Sayının En Büyük Ortak Böleni (EBOB)
**Problem Tanımı:** Verilen iki pozitif tamsayının en büyük ortak bölenini (EBOB) bulan bir fonksiyon yazın.

**Girdi Formatı:** İki pozitif tamsayı.

**Çıktı Formatı:** EBOB değeri.

**Kısıtlamalar:** Girdiler her zaman pozitif tamsayı olacaktır.

**Örnek Senaryolar:**
- Girdi: `54`, `24`
- Çıktı: `6`
- Girdi: `7`, `13`
- Çıktı: `1`

#### 8. Anagram Kontrolü
**Problem Tanımı:** Verilen iki string'in anagram olup olmadığını kontrol eden bir fonksiyon yazın (aynı harfleri farklı sıralamada içeren kelimeler).

**Girdi Formatı:** İki string.

**Çıktı Formatı:** `True` veya `False`.

**Kısıtlamalar:** Boşluklar ve büyük/küçük harf duyarlılığı göz ardı edilmelidir.

**Örnek Senaryolar:**
- Girdi: `"listen"`, `"silent"`
- Çıktı: `True`
- Girdi: `"hello"`, `"world"`
- Çıktı: `False`

#### 9. Listedeki Eksik Sayıyı Bulma
**Problem Tanımı:** 1'den N'e kadar olan sayılardan birinin eksik olduğu bir liste veriliyor. Eksik olan sayıyı bulan bir fonksiyon yazın.

**Girdi Formatı:** 1'den N'e kadar olan (bir tanesi eksik) tamsayıları içeren bir liste.

**Çıktı Formatı:** Eksik olan tamsayı.

**Kısıtlamalar:** Liste her zaman bir eleman eksik olacaktır ve tekrar eden eleman içermeyecektir.

**Örnek Senaryolar:**
- Girdi: `[1, 2, 4, 5]` (N=5)
- Çıktı: `3`
- Girdi: `[9, 6, 4, 2, 3, 5, 7, 0, 1]` (N=9, 0'dan N'e)
- Çıktı: `8`

#### 10. Listeyi Belirli Bir Değere Göre Döndürme (Rotate)
**Problem Tanımı:** Verilen bir listeyi, belirtilen `k` adımı kadar sağa döndüren bir fonksiyon yazın.

**Girdi Formatı:** Bir liste ve döndürme adımı `k` (pozitif tamsayı).

**Çıktı Formatı:** Döndürülmüş liste.

**Kısıtlamalar:** `k` negatif olmayan bir tamsayıdır.

**Örnek Senaryolar:**
- Girdi: `[1, 2, 3, 4, 5]`, `k=2`
- Çıktı: `[4, 5, 1, 2, 3]`
- Girdi: `[-1, -100, 3, 99]`, `k=2`
- Çıktı: `[3, 99, -1, -100]`

### Zor Seviye Sorular

#### 11. İki Sıralı Listenin Medyanını Bulma
**Problem Tanımı:** Verilen iki sıralı tamsayı listesinin birleştirilmiş halinin medyanını bulan bir fonksiyon yazın. Algoritmanın zaman karmaşıklığı O(log(m+n)) olmalıdır; burada m ve n listelerin uzunluklarıdır.

**Girdi Formatı:** İki sıralı tamsayı listesi.

**Çıktı Formatı:** Medyan değeri (float).

**Kısıtlamalar:** Listeler boş olabilir, ancak ikisi aynı anda boş olamaz.

**Örnek Senaryolar:**
- Girdi: `[1, 3]`, `[2]`
- Çıktı: `2.0`
- Girdi: `[1, 2]`, `[3, 4]`
- Çıktı: `2.5`

#### 12. En Uzun Palindromik Alt String
**Problem Tanımı:** Verilen bir string içindeki en uzun palindromik alt string'i bulan bir fonksiyon yazın.

**Girdi Formatı:** Bir string.

**Çıktı Formatı:** En uzun palindromik alt string.

**Kısıtlamalar:** Girdi string'inin maksimum uzunluğu 1000'dir.

**Örnek Senaryolar:**
- Girdi: `"babad"`
- Çıktı: `"bab"` ("aba" da geçerli bir cevaptır).
- Girdi: `"cbbd"`
- Çıktı: `"bb"`

#### 13. Kelime Merdiveni (Word Ladder)
**Problem Tanımı:** Bir başlangıç kelimesinden bir bitiş kelimesine, her adımda sadece bir harf değiştirerek ve her ara kelimenin verilen kelime listesinde bulunması koşuluyla en kısa dönüşüm dizisinin uzunluğunu bulun.

**Girdi Formatı:** Başlangıç kelimesi, bitiş kelimesi ve bir kelime listesi.

**Çıktı Formatı:** En kısa dönüşüm uzunluğu. Eğer dönüşüm mümkün değilse 0.

**Kısıtlamalar:** Tüm kelimeler aynı uzunluktadır ve küçük harflerden oluşur.

**Örnek Senaryolar:**
- Girdi: `beginWord = "hit"`, `endWord = "cog"`, `wordList = ["hot","dot","dog","lot","log","cog"]`
- Çıktı: `5` (hit -> hot -> dot -> dog -> cog)
- Girdi: `beginWord = "hit"`, `endWord = "cog"`, `wordList = ["hot","dot","dog","lot","log"]`
- Çıktı: `0`

#### 14. Maksimum Alt Dizi Toplamı
**Problem Tanımı:** Verilen bir tamsayı dizisindeki bitişik alt dizilerden en büyük toplama sahip olanını bulun ve bu toplamı döndürün.

**Girdi Formatı:** Bir tamsayı listesi.

**Çıktı Formatı:** Maksimum alt dizi toplamı.

**Kısıtlamalar:** Liste en az bir eleman içerir.

**Örnek Senaryolar:**
- Girdi: `[-2, 1, -3, 4, -1, 2, 1, -5, 4]`
- Çıktı: `6` (Alt dizi: `[4, -1, 2, 1]`)
- Girdi: `[5, 4, -1, 7, 8]`
- Çıktı: `23` (Alt dizi: `[5, 4, -1, 7, 8]`)

#### 15. Birleştirme Aralıkları (Merge Intervals)
**Problem Tanımı:** Verilen bir aralık listesinde, çakışan aralıkları birleştirin ve yeni bir aralık listesi döndürün.

**Girdi Formatı:** Her biri `[başlangıç, bitiş]` formatında olan bir aralık listesi.

**Çıktı Formatı:** Çakışan aralıkların birleştirildiği yeni bir aralık listesi.

**Kısıtlamalar:** Girdi listesi başlangıç değerine göre sıralanmamış olabilir.

**Örnek Senaryolar:**
- Girdi: `[[1,3],[2,6],[8,10],[15,18]]`
- Çıktı: `[[1,6],[8,10],[15,18]]`
- Girdi: `[[1,4],[4,5]]`
- Çıktı: `[[1,5]]`

---

## Bölüm 2: Çözümler

### Kolay Seviye Çözümleri

#### 1. Listedeki En Büyük Sayıyı Bulma
**Çözüm Mantığı:**
1. Listenin ilk elemanını geçici olarak en büyük sayı (`max_sayi`) olarak ayarla.
2. Liste üzerinde bir döngü başlat (ikinci elemandan başlayarak).
3. Döngüdeki her elemanı `max_sayi` ile karşılaştır.
4. Eğer döngüdeki eleman `max_sayi`'dan büyükse, `max_sayi`'yı bu yeni elemanla güncelle.
5. Döngü bittiğinde, `max_sayi` değişkeni listenin en büyük elemanını tutacaktır.

**Optimal Çözüm Kodu:**
```python
def en_buyuk_sayi(liste):
    # Python'un yerleşik max() fonksiyonu bu iş için en basit ve etkili yoldur.
    return max(liste)

# Test
print(en_buyuk_sayi([1, 2, 3, 4, 5]))
# Çıktı: 5
```

**Alternatif Yaklaşım (Döngü ile):**
```python
def en_buyuk_sayi_dongu(liste):
    max_sayi = liste[0] # İlk elemanı en büyük olarak kabul et
    for sayi in liste[1:]:
        if sayi > max_sayi:
            max_sayi = sayi # Daha büyük bir sayı bulursak güncelle
    return max_sayi

# Test
print(en_buyuk_sayi_dongu([-1, -5, -3]))
# Çıktı: -1
```

#### 2. String'i Ters Çevirme
**Çözüm Mantığı:**
Python'da string'ler dilimleme (slicing) adı verilen bir özelliği destekler. `[::]` formatı ile string'in başlangıcı, bitişi ve adımı belirtilebilir. Adım olarak -1 kullanmak, string'i sondan başa doğru birer birer okur ve bu da string'in ters çevrilmesini sağlar.

**Optimal Çözüm Kodu:**
```python
def ters_cevir(s):
    # String dilimleme ile ters çevirme en kısa yoldur.
    # [::-1] ifadesi, string'i baştan sona -1 adımla (yani tersten) okur.
    return s[::-1]

# Test
print(ters_cevir("hello"))
# Çıktı: "olleh"
```

#### 3. Faktöriyel Hesaplama
**Çözüm Mantığı:**
1. Faktöriyel, bir sayının kendisinden 1'e kadar olan tüm pozitif tamsayılarla çarpımıdır. (0! = 1 kabul edilir).
2. Sonucu tutmak için bir değişken (`sonuc`) oluştur ve başlangıç değerini 1 yap.
3. 1'den verilen sayıya kadar (verilen sayı dahil) bir döngü oluştur.
4. Döngünün her adımında, `sonuc` değişkenini döngüdeki sayı ile çarp.
5. Döngü bittiğinde, `sonuc` faktöriyel değerini tutacaktır.

**Optimal Çözüm Kodu:**
```python
def faktoriyel(n):
    if n == 0:
        return 1 # 0'ın faktöriyeli 1'dir.
    sonuc = 1
    # 1'den n'ye kadar olan sayıları çarp
    for i in range(1, n + 1):
        sonuc *= i
    return sonuc

# Test
print(faktoriyel(5))
# Çıktı: 120
```

**Alternatif Yaklaşım (Recursive):**
```python
def faktoriyel_recursive(n):
    # Temel durum: n 0 ise 1 döndür
    if n == 0:
        return 1
    # Recursive adım: n * (n-1)!
    else:
        return n * faktoriyel_recursive(n - 1)

# Test
print(faktoriyel_recursive(0))
# Çıktı: 1
```

#### 4. Listedeki Çift Sayıları Filtreleme
**Çözüm Mantığı:**
1. Çift sayıları depolamak için boş bir liste (`cift_sayilar`) oluştur.
2. Girdi listesindeki her bir sayı için bir döngü başlat.
3. Her sayının 2'ye bölümünden kalanın 0 olup olmadığını kontrol et ( `sayi % 2 == 0` ).
4. Eğer kalan 0 ise, bu sayı çifttir ve `cift_sayilar` listesine eklenir.
5. Döngü tamamlandığında, `cift_sayilar` listesini döndür.

**Optimal Çözüm Kodu (List Comprehension):**
```python
def ciftleri_filtrele(liste):
    # List comprehension, bu tür filtreleme işlemleri için en okunaklı ve Pythonic yoldur.
    return [sayi for sayi in liste if sayi % 2 == 0]

# Test
print(ciftleri_filtrele([1, 2, 3, 4, 5, 6]))
# Çıktı: [2, 4, 6]
```

#### 5. İki Listenin Birleşimi ve Tekilleştirilmesi
**Çözüm Mantığı:**
1. Python'daki `set` veri yapısı, doğası gereği tekrar eden elemanları barındırmaz.
2. İki listeyi birleştirmek için `+` operatörünü kullan.
3. Birleştirilmiş listeyi bir `set`'e dönüştürerek tekrar eden elemanlardan kurtul.
4. Son olarak, bu `set`'i tekrar bir listeye dönüştürerek sonucu elde et.

**Optimal Çözüm Kodu:**
```python
def birlestir_ve_tekillestir(liste1, liste2):
    # İki listeyi birleştir, set'e çevirerek tekilleştir ve tekrar listeye çevir.
    birlesik_liste = liste1 + liste2
    return list(set(birlesik_liste))

# Test
print(birlestir_ve_tekillestir([1, 2, 3], [3, 4, 5]))
# Çıktı: [1, 2, 3, 4, 5] (Sıra farklı olabilir)
```

### Orta Seviye Çözümleri

#### 6. Palindrom Kontrolü
**Çözüm Mantığı:**
1. String'i işlemeye hazırlamak için tüm harfleri küçük harfe çevir ve boşlukları kaldır.
2. Temizlenmiş string'in tersi ile kendisinin aynı olup olmadığını kontrol et. Eğer aynıysa, bu bir palindromdur.

**Optimal Çözüm Kodu:**
```python
def is_palindrome(s):
    # 1. Adım: String'i temizle (küçük harf ve boşluksuz)
    temiz_s = ''.join(filter(str.isalnum, s)).lower()
    # 2. Adım: Temizlenmiş string'i tersiyle karşılaştır
    return temiz_s == temiz_s[::-1]

# Test
print(is_palindrome("A man a plan a canal Panama"))
# Çıktı: True
```

#### 7. İki Sayının En Büyük Ortak Böleni (EBOB)
**Çözüm Mantığı (Öklid Algoritması):**
1. İki sayı (`a` ve `b`) al. `b` sıfır olmadığı sürece döngüyü tekrarla.
2. Her adımda, `a`'yı `b`'ye, `b`'yi ise `a`'nın `b`'ye bölümünden kalana (`a % b`) eşitle.
3. `b` sıfır olduğunda, `a` değişkeni EBOB değerini tutacaktır.

**Optimal Çözüm Kodu:**
```python
def ebob(a, b):
    # Öklid algoritması
    while b:
        a, b = b, a % b
    return a

# Test
print(ebob(54, 24))
# Çıktı: 6
```

#### 8. Anagram Kontrolü
**Çözüm Mantığı:**
1. İki string'in anagram olması için aynı harfleri aynı sayıda içermeleri gerekir.
2. String'leri küçük harfe çevirip boşluklarını kaldırdıktan sonra sıralarsak, anagram olan iki string tamamen aynı sıralanmış string'i üretecektir.

**Optimal Çözüm Kodu:**
```python
def is_anagram(s1, s2):
    # String'leri temizle ve sırala
    temiz_s1 = sorted(''.join(filter(str.isalnum, s1)).lower())
    temiz_s2 = sorted(''.join(filter(str.isalnum, s2)).lower())
    # Sıralanmış hallerini karşılaştır
    return temiz_s1 == temiz_s2

# Test
print(is_anagram("listen", "silent"))
# Çıktı: True
```

#### 9. Listedeki Eksik Sayıyı Bulma
**Çözüm Mantığı (Gauss Toplam Formülü):**
1. 1'den N'e kadar olan sayıların toplamı `N * (N + 1) / 2` formülü ile bulunabilir.
2. Beklenen toplamı bu formülle hesapla.
3. Verilen listenin içindeki sayıların gerçek toplamını bul.
4. Beklenen toplamdan gerçek toplamı çıkardığında eksik sayıyı bulursun.

**Optimal Çözüm Kodu:**
```python
def find_missing_number(nums):
    n = len(nums)
    # 0'dan n'e kadar olan sayıların beklenen toplamı
    beklenen_toplam = n * (n + 1) // 2
    # Listenin gerçek toplamı
    gercek_toplam = sum(nums)
    # Aradaki fark eksik sayıyı verir
    return beklenen_toplam - gercek_toplam

# Test
# 0'dan 9'a kadar olan sayılardan 8 eksik
print(find_missing_number([9, 6, 4, 2, 3, 5, 7, 0, 1]))
# Çıktı: 8
```

#### 10. Listeyi Belirli Bir Değere Göre Döndürme (Rotate)
**Çözüm Mantığı:**
1. `k` değeri listenin uzunluğundan büyük olabilir, bu yüzden `k`'yi listenin uzunluğuna göre modunu alarak sadeleştir (`k = k % len(liste)`).
2. Listenin son `k` elemanını al. Bu, yeni listenin başı olacak.
3. Listenin ilk `len(liste) - k` elemanını al. Bu, yeni listenin sonu olacak.
4. Bu iki parçayı birleştir.

**Optimal Çözüm Kodu:**
```python
def rotate_array(nums, k):
    n = len(nums)
    k = k % n # k'nin liste uzunluğundan büyük olma ihtimaline karşı
    if k == 0:
        return nums
    # Son k elemanı başa, geri kalanı sona ekle
    return nums[-k:] + nums[:-k]

# Test
print(rotate_array([1, 2, 3, 4, 5], 2))
# Çıktı: [4, 5, 1, 2, 3]
```

### Zor Seviye Çözümleri

#### 11. İki Sıralı Listenin Medyanını Bulma
**Çözüm Mantığı (Binary Search Yaklaşımı):**
Bu problem, O(log(m+n)) zaman karmaşıklığı gerektirdiği için binary search kullanmamız gerekir. İki listeyi birleştirmek yerine, medyanın hangi pozisyonda olacağını hesaplayıp, bu pozisyondaki elemanı binary search ile buluruz.

**Optimal Çözüm Kodu:**
```python
def findMedianSortedArrays(nums1, nums2):
    # Daha kısa olan listeyi nums1 yapalım
    if len(nums1) > len(nums2):
        nums1, nums2 = nums2, nums1
    
    m, n = len(nums1), len(nums2)
    left, right = 0, m
    
    while left <= right:
        # nums1'den kaç eleman alacağımızı belirle
        partition1 = (left + right) // 2
        # nums2'den kaç eleman alacağımızı belirle
        partition2 = (m + n + 1) // 2 - partition1
        
        # Sol tarafın maksimum değerleri
        max_left1 = float('-inf') if partition1 == 0 else nums1[partition1 - 1]
        max_left2 = float('-inf') if partition2 == 0 else nums2[partition2 - 1]
        
        # Sağ tarafın minimum değerleri
        min_right1 = float('inf') if partition1 == m else nums1[partition1]
        min_right2 = float('inf') if partition2 == n else nums2[partition2]
        
        # Doğru bölümlemeyi bulduysak
        if max_left1 <= min_right2 and max_left2 <= min_right1:
            # Toplam eleman sayısı çiftse
            if (m + n) % 2 == 0:
                return (max(max_left1, max_left2) + min(min_right1, min_right2)) / 2
            # Toplam eleman sayısı tekse
            else:
                return max(max_left1, max_left2)
        
        # Sol tarafta çok eleman var, nums1'den daha az al
        elif max_left1 > min_right2:
            right = partition1 - 1
        # Sol tarafta az eleman var, nums1'den daha fazla al
        else:
            left = partition1 + 1

# Test
print(findMedianSortedArrays([1, 3], [2]))
# Çıktı: 2.0
```

#### 12. En Uzun Palindromik Alt String
**Çözüm Mantığı (Expand Around Centers):**
Her karakteri ve her iki karakter arasını merkez olarak kabul ederek, o merkezden başlayarak palindromu genişletmeye çalışırız. Bu yaklaşım O(n²) zaman karmaşıklığına sahiptir.

**Optimal Çözüm Kodu:**
```python
def longestPalindrome(s):
    if not s:
        return ""
    
    start = 0
    max_len = 1
    
    def expand_around_center(left, right):
        # Merkez etrafında palindromu genişlet
        while left >= 0 and right < len(s) and s[left] == s[right]:
            left -= 1
            right += 1
        return right - left - 1  # Palindromun uzunluğu
    
    for i in range(len(s)):
        # Tek uzunluklu palindrom (merkez bir karakter)
        len1 = expand_around_center(i, i)
        # Çift uzunluklu palindrom (merkez iki karakter arası)
        len2 = expand_around_center(i, i + 1)
        
        # En uzun palindromu güncelle
        current_max = max(len1, len2)
        if current_max > max_len:
            max_len = current_max
            start = i - (current_max - 1) // 2
    
    return s[start:start + max_len]

# Test
print(longestPalindrome("babad"))
# Çıktı: "bab" veya "aba"
```

#### 13. Kelime Merdiveni (Word Ladder)
**Çözüm Mantığı (BFS - Breadth-First Search):**
Bu problem, en kısa yolu bulmayı gerektirdiği için BFS algoritması kullanılır. Her kelimeden bir harf değiştirerek ulaşılabilecek tüm geçerli kelimeleri kontrol ederiz.

**Optimal Çözüm Kodu:**
```python
from collections import deque

def ladderLength(beginWord, endWord, wordList):
    if endWord not in wordList:
        return 0
    
    wordSet = set(wordList)
    queue = deque([(beginWord, 1)])  # (kelime, adım_sayısı)
    visited = set([beginWord])
    
    while queue:
        current_word, steps = queue.popleft()
        
        # Hedef kelimeye ulaştık
        if current_word == endWord:
            return steps
        
        # Mevcut kelimeden bir harf değiştirerek yeni kelimeler üret
        for i in range(len(current_word)):
            for c in 'abcdefghijklmnopqrstuvwxyz':
                new_word = current_word[:i] + c + current_word[i+1:]
                
                # Yeni kelime geçerli ve daha önce ziyaret edilmemişse
                if new_word in wordSet and new_word not in visited:
                    visited.add(new_word)
                    queue.append((new_word, steps + 1))
    
    return 0  # Dönüşüm mümkün değil

# Test
print(ladderLength("hit", "cog", ["hot","dot","dog","lot","log","cog"]))
# Çıktı: 5
```

#### 14. Maksimum Alt Dizi Toplamı
**Çözüm Mantığı (Kadane's Algorithm):**
Bu klasik algoritma, her pozisyonda "buraya kadar olan maksimum toplamı" hesaplar. Eğer önceki toplam negatifse, yeni bir alt dizi başlatmak daha mantıklıdır.

**Optimal Çözüm Kodu:**
```python
def maxSubArray(nums):
    max_current = max_global = nums[0]
    
    for i in range(1, len(nums)):
        # Mevcut elemanı önceki toplama ekle veya yeni bir alt dizi başlat
        max_current = max(nums[i], max_current + nums[i])
        # Global maksimumu güncelle
        max_global = max(max_global, max_current)
    
    return max_global

# Test
print(maxSubArray([-2, 1, -3, 4, -1, 2, 1, -5, 4]))
# Çıktı: 6
```

#### 15. Birleştirme Aralıkları (Merge Intervals)
**Çözüm Mantığı:**
1. Aralıkları başlangıç değerine göre sırala.
2. İlk aralığı sonuç listesine ekle.
3. Her yeni aralık için, son eklenen aralıkla çakışıp çakışmadığını kontrol et.
4. Çakışıyorsa birleştir, çakışmıyorsa yeni aralık olarak ekle.

**Optimal Çözüm Kodu:**
```python
def merge(intervals):
    if not intervals:
        return []
    
    # Aralıkları başlangıç değerine göre sırala
    intervals.sort(key=lambda x: x[0])
    
    merged = [intervals[0]]
    
    for current in intervals[1:]:
        last_merged = merged[-1]
        
        # Mevcut aralık, son birleştirilmiş aralıkla çakışıyor mu?
        if current[0] <= last_merged[1]:
            # Çakışıyorsa birleştir (bitiş değerini güncelle)
            last_merged[1] = max(last_merged[1], current[1])
        else:
            # Çakışmıyorsa yeni aralık olarak ekle
            merged.append(current)
    
    return merged

# Test
print(merge([[1,3],[2,6],[8,10],[15,18]]))
# Çıktı: [[1, 6], [8, 10], [15, 18]]
```

---

Bu doküman, Python'un temel konularını kullanarak algoritma problemlerini çözme becerinizi geliştirmenize yardımcı olmak için hazırlanmıştır. Her zorluk seviyesindeki sorular, gerçek programlama mülakatlarında ve pratik uygulamalarda karşılaşabileceğiniz problem türlerini temsil etmektedir.

---
