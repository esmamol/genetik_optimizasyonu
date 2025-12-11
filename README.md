# Genetik Algoritma ile Kargo Kutusu Optimizasyonu (Senaryo 6)

Bu proje, BLG307 Yapay Zeka Sistemleri dersi kapsamında verilen ödev için geliştirilmiştir. 
Amaç, bir e-ticaret firması için en uygun kargo kutusu ölçülerini (genişlik x₁ ve yükseklik x₂) 
Genetik Algoritma (GA) kullanarak optimize etmektir.

---

## 📌 Projenin Amacı

Optimizasyon yapılacak amaç fonksiyonu:

\[
y = x_1 \cdot x_2 - 0.1x_1^2 - 0.1x_2^2
\]

Bu fonksiyon kutunun **hacmini artırırken**, çok büyük kutuların **maliyetini cezalandırır**.  
Amaç, kısıtlar altında **maksimum** değeri veren x₁ ve x₂'yi bulmaktır.

### Kısıtlar:
- Minimum genişlik:  
  \[
  x_1 \ge 15
  \]
- Raf hacmi sınırı:  
  \[
  x_1 \cdot x_2 \le 600
  \]

### Değişken Aralıkları:
- x₁ ∈ [15, 40]  
- x₂ ∈ [5, 20]

Proje, bu optimizasyon problemini çözmek için **Genetik Algoritma** kullanır.

---

## ⚙️ Kullanılan Yöntem: Genetik Algoritma (GA)

Projede kullanılan Genetik Algoritma bileşenleri:

- **Popülasyon Oluşturma:**  
  Rastgele x₁ ve x₂ değerlerinden başlangıç popülasyonu üretilir.

- **Fitness Fonksiyonu:**  
  Amaç fonksiyonu + kısıt kontrolü.

- **Seçilim (Selection):**  
  Turnuva seçimi (tournament selection).

- **Çaprazlama (Crossover):**  
  %80 olasılıkla uygulanır; x₁ ve x₂ ebeveynlerden alınarak yeni birey oluşturulur.

- **Mutasyon (Mutation):**  
  Değerler küçük rastgele değişimlerle güncellenir.

- **Jenerasyon Döngüsü:**  
  150 jenerasyon boyunca çalıştırılarak en iyi birey takip edilir.

- **Görselleştirme:**  
  Fitness değerinin gelişimi grafikle gösterilir.

---

## ▶️ Çalıştırma Adımları

Aşağıdaki adımlar Google Colab üzerinde çalışmak içindir.

### **1. Colab’de .ipynb dosyasını açın**
- Dosyayı yükleyin veya GitHub üzerinden açın.

### **2. Tüm hücreleri sırayla çalıştırın**
- Hücreler şu sırayı içerir:
  1. Projenin açıklaması ve amaç
  2. Kütüphanelerin import edilmesi
  3. Amaç fonksiyonu ve kısıtların tanımlanması
  4. Popülasyon oluşturma
  5. Seçilim, çaprazlama, mutasyon fonksiyonları
  6. Genetik Algoritma döngüsü
  7. En iyi çözüm çıktısı
  8. Fitness grafiği
  9. Sonuç yorumları

### **3. Sonuçları inceleyin**
Algoritma çalıştığında şu bilgiler Colab çıktısında görünecektir:

- Optimum genişlik (x₁)
- Optimum yükseklik (x₂)
- Amaç fonksiyonu değeri
- Fitness evrim grafiği

---

## 🛠️ Kurulum Yönergeleri

Bu proje Google Colab üzerinde çalışmak üzere tasarlanmıştır.  
Herhangi bir ek kurulum gerektirmez.

Eğer projeyi kendi bilgisayarınızda çalıştırmak isterseniz:

### Gereken Kütüphaneler:
```bash
pip install numpy
pip install matplotlib
