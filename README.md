# AkbankDerinOgrenme
# Brain Tumor MRI Classification

Bu repo, Global AI Hub bootcamplerinde **template olarak** kullanılabilir. Projede, MRI beyin görüntüleri kullanarak **beyin tümörü sınıflandırması** yapan bir CNN modeli geliştirilmiştir.  

Proje, eğitim, validation ve test süreçlerini kapsayan **end-to-end deep learning pipeline** içerir ve Kaggle üzerinde GPU kullanımıyla optimize edilmiştir.  

---

## Giriş

Bu projede kullanılan veri seti: [Brain Tumor MRI Dataset](https://www.kaggle.com/datasets/jakeshbohaju/brain-tumor-mri-dataset)

- **Sınıflar:** `glioma_tumor`, `meningioma_tumor`, `pituitary_tumor`, `no_tumor`
- **Toplam görüntü sayısı:** Yaklaşık 3000+ (Training + Testing)

Proje kapsamında:
- Custom CNN modeli geliştirilmiştir
- Veriler uygun transform ve augmentasyon ile işlenmiştir
- Model, PyTorch kullanılarak GPU üzerinde eğitilmiştir
- Eğitim ve validation sonuçları görselleştirilmiştir

---

## Teknik Anlatım

Notebook içerisinde tüm adımlar markdown hücreleri ile açıklanmıştır:

1. **Veri Ön İşleme:**  
   - Tüm görüntüler RGB formatına çevrildi  
   - Training verisi için augmentasyonlar uygulandı  
   - Validation ve test verisi normalize edildi  

2. **Train / Validation / Test Split:**  
   - Training klasörü: %70 Train, %15 Validation  
   - Testing klasörü: %15 Final Test  

3. **Model Mimarisi:**  
   - 3 Convolution + MaxPooling blokları  
   - Dropout katmanı ile regularizasyon  
   - 2 Fully Connected katmanı  
   - Aktivasyon: ReLU  
   - Loss: CrossEntropyLoss  

4. **Eğitim:**  
   - Optimizer: Adam (lr=1e-4)  
   - Epoch sayısı ve batch size parametre olarak değiştirilebilir  
   - GPU kullanımı aktif  

5. **Değerlendirme:**  
   - Train/Validation Loss ve Accuracy grafikleri  
   - Confusion Matrix ve Classification Report

---

## Eğitim ve Hiperparametre Seçimi

Model eğitimi sırasında **batch size** ve **epoch sayısı** farklı kombinasyonlarda denenmiştir.  

- Deneme süreci:  
  - Batch size: 16, 32, 64  
  - Epoch sayısı: 15, 25  
- Her kombinasyon için **validation accuracy** ölçülmüş ve en iyi sonuç veren kombinasyon seçilmiştir.  

> Örnek: Batch size=16 ve Epoch=25 en iyi validation performansını sağladı.  

Bu sayede modelin overfitting yapmadan optimum öğrenme hızında eğitilmesi sağlanmıştır.

---

## Metrikler

- Validation Accuracy: ~%75 (en iyi model)
- Test Accuracy: ~%90  
- Confusion Matrix ve Classification Report ile sınıf bazlı performans değerlendirildi  
- Modelin genel başarısı tümör sınıflarını doğru şekilde ayırabilmektedir  

> Not: Kesin değerler notebook çalıştırıldığında elde edilecektir.

---

## Ekler

- `UI/` klasörü: Streamlit veya başka arayüz ile deploy için örnek scriptler  
- GPU optimizasyonu: Automatic Mixed Precision (AMP) opsiyonel olarak eklenebilir  
- Denormalize ve görselleştirme fonksiyonları eğitim sonrası analiz için kullanılabilir

---

## Sonuç ve Gelecek Çalışmalar

- Mevcut model, beyin tümörü sınıflandırması için temel bir pipeline sağlar  
- Gelecek geliştirmeler:  
  - Transfer learning veya pre-trained modellerin kullanımı  
  - Daha büyük veri seti ile performans artışı  
  - Deployment ve gerçek zamanlı tahmin arayüzü  
  - Dinamik veri toplama ve veri artırma stratejileri

Bu proje, bootcamp sonrasında geliştirilmeye devam edebilir ve farklı modeller ile test edilebilir.



## Linkler
[https://www.kaggle.com/code/ulassen/akbankderin-renme?scriptVersionId=264160091](https://www.kaggle.com/code/ulassen/akbankderin-renme)
