# Plant-Pathology-Selin-Repo

# 🌿 Plant Pathology – Yaprak Hastalıkları Sınıflandırma Projesi

# Giriş

Bu proje, Global AI Hub Derin Öğrenme Bootcamp kapsamında geliştirilmiştir.
Kullanılan veri seti: Plant Pathology 2020 – FGVC7 (Kaggle yarışma veri seti)

Amaç:

Bitki yapraklarının görüntülerinden hastalık türlerini otomatik olarak sınıflandırmak. Hastalık teşhisinde yapay zekâ tabanlı bir çözüm önermektir.

Veri setinde yer alan sınıflar:

. healthy (sağlıklı yaprak)

. multiple_diseases (birden fazla hastalık)

. rust (pas hastalığı)

. scab (kabuk hastalığı)

# Yöntemler

Projenin temel adımları:

Veri Yükleme ve İnceleme

train.csv dosyası ile görüntü-id ve etiketler incelendi.

Eksik olan label sütunu one-hot formatından yeniden oluşturuldu.

Görsellerden örnekler görselleştirildi.

Veri Ön İşleme

Eğitim/Doğrulama ayrımı (%80 / %20 stratify ile).

ImageDataGenerator ile veri artırma (rotation, shift, zoom, flip).

Görsellerin normalizasyonu (0–1 aralığı).

Model Kurulumu

Basit bir CNN modeli oluşturuldu:

3 adet Conv2D + MaxPooling bloğu

Flatten + Dense katmanları

Dropout (overfitting önlemek için)

Aktivasyon fonksiyonu: ReLU (gizli katmanlarda), Softmax (çıktı katmanında).

Optimizasyon: Adam

Loss: Categorical Crossentropy

Eğitim

Başlangıç için 5 epoch deneme yapıldı.

Sonrasında 20 epoch ile doğrulama metrikleri takip edilebilir.

Değerlendirme

Accuracy ve Loss grafiklerinin çizimi

Confusion Matrix ile sınıflar arası performans

Classification Report (Precision, Recall, F1-score)

Modelin Açıklanabilirliği

Grad-CAM yöntemi ile modelin tahmin sırasında yaprak üzerinde odaklandığı bölgeler görselleştirildi.

# Sonuçlar

Eğitim ve doğrulama doğrulukları % 80 seviyesine ulaşmıştır.

Confusion Matrix ve classification raporu, modelin bazı sınıflarda yüksek başarı gösterdiğini, bazı benzer sınıflarda ise hatalar yaptığını göstermiştir.

Grad-CAM çıktıları, modelin yaprağın hastalık görülen bölgelerine odaklandığını göstermiştir.

# Çıktılar

Model, .h5 formatında kaydedilmiştir:

plant_disease_model.h5


Daha sonra bu model yüklenerek yeni yaprak görüntülerinde tahmin yapılabilir.

# Gelecek Çalışmalar

Bu proje, temel bir CNN modeli ile hastalık sınıflandırmasının mümkün olduğunu göstermektedir.
Gelecek geliştirmeler:

Transfer Learning (EfficientNet, ResNet gibi hazır modellerle daha yüksek doğruluk)

Daha fazla data augmentation eklemek

Modeli mobil/web uygulaması olarak deploy etmek (ör. Streamlit, Flask)

Gerçek zamanlı görüntü tanıma için kamera entegrasyonu

# Linkler

Kaggle Notebook: https://www.kaggle.com/code/enesgleryz/plant-pathology-selin
