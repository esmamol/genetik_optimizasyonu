# BLG-307 Yapay Zeka Sistemleri – 1. Proje Ödevi

## Genetik Algoritma ile Kargo Kutusu Optimizasyonu

**Öğrenci:** Esma Mol  
**Okul Numarası:** 2312721016  
**Senaryo:** 6 – Kargo Kutusu Tasarımı  
**Ders:** BLG307 – Yapay Zeka Sistemleri  
**Yöntem:** Genetik Algoritma (GA)

---
# Genetik Algoritma ile Kargo Kutusu Optimizasyonu (Senaryo 6)

Bu proje, **BLG307 Yapay Zeka Sistemleri** dersi kapsamında verilen ödev için geliştirilmiştir.  
Amaç, bir e-ticaret firması için en uygun kargo kutusu ölçülerini  
(**genişlik x₁** ve **yükseklik x₂**) **Genetik Algoritma (GA)** kullanarak optimize etmektir.

---

## 📌 Projenin Amacı

Optimizasyon problemi aşağıdaki amaç fonksiyonu ile tanımlanmıştır:

\[
y = x_1 \cdot x_2 - 0.1x_1^2 - 0.1x_2^2
\]

Bu fonksiyon:
- \(x_1 \cdot x_2\) terimi ile **kutunun hacmini artırmayı**,  
- \(-0.1x_1^2\) ve \(-0.1x_2^2\) terimleri ile **aşırı büyük boyutların maliyetini cezalandırmayı** amaçlamaktadır.

Temel hedef, aşağıdaki kısıtlar altında amaç fonksiyonunu **maksimize eden**
\(x_1\) ve \(x_2\) değerlerini bulmaktır.

---

## 🔒 Kısıtlar

- **Minimum genişlik kısıtı:**
\[
x_1 \ge 15
\]

- **Raf hacmi kısıtı:**
\[
x_1 \cdot x_2 \le 600
\]

---

## 📐 Değişken Aralıkları

- \(x_1 \in [15, 40]\)  
- \(x_2 \in [5, 20]\)

---

## ⚙️ Kullanılan Yöntem: Genetik Algoritma (GA)

Bu projede sürekli değişkenli ve kısıtlı bir optimizasyon problemi  
**Genetik Algoritma** kullanılarak çözülmüştür.

Kullanılan GA bileşenleri aşağıda özetlenmiştir:

- **Popülasyon Oluşturma:**  
  \(x_1\) ve \(x_2\) değerleri tanımlı aralıklarda rastgele seçilerek başlangıç popülasyonu oluşturulmuştur.

- **Fitness Fonksiyonu:**  
  Amaç fonksiyonu doğrudan fitness değeri olarak kullanılmış,  
  kısıt ihlali durumunda ceza (penalty) yöntemi uygulanmıştır.

- **Seçilim (Selection):**  
  **Rank-based selection** yöntemi kullanılmıştır.  
  Bu yöntem, bireyleri mutlak fitness değerlerine göre değil,  
  fitness sıralamalarına göre seçerek genetik çeşitliliği korumayı amaçlar.

- **Çaprazlama (Crossover):**  
  Birey yapısı iki genli olduğu için **tek noktalı çaprazlama** uygulanmıştır.  
  Çaprazlama işlemi %80 olasılıkla gerçekleştirilmiştir.

- **Mutasyon (Mutation):**  
  Düşük olasılıkla genlerde küçük rastgele değişiklikler yapılmış,  
  böylece yerel optimumlara erken sıkışma önlenmiştir.

- **Jenerasyon Döngüsü:**  
  Algoritma **150 jenerasyon** boyunca çalıştırılmış ve her jenerasyonda
  elde edilen en iyi birey takip edilmiştir.

- **Görselleştirme:**  
  En iyi fitness değerlerinin jenerasyonlara göre değişimi grafikle gösterilmiştir.

---

## ▶️ Çalıştırma Adımları

Bu proje **Google Colab** ortamında çalıştırılmak üzere tasarlanmıştır.

### 1. Notebook Dosyasını Açın
- `.ipynb` dosyasını Google Colab’e yükleyin  
  veya GitHub deposu üzerinden doğrudan açın.

### 2. Hücreleri Sırayla Çalıştırın

### 3. Sonuçları İnceleyin

---

## 🛠️ Kurulum Yönergeleri

Bu proje Google Colab üzerinde çalışmak üzere tasarlanmıştır  
ve **ek bir kurulum gerektirmez**.

Projeyi yerel bir bilgisayarda çalıştırmak isteyen kullanıcılar için
gerekli kütüphaneler aşağıda verilmiştir:

```bash
pip install numpy
pip install matplotlib
