# 🛫 Havayolu Yolcu Memnuniyeti Veri Analizi Raporu

**Proje Sahibi:** Eda Özge Uğurlu  
**Veri Seti:** [Airline Passenger Satisfaction Dataset - train.csv]

---

## 📌 Veri Seti Seçimi ve Tanımı

Bu projede, yolcu memnuniyetini etkileyen çeşitli faktörleri içeren **"Airline Passenger Satisfaction Dataset"** adlı veri seti kullanılmıştır.  
Veri seti; uçuş mesafesi, gecikmeler, hizmet kalitesi gibi birçok değişkeni barındırmaktadır.

### 🎯 Amaç

Yolcu memnuniyetine etki eden unsurları analiz ederek, bu alanda öngörülerde bulunmak ve veri temelli çıkarımlar elde etmektir.

---

## 📊 İstatistiksel Özet

Sayısal değişkenlerin merkezi eğilim ve dağılım ölçütleri `df.describe()` metodu kullanılarak analiz edilmiştir.  
Bu analiz sayesinde, veri setindeki temel yapılar anlaşılmış ve genel dağılım özellikleri elde edilmiştir.

---

## ❗ Eksik Değer Analizi

- **Eksik Değer Bulunan Sütun:** `Arrival Delay in Minutes`
- **Eksik Değer Sayısı:** 393
- **Toplam Veriye Oranı:** %1.31

> Bu projede eksik veriler silinmemiş, analiz sürecine dahil edilmiştir.

---

## ⚠️ Aykırı Değer Analizi

- Aykırı değerler, **IQR (Interquartile Range)** yöntemi kullanılarak belirlenmiştir.
- Görselleştirme amacıyla **Boxplot** grafiklerinden yararlanılmıştır.

> Aykırı değerler çıkarılmamış, analizde değerlendirilmiştir.

---

## 📈 Görselleştirme

### 🔹 Sayısal Değişkenler

- Uçuş mesafesi, gecikme süreleri vb. değişkenler için **Histogram** grafikler oluşturulmuştur.

### 🔸 Kategorik Değişkenler

- Cinsiyet, uçuş sınıfı, hizmet değerlendirmeleri gibi değişkenler **Bar chart** ile görselleştirilmiştir.

---

## 🔍 Memnuniyet Analizi

- Memnuniyet düzeyi ile uçuş sınıfı ve gecikmeler gibi değişkenler arasında **anlamlı farklar** tespit edilmiştir.
- Bu farklar, yolcu memnuniyetini etkileyen başlıca unsurlar olarak değerlendirilmiştir.

---

## 📝 Sonuç ve Yorum

- Veri seti, eksik ve aykırı değerler açısından detaylıca analiz edilmiştir.
- Görselleştirmeler ile örüntüler daha görünür hale getirilmiş, yolcu memnuniyetine etki eden faktörler belirlenmiştir.
- Bu analiz, havayolu şirketleri için **hizmet kalitesini artırmaya yönelik stratejik kararlar** açısından yol gösterici olabilir.

---

## 📂 Kullanılan Kütüphaneler

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`

---

## 📌 Not

Bu çalışma, bireysel bir analiz projesi olup eğitim amaçlı gerçekleştirilmiştir.




