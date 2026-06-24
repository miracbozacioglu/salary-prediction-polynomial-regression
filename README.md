<h1 align="center"> Polinom Regresyon — Maaş Tahmini</h1>

<p align="center">
  <i>Doğrusal olmayan bir Polinom Regresyon modeli ile çalışanların unvan seviyesine göre maaşlarını tahmin etme.</i>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.9+-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white" alt="Jupyter" />
  <img src="https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="scikit-learn" />
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas" />
  <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy" />
  <img src="https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=matplotlib&logoColor=white" alt="Matplotlib" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Lisans-MIT-green?style=flat-square" alt="Lisans" />
  <img src="https://img.shields.io/badge/Durum-Tamamland%C4%B1-success?style=flat-square" alt="Durum" />
  <img src="https://img.shields.io/badge/Model-Polinom%20Regresyon-blueviolet?style=flat-square" alt="Model" />
</p>

---

## 🎯 Proje Hakkında

> **Amaç:** Bir çalışanın **unvan seviyesine** dayanarak alması gereken **maaşı** tahmin eden, bu iki değişken arasındaki *doğrusal olmayan* ilişkiyi yakalayan bir model geliştirmek.

Gerçek dünyadaki maaş verilerinde, kıdem arttıkça maaş nadiren doğrusal bir şekilde artar — genellikle üst seviyelerde **ivmelenerek** yükselir. Basit bir **Doğrusal Regresyon (Linear Regression)** modeli bu eğriselliği yakalayamaz ve büyük tahmin hatalarına yol açar.

Bu proje, neden **Polinom Regresyonun** doğru araç olduğunu göstermektedir:

- 🔹 Doğrusal Regresyonu, **yüksek dereceli özellikler** (`Seviye²`, `Seviye³`, …) ekleyerek genişletir.
- 🔹 Bu sayede model, verideki eğrisel trende **uyum sağlayacak şekilde bükülebilir**.
- 🔹 Farkı net bir şekilde ortaya koymak için Doğrusal ve Polinom uyumlarını **görsel olarak karşılaştırırız**.

Notebook, sürecin tamamını adım adım gösterir: verinin yüklenmesi, her iki modelin eğitilmesi, karar eğrilerinin yan yana çizdirilmesi ve yeni bir kıdem seviyesi için maaş tahmini yapılması.

---

## 📊 Veri Seti

Veri seti (`Position_Salaries.csv`), iş unvanlarını kıdem seviyeleri ve karşılık gelen maaşlarla eşleştiren **10 kayıt** içerir.

| Sütun      | Tür         | Açıklama                                                |
| :--------- | :---------- | :----------------------------------------------------- |
| `Position` | Kategorik   | İş unvanı (örn. *Business Analyst*, *Manager*).        |
| `Level`    | Sayısal     | Sayısal kıdem seviyesi (1–10).                         |
| `Salary`   | Sayısal     | Yıllık maaş (USD) — **hedef** değişken.                |

### 🔍 Özellik Seçimi Hakkında Bir Not

> **`Position`** sütunu modele **bilinçli olarak dahil edilmemiştir**.
>
> Her bir unvan, birebir bir `Level` değerine karşılık gelir — yani iki sütun da *aynı hiyerarşik bilgiyi* taşır. `Position` sütununu tutmak gereksiz tekrar (redundancy) yaratacağından, bağımsız değişken (**X**) olarak yalnızca **`Level`** kullanılmış, bağımlı değişken (**y**) ise **`Salary`** olarak belirlenmiştir.

#### Veriden bir örnek:

| Position           | Level | Salary    |
| :----------------- | :---: | --------: |
| Business Analyst   |   1   |   45,000  |
| Senior Consultant  |   3   |   60,000  |
| Region Manager     |   6   |  150,000  |
| Senior Partner     |   8   |  300,000  |
| CEO                |  10   | 1,000,000 |

---

## 🛠️ Kullanılan Teknolojiler

| Kütüphane          | Projedeki Rolü                                          |
| :----------------- | :------------------------------------------------------ |
| 🐍 **Python**      | Ana programlama dili.                                   |
| 🐼 **Pandas**      | Veri setinin yüklenmesi ve işlenmesi.                  |
| 🔢 **NumPy**       | Sayısal işlemler ve dizi (array) manipülasyonu.        |
| 📉 **Matplotlib**  | Doğrusal ve Polinom regresyon eğrilerinin görselleştirilmesi. |
| 🤖 **Scikit-Learn**| Regresyon modellerinin kurulması (`LinearRegression`, `PolynomialFeatures`). |

---

## 🚀 Nasıl Çalıştırılır?

Projeyi yerel makinenizde çalıştırmak için aşağıdaki adımları izleyin.

**1. Depoyu klonlayın**

```bash
git clone https://github.com/<kullanici-adiniz>/polynomial_regression.git
cd polynomial_regression
```

**2. (Önerilir) Bir sanal ortam oluşturup etkinleştirin**

```bash
# Ortamı oluşturun
python -m venv venv

# Etkinleştirin (Windows)
venv\Scripts\activate

# Etkinleştirin (macOS / Linux)
source venv/bin/activate
```

**3. Gerekli bağımlılıkları kurun**

```bash
pip install numpy pandas matplotlib scikit-learn jupyter
```

**4. Notebook'u başlatın**

```bash
jupyter notebook polynomial_regression.ipynb
```

> 💡 Veri yükleme, model eğitimi, görselleştirmeler ve nihai maaş tahminini yeniden üretmek için hücreleri yukarıdan aşağıya doğru çalıştırın.

---

## ✅ Sonuç

> **Polinom Regresyon, bu doğrusal olmayan veri setinde Doğrusal Regresyonu açık ara geride bırakmaktadır.**

Görsel karşılaştırma her şeyi anlatıyor:

- 📏 **Doğrusal** model, veriyi kötü bir şekilde uyumsuzlaştıran (under-fit) tek bir düz çizgi çizer — düşük seviyeleri olduğundan fazla, yüksek seviyeleri ise ciddi şekilde eksik tahmin eder.
- 🎯 **Polinom** model ise veri noktaları boyunca pürüzsüzce bükülerek, üst seviyelerdeki dik maaş artışını yüksek doğrulukla takip eder.

Bu proje, temel bir makine öğrenmesi prensibinin pratik bir hatırlatıcısıdır: **model, verinin şekline uymalıdır.** Altta yatan ilişki eğrisel olduğunda, polinom özellikleri eklemek çok daha doğru bir uyum elde etmenin basit ama güçlü bir yoludur. 🚀

---

<p align="center">
  <i>⭐ Bu projeyi faydalı bulduysanız, bir yıldız vermeyi düşünebilirsiniz!</i>
</p>
