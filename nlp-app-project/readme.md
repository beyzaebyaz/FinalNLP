# NLP Metin Benzerliği Projesi

Bu proje, doğal dil işleme teknikleri kullanarak metin benzerliklerini hesaplayan ve karşılaştıran bir çalışmadır.

## Proje Yapısı

```
├── reviews.csv                         # Ham veri seti
├── reviews_cleaned_ultimate.csv        # Temizlenmiş veri
├── reviews_lemmatized.csv             # Lemmatize edilmiş veri
├── reviews_stemmed.csv                # Stemming uygulanmış veri
├── generate_tfidf_vectors.ipynb       # TF-IDF vektörlerini oluşturan notebook
├── train_word2vec_models.ipynb        # Word2Vec modellerini eğiten notebook
├── task-2.ipynb                       # Benzerlik hesaplama ve değerlendirme notebook'u
├── vectors/                           # TF-IDF vektörleri ve vectorizer'lar
└── models0/                           # Eğitilmiş Word2Vec modelleri
```

## Gereksinimler

Projeyi çalıştırmak için aşağıdaki Python kütüphaneleri gereklidir:

```
pandas
numpy
scikit-learn
gensim
nltk
```

Kütüphaneleri yüklemek için:
```bash
pip install pandas numpy scikit-learn gensim nltk
```

## Çalıştırma Talimatları

1. TF-IDF Vektörlerinin Oluşturulması:
   - `generate_tfidf_vectors.ipynb` notebook'unu açın
   - Tüm hücreleri sırayla çalıştırın
   - İşlem sonunda `vectors/` klasöründe TF-IDF vektörleri oluşacaktır

2. Word2Vec Modellerinin Eğitilmesi:
   - `train_word2vec_models.ipynb` notebook'unu açın
   - Tüm hücreleri sırayla çalıştırın
   - İşlem sonunda `models0/` klasöründe 16 farklı model oluşacaktır

3. Benzerlik Hesaplamaları ve Değerlendirme:
   - `task-2.ipynb` notebook'unu açın
   - Tüm hücreleri sırayla çalıştırın
   - Örnek metin seçin
   - Her model için benzerlik sonuçlarını inceleyin
   - Jaccard benzerlik matrisini değerlendirin

## Model Yapılandırmaları

### TF-IDF Modelleri
- Lemmatized versiyon
- Stemmed versiyon

### Word2Vec Modelleri (16 farklı model)
Parametreler:
- vector_size: [100, 300]
- window: [2, 5]
- sg: [0 (CBOW), 1 (Skip-gram)]
- Hem lemmatized hem de stemmed versiyonlar

## Değerlendirme Kriterleri

1. Anlamsal Değerlendirme (1-5 puan):
   - 1: Çok alakasız, anlamca zayıf benzerlik
   - 2: Kısmen ilgili ama bağlamı tutmuyor
   - 3: Ortalama düzeyde benzer
   - 4: Anlamlı, açık benzerlik içeriyor
   - 5: Neredeyse aynı temada, çok güçlü benzerlik

2. Sıralama Tutarlılığı:
   - Jaccard benzerlik matrisi ile modeller arası tutarlılık analizi
   - Model yapılandırmalarının etkisi değerlendirmesi

## Notlar

- Veri seti içinden örnek metin seçilmelidir
- TF-IDF vektörleri oluşturulurken mevcut veri seti kullanılmalıdır
- Değerlendirme sonuçları ayrıntılı olarak raporlanmalıdır

---

## 🔍 Proje Amacı

Mobil uygulama mağazalarında yapılan kullanıcı yorumları genellikle büyük miktarda veri içerir ve manuel olarak analiz edilmesi zordur. Bu projede, kullanıcıların en çok hangi konularda şikayet ettiğini anlamak için şu adımlar uygulanmıştır:

1. **Olumsuz yorumların filtrelenmesi**
2. **Verilerin ön işlenmesi (tokenization, stopword removal, lowercasing, lemmatization, stemming)**
3. **TF-IDF ve Word2Vec modelleme yöntemleriyle metinlerin sayısal gösterimi**
4. **Word2Vec ile semantik kümelerin analizi**
5. **Zipf yasasına göre kelime sıklığı dağılımı**
6. **En çok tekrar eden şikayet başlıklarının çıkarılması**


