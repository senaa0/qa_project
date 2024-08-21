# Web Trafik Loglarına Dayalı Yapay Zeka Destekli Soru-Cevap Sistemi

## 1. Giriş

Bu proje, web trafik loglarına dayalı bir yapay zeka destekli soru-cevap(Q&A) sistemi geliştirmeyi amaçladım. Sistem, kullanıcıların doğal dilde sordukları sorulara, web trafik loglarından elde edilen verilerle yanıtlar üretmekte olmaktadır.

## 2. Proje Adımları

### 2.1. Web Trafik Loglarının Üretilmesi

İlk olarak rastgele web trafik logları üreten bir script geliştirmekle başlatıldı. Bu loglar, IP adresleri, zaman damgaları, HTTP istekleri, yanıt kodları ve kullanıcı ajanları gibi bilgileri içermektedir. Veriler JSON formatında saklandı ve modelin eğitiminde kullanıldı.

### 2.2. Veri Kümesinin Oluşturulması ve İşlenmesi

Elde edilen log verileri, modelin eğitimi için uygun bir veri kümesine dönüştürüldü. Bu süreçte `request` ve `url` alanları kullanıldı. Veriler, eğitim ve değerlendirme veri kümelerine ayrıldı ve gerekli ön işleme adımı gerçekleştirildi.

### 2.3. Model Eğitim ve Kaydetme

Soru-cevap sistemi için T5 modeli eğitilmesine karar verdim. Eğitim sürecinde model, önceden işlenmiş eğitim ve değerlendirme veri kümeleri ile eğitildi. Eğitim tamamlandıktan sonra, modelin performans değerlendirmesi yapıldı ve sonuçlar bir dosyaya kaydedildi. Model ve tokenizer, sonradan kullanılmak üzere saklandı.

### 2.4. Soru-Cevap İşlemi

Eğitilmiş model kullanılarak, kullanıcıların doğal dilde sordukları sorulara yanıt üretme işlevi geliştirildi. Bu işlev, en yakın web trafik loglarını bulur ve yanıt üretir. Soru-cevap işlemi için gerekli olan log vektörleri ve sorgu vektörleri hesaplanarak model aracılığıyla yanıtlar elde edildi.

## 3. Karşılaşılan Zorluklar

- **Veri Üretimi:** Web trafik loglarının rastgele üretilmesi sırasında veri formatı ve tutarlılık sorunları yaşandı. Log verilerinin kalitesini ve çeşitliliğini artırmak için çeşitli düzenlemeler yapıldı.
  
- **Model Eğitimi:** Modelin eğitim süreci uzun sürdü ve hiperparametrelerin ayarlanması zor oldu. Eğitim verisinin boyutu ve kalitesi, modelin performansını etkiledi.

- **Soru-Cevap İşlemi:** Soru-cevap sisteminin doğruluğu, kullanılan log verisinin kalitesine ve sorgu vektörlerinin doğruluğuna bağlı olarak değişti. Bu nedenle, modelin çıktıları her zaman tatmin edici sonuçlar elde edilemedi.

## 4. Performans Değerlendirmesi

Modelin performansı, eğitim ve değerlendirme aşamalarında yapılan ölçümlerle değerlendirildi. Eğitim sürecinde, modelin doğruluk oranı, kayıp fonksiyonu ve diğer metrikler takip edildi. Eğitim sonuçları, modelin web trafik loglarından elde edilen bilgileri ne kadar iyi öğrendiğini ve soru-cevap işlemini ne kadar etkili gerçekleştirdiğini göstermektedir.

- **Eğitim Sonuçları:** Modelin eğitimi tamamlandıktan sonra elde edilen sonuçlar değerlendirildi ve performans metrikleri (doğruluk, kayıp vb.) bir dosyada(evaluation_results.txt) özetlendi.
- **Soru-Cevap Performansı:** Soru-cevap işlevi test edilerek çeşitli sorgulara verilen yanıtların doğruluğu ve yeterliliği değerlendirildi. Sonuçlar, sistemin pratikte ne kadar etkili olduğunu gösterir.

## 5. Sonuç ve Gelecek Çalışmalar

Bu proje, web trafik loglarına dayalı bir yapay zeka destekli soru-cevap sisteminin başarılı bir şekilde geliştirilmesini ve uygulanmasını gerçekleştirildi. Gelecek çalışmalarda, modelin doğruluğunu artırmak için daha kapsamlı veri kümesi kullanımı ve hiperparametre optimizasyonu yapılabilir. Ayrıca, sistemin çeşitli kullanım senaryolarında performansının daha detaylı incelenmesi faydalı olacaktır.

