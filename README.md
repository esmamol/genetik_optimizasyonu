# BLG-307 Yapay Zeka Sistemleri – 1. Proje Ödevi

## Genetik Algoritma ile Kargo Kutusu Optimizasyonu

**Ad Soyad:** Esma Mol  
**Okul Numarası:** 2312721016  
**Senaryo:** 6 – Kargo Kutusu Tasarımı  
**Ders:** BLG307 – Yapay Zeka Sistemleri  
**Yöntem:** Genetik Algoritma (GA)

---

## 📌 Proje Tanımı

Bu proje, **BLG307 Yapay Zeka Sistemleri** dersi kapsamında verilen ödev için geliştirilmiştir.  
Amaç, bir e-ticaret firması için en uygun kargo kutusu ölçülerini  
(**genişlik (x1)** ve **yükseklik (x2)**) **Genetik Algoritma (GA)** kullanarak optimize etmektir.

Problem, sürekli değişkenli ve kısıtlı bir optimizasyon problemi olup,
klasik yöntemlerle çözümü zor olduğundan sezgisel bir yaklaşım olan
Genetik Algoritma tercih edilmiştir.

---

## 🎯 Projenin Amacı

Optimizasyon problemi aşağıdaki amaç fonksiyonu ile tanımlanmıştır:

y = x1 * x2 - 0.1 * x1^2 - 0.1 * x2^2

Bu fonksiyon:
- "x1 * x2" terimi ile **kutunun hacmini artırmayı**,  
- "- 0.1 * x1^2 - 0.1 * x2^2" terimleri ile **aşırı büyük boyutların maliyetini cezalandırmayı** amaçlamaktadır.

Temel hedef, aşağıdaki kısıtlar altında amaç fonksiyonunu **maksimize eden**
x1 ve x2 değerlerini bulmaktır.

---

## 🔒 Kısıtlar

- **Minimum genişlik kısıtı:**
x1 >= 15

- **Raf hacmi kısıtı:**
x1 * x2 <= 600

---

## 📐 Değişken Aralıkları

- **Genişlik (x1):** 15 – 40  
- **Yükseklik (x2):** 5 – 20  

---

## ⚙️ Kullanılan Yöntem: Genetik Algoritma (GA)

Bu projede kısıtlı ve sürekli optimizasyon problemi,
**Genetik Algoritma** kullanılarak çözülmüştür.

Kullanılan temel GA bileşenleri aşağıda özetlenmiştir:

- **Popülasyon Oluşturma:**  
  x1 ve x2 değerleri tanımlı aralıklarda rastgele seçilerek
  başlangıç popülasyonu oluşturulmuştur.

- **Fitness Fonksiyonu:**  
  Amaç fonksiyonu doğrudan fitness değeri olarak kullanılmış,
  kısıt ihlali durumunda **ceza (penalty) yöntemi** uygulanmıştır.

- **Seçilim (Selection):**  
  **Rank-based selection** yöntemi kullanılmıştır.  
  Bu yöntemde bireyler mutlak fitness değerlerine göre değil,
  fitness sıralamalarına göre seçilir.  
  Böylece erken yakınsama (premature convergence) azaltılarak
  genetik çeşitlilik korunmuştur.

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
Algoritma çalıştırıldığında optimum çözüm değerleri ve
fitness evrim grafiği elde edilir.

---

## 📊 Sonuçlar ve Analiz

Genetik Algoritma çalıştırıldığında aşağıdaki optimum değerler elde edilmiştir:

- Optimum genişlik (x1) ≈ **29.93**
- Optimum yükseklik (x2) = **20**
- Amaç fonksiyonu (fitness) değeri ≈ **469.01**

### 🔍 Kısıt Kontrolü

\[
x1*x2 = 29.93 \times 20 = 598.6 <= 600
\]

Bu sonuç, elde edilen çözümün **raf hacmi kısıtını sağladığını**
ve aynı zamanda x1>=15 koşulunun da karşılandığını göstermektedir.

### 📈 Yorum

Fitness evrim grafiği incelendiğinde, algoritmanın jenerasyonlar boyunca
daha iyi çözümlere yakınsadığı görülmektedir.  
Bu durum, kullanılan **rank-based selection** yönteminin ve
genetik algoritma parametrelerinin problemi çözmede etkili olduğunu göstermektedir.

---

## 🛠️ Kurulum Yönergeleri

Bu proje Google Colab üzerinde çalışmak üzere tasarlanmıştır  
ve **ek bir kurulum gerektirmez**.

Projeyi yerel bir bilgisayarda çalıştırmak isteyen kullanıcılar için
gerekli kütüphaneler aşağıda verilmiştir:

```bash
pip install numpy
pip install matplotlib
