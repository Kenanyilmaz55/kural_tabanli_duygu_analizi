# Türkçe Cümle Duygu Analizi (Sentiment Analysis) - Zemberek ile

Bu proje, Türkçe metinlerdeki **duygu durumunu (pozitif/negatif)** analiz etmek için Zemberek doğal dil işleme kütüphanesini kullanan bir Python uygulamasıdır. Projede özel olarak hazırlanan pozitif ve negatif kelime listeleri, köklerine indirgenerek duygu tespiti yapılır.

---

##  Özellikler

- Zemberek ile kök bazlı Türkçe metin analizi
- Cümle düzeyinde pozitif/negatif duygu sınıflandırması
- Yüklem analizi (Negatiflik içerme durumu)
- Excel'den alınan test verileriyle model değerlendirme
- Doğruluk, Kesinlik, Anma ve F1-Skor hesaplama
- Matplotlib ile görselleştirme
- Hatalı tahminlerin detaylı listesi

---

##  Proje Yapısı

```bash
.
├── main.py                     # Ana çalıştırma dosyası
├── data_preprocessing.py      # Veri temizleme ve kök çıkarımı
├── sentiment_analysis.py      # Duygu analizi ve model değerlendirme
├── visualization.py           # Performans görselleştirmeleri
├── constants.py               # Zemberek .jar yolu gibi sabitler
├── pozitif_kelimeler.txt         # Pozitif kelimeler listesi
├── negatif_kelimeler.txt         # Negatif kelimeler listesi
├── esit_verilen.xlsx          # Etiketli test verileri
└── README.md                  # Proje açıklaması (bu dosya)
```

---

##  Kurulum

### 1. Python Bağımlılıkları

Aşağıdaki kütüphaneleri yüklemeniz gerekir:

```bash
pip install pandas matplotlib scikit-learn jpype1 zemberek-python
```

### 2. Zemberek Kurulumu

- [Zemberek NLP](https://github.com/ahmetaa/zemberek-nlp) Java tabanlıdır. `.jar` dosyasını indirmeniz ve yolunu `constants.py` dosyasındaki `ZEMBEREK_PATH` değişkenine girmeniz gerekir.

```python
# constants.py
ZEMBEREK_PATH = "C:/Users/kullanıcı_adı/Desktop/zemberek-full.jar"
```

---

##  Kullanım

Terminalde aşağıdaki komutla çalıştırılır:

```bash
python main.py
```

### Ardından:
- Sistem sizden analiz etmek istediğiniz cümleyi isteyecek.
- `q` yazarak çıkabilirsiniz.
- Cümle analizi yapıldıktan sonra:
  - Tahmin edilen duygu (pozitif/negatif)
  - Güven skoru
  - Yüklem kökü ve olumsuzluk durumu
  - Kullanılan pozitif/negatif kökler yazdırılır.

### Model Değerlendirme:
- `esit_verilen.xlsx` dosyasındaki test cümleleri üzerinde:
  - Doğruluk
  - Kesinlik
  - Anma
  - F1 Skoru
  - Hatalı tahmin listesi
  - Performans grafiği

