## **Müşteri Segmentasyonu ve Analizi Raporu**

### **1. Giriş**

Bu rapor, müşteri verilerini kullanarak yapılan K-Means kümeleme analizini ve elde edilen segmentlerin özelliklerini detaylandırır. Analiz, müşterilerin satın alma davranışlarını anlamak ve hedeflenmiş stratejiler geliştirmek amacıyla gerçekleştirilmiştir.

### **2. Verinin Hazırlanması**

#### **2.1 Veri Yükleme ve Temizleme**

- **Veri Kümesi**: `data.csv` dosyasından yüklenen veriler.
- **Sütunlar**: `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, `Country`.
- **Eksik Veriler**: `InvoiceDate` sütunundaki eksik veriler `dropna` ile temizlendi.

#### **2.2 RFM Analizi**

- **Recency (En son alışveriş tarihi)**: `snapshot_date` kullanılarak müşterinin en son alışveriş yaptığı tarihten bugüne kadar geçen gün sayısı hesaplandı.
- **Frequency (Alışveriş Sıklığı)**: Müşterinin yaptığı benzersiz fatura sayısı.
- **Monetary (Toplam Harcama)**: Müşterinin yaptığı toplam harcama.

### **3. K-Means Kümeleme**

#### **3.1 Ölçeklendirme**

- **StandardScaler** kullanılarak RFM değerleri standartlaştırıldı. Bu adım, farklı ölçeklerdeki değişkenlerin eşit ağırlıkta değerlendirilmesini sağlar.

#### **3.2 Kümeleme**

- **K-Means Modeli**: `n_clusters=4` ile dört farklı segment oluşturuldu.
- **Sonuçların İncelenmesi**: Her bir segmentin ortalama `Recency`, `Frequency`, ve `Monetary` değerleri hesaplandı.

### **4. Sonuçlar ve Bulgular**

#### **4.1 Segment Özellikleri**

- **Segment 0**: Ortalama olarak yüksek harcama, düşük sıklıkta alışveriş.
- **Segment 1**: Yüksek sıklıkta alışveriş, orta seviyede harcama.
- **Segment 2**: Düşük recency ve yüksek frequency, düşük harcama.
- **Segment 3**: Düşük recency, düşük frequency, orta seviyede harcama.

#### **4.2 Segment Bazında Analiz**

- **Yüksek Harcama Segmenti**: Bu segmentin müşterilerine özel teklifler sunulabilir.
- **Yüksek Sıklıkta Alışveriş Yapan Segment**: Sadakat programları ve ödüller ile bu segmentin memnuniyeti artırılabilir.
- **Düşük Harcama Segmenti**: Bu segmentin alışveriş davranışlarını artırmak için teşvikler ve indirimler sunulabilir.

### **5. Uygulama Önerileri**

#### **5.1 Pazarlama Stratejileri**

- **Yüksek Harcama Segmenti**: Özel kampanyalar, premium ürün önerileri.
- **Yüksek Sıklıkta Alışveriş Yapan Segment**: Sadakat programları, düzenli müşteri ödülleri.
- **Düşük Harcama Segmenti**: İndirimler, teşvikler.

#### **5.2 Satış Tahminleri**

- Segmentlerin ortalama harcama değerlerine göre gelecekteki satış tahminleri yapılabilir.

### **6. Sonuç ve Öneriler**

K-Means segmentasyonu ile müşteri gruplarının özelliklerini detaylı bir şekilde inceledik. Her segmentin belirli özellikleri ve davranışları olduğu gözlemlendi. Bu bilgiler, hedeflenmiş pazarlama stratejileri geliştirmek ve müşteri memnuniyetini artırmak için kullanılabilir. İlerleyen aşamalarda, segmentlere yönelik spesifik kampanyaların ve stratejilerin uygulanması önerilmektedir.
