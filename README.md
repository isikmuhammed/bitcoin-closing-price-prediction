# Bitcoin Kapanış Fiyatı Tahmini
Bu proje, Bitcoin'in kapanış fiyatını geçmiş veriler kullanarak tahmin etmeyi amaçlamaktadır. Modelin performansı, Ortalama Kare Hata (MSE) ve R² skoru gibi çeşitli metriklerle değerlendirilmiştir.

İçindekiler
 Veri Seti
 Ön İşleme
 Modelleme
 Değerlendirme
 Sonuçlar
 Nasıl Çalıştırılır

Veri Seti
Bu veri seti, 2018'den Eylül 2024'e kadar olan saatlik Bitcoin verilerini içermektedir. Kullanılan temel özellikler şunlardır:

Açılış (Open): Saatlik açılış fiyatı.
Kapanış (Close): Bitcoin'in saatlik kapanış fiyatı (Hedef değişken).
En Yüksek (High) ve En Düşük (Low): Saatlik en yüksek ve en düşük fiyatlar.
Hacim (Volume): Saatlik toplam işlem hacmi.
Ön İşleme
Veri seti, modele girmeden önce aşağıdaki ön işleme adımlarından geçirilmiştir:

Eksik verilerin doldurulması veya çıkarılması.
MinMaxScaler kullanılarak özelliklerin ölçeklenmesi.
Verilerin eğitim (%80) ve test (%20) olarak ayrılması.
Modelleme
Bitcoin fiyat tahmini için çeşitli makine öğrenmesi modelleri denenmiştir:

Doğrusal Regresyon (Linear Regression): Temel bir regresyon modeli ile başlangıç noktası oluşturuldu.
Karar Ağacı Sınıflandırıcısı (Decision Tree Classifier): Verideki doğrusal olmayan ilişkileri modellemek için kullanıldı.
Veriler ayrıca çapraz doğrulama ile bölünerek modelin farklı veri alt kümelerinde ne kadar iyi genelleştiği test edilmiştir.

Değerlendirme
Modeller şu temel metriklere göre değerlendirildi:

Ortalama Kare Hata (MSE): Tahminlerin gerçek değerlerden ne kadar sapma gösterdiğini ölçer (düşük olması daha iyidir).
R² Skoru: Hedef değişkendeki varyansın model tarafından ne kadar açıklandığını gösterir (1'e ne kadar yakınsa o kadar iyidir).
Doğruluk (Accuracy): Sınıflandırma problemleri için doğru tahmin edilen oran.
Sonuçlar
Regresyon Performansı
Eğitim Seti MSE: 2.003726e-06
Test Seti MSE: 1.994599e-06
Eğitim Seti R²: 0.999973
Test Seti R²: 0.999973
Çapraz Doğrulama MSE Skorları
Her katman için MSE: [1.994599e-06, 2.119378e-06, 1.918546e-06, 2.141710e-06, 1.855607e-06]
Tüm katmanlar için ortalama MSE: 2.005968e-06
Sınıflandırma Performansı
Eğitim Seti Doğruluğu: 1.0
Test Seti Doğruluğu: 0.9973
İlk 10 Tahmin vs Gerçek Değerler:
Tahminler: [0.08851209, 0.94206707, 0.08698868, 0.5367584, 0.04672829, 0.05834579, 0.38895936, 0.46789159, 0.08281189, 0.07963987]
Gerçek Değerler: [0.08836764, 0.94320158, 0.0873011, 0.53615197, 0.04660288, 0.05839404, 0.38847885, 0.46812129, 0.0823394, 0.07981842]

Sınıflandırma Raporu (Test Seti)
              Kesinlik (Precision)    Geri Çağırma (Recall)   F1-Skoru   Destek (Support)

           0            1.00               1.00              1.00       3881
           1            1.00               1.00              1.00       3871
           2            1.00               1.00              1.00       3939

    Doğruluk                                 1.00              11691
   Makro Ortalama       1.00               1.00              1.00       11691
Ağırlıklı Ortalama      1.00               1.00              1.00       11691

Kümeleme (Clustering)
Küme Sayıları:
Küme 0: 29,195
Küme 1: 18,248
Küme 2: 11,011


Kaggle: https://www.kaggle.com/code/muhammedisik/bitcoin-closing-price-prediction
