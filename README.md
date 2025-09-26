# 🐶🐱 Cats vs Dogs Classifier (CNN)

Bu repo, **Akbank Derin Öğrenme Bootcamp** kapsamında geliştirilmiş bir derin öğrenme projesini içermektedir.  
Projenin amacı, **kedi ve köpek resimlerini ayırt edebilen** bir **Convolutional Neural Network (CNN)** modeli geliştirmektir.  

---

## 📌 İçindekiler
- [🎯 Projenin Amacı](#-projenin-amacı)
- [📂 Veri Seti](#-veri-seti)
- [📚 Kullanılan Kütüphaneler](#-kullanılan-kütüphaneler)
- [⚙️ Metodoloji](#️-metodoloji)
- [🏗️ Model Mimarisi](#️-model-mimarisi)
- [📊 Sonuçlar](#-sonuçlar)
- [🚀 Çalıştırma](#-çalıştırma)
- [🔮 Gelecek Çalışmalar](#-gelecek-çalışmalar)
- [✍️ Kaggle ](#️-Kaggle)

---

## 🎯 Projenin Amacı
Bu projenin hedefi, **Dogs vs Cats** veri seti üzerinde CNN kullanarak ikili sınıflandırma problemi çözmektir.  
Model, bir görüntünün **kedi mi yoksa köpek mi** olduğunu tahmin etmeyi öğrenir.  

---

## 📂 Veri Seti
- **Kaynak:** [Kaggle Dogs vs Cats Dataset](https://www.kaggle.com/c/dogs-vs-cats)  
- **Toplam Görüntü:** 25.000  
- **Sınıf Dağılımı:** 12.500 kedi 🐱, 12.500 köpek 🐶  
- **Bölünme:**
  - %80 Eğitim (20.000 resim)  
  - %20 Doğrulama (5.000 resim)  

---

## 📚 Kullanılan Kütüphaneler
- **Veri İşleme:** `numpy`, `pandas`, `os`, `zipfile`  
- **Görselleştirme:** `matplotlib`, `seaborn`  
- **Derin Öğrenme:** `tensorflow`, `keras`  
- **Model Değerlendirme:** `scikit-learn`  

---

## ⚙️ Metodoloji
- **Veri Önişleme**
  - Etiketleme & DataFrame oluşturma
  - Eğitim / doğrulama split (%80 - %20)
  - Data Augmentation (rotation, shift, shear, zoom, flip)

- **Model Eğitimi**
  - CNN tabanlı model (Conv2D, MaxPooling, Dense, Dropout)
  - Aktivasyon fonksiyonları: ReLU & Sigmoid
  - Optimizer: Adam
  - Loss: Binary Crossentropy
  - Eğitim süresi: 15 epoch  

- **Değerlendirme**
  - Accuracy & Loss grafikleri  
  - Confusion Matrix & Classification Report  

---

## 🏗️ Model Mimarisi
```text
Conv2D(32, (3x3)) + MaxPooling2D
Conv2D(64, (3x3)) + MaxPooling2D
Conv2D(128, (3x3)) + MaxPooling2D
Flatten
Dense(512, activation='relu')
Dropout(0.5)
Dense(1, activation='sigmoid')
```
---

## 📊 Sonuçlar

### 📈 Eğitim / Doğrulama Başarımları
Eğitim süresince modelin doğruluk ve kayıp değerlerinin değişimi aşağıdaki grafikte gösterilmiştir:

<img width="990" height="528" alt="egitim_dogrulama" src="https://github.com/user-attachments/assets/488cf9c9-6e0a-449e-a243-b46adb7a3944" />


---

### 🌀 Confusion Matrix
Doğrulama seti üzerinde elde edilen karmaşıklık matrisi:

<img width="548" height="432" alt="karmasıklık_matrisi" src="https://github.com/user-attachments/assets/6db2fb51-b3d5-40ff-b005-c32426a878f4" />


Bu görsel, modelin hangi sınıfta daha fazla hata yaptığını ve doğru sınıflandırmaları göstermektedir.  

---

### 📝 Classification Report
Doğrulama seti için elde edilen sınıflandırma raporu:  

```text

              precision    recall  f1-score   support

         Cat       0.51      0.43      0.47      2548
         Dog       0.49      0.57      0.53      2452

    accuracy                           0.50      5000
   macro avg       0.50      0.50      0.50      5000
weighted avg       0.50      0.50      0.50      5000
 
```
---

## 🚀 Çalıştırma
Projeyi çalıştırmak için:
1. Kaggle üzerinde **Dogs vs Cats** datasetini projenize ekleyin.
2. Notebook’u açıp baştan sona çalıştırın.
3. Eğitim sonrası modeli `.h5` formatında kaydedebilirsiniz:

```python

 model.save('cat_dog_classifier.h5')

```
---

## 🔮 Gelecek Çalışmalar

* 🔥 Grad-CAM / Eigen-CAM ile modelin karar verdiği bölgelerin görselleştirilmesi
* 🧠 Transfer Learning (VGG16, ResNet50 vb. gibi önceden eğitilmiş modelleri kullanma)

---

## ✍️ kaggle
https://www.kaggle.com/code/balciemirhan/dogs-vs-cats-classification
