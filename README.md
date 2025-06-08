# İçerik Tabanlı Film Öneri Sistemi

Bu projede, içerik tabanlı filtreleme (content-based filtering) yaklaşımıyla film öneri sistemi geliştirilmiştir. Film açıklamaları ve tür bilgileri temel alınarak benzer filmleri öneren bir yapı kurulmuştur. Proje aynı zamanda film endüstrisine dair bazı keşifsel analizler de içermektedir.

## Veri Seti

Kaynak: [Kaggle](https://www.kaggle.com/datasets)  
Veri kümesinde film adı, yönetmen, oyuncular, açıklama ve tür gibi temel nitelikler yer almaktadır.

## Proje Aşamaları

1. Veri Analizi ve Görselleştirme (EDA)  
   - En fazla filme sahip yönetmenler tespit edilmiştir.  
   - En fazla sayıda filmde rol alan oyuncular belirlenmiştir.  
   - Oyuncu-yönetmen eşleşmelerine dair frekans analizi yapılmıştır (ısı haritası ile).  
   - Bir oyuncunun birlikte çalıştığı farklı yönetmen sayıları analiz edilmiştir.

2. Özellik Oluşturma (Feature Engineering)  
   - Film açıklamaları `TF-IDF` vektörizasyon ile sayısal hale getirilmiştir.  
   - Film türleri çoklu etiket (multi-label) formatından ayrıştırılarak modele entegre edilmiştir.  
   - Her film için açıklama + tür bilgisi birleştirilerek içerik temelli karşılaştırma yapılmıştır.

3. Öneri Sistemi (Recommendation Engine)  
   - Cosine Similarity metrikleri kullanılarak benzer içerikli filmler bulunmuştur.  
   - Kullanıcıdan alınan örnek bir film üzerinden sistem benzer filmleri önermektedir.  
   - Öneri çıktıları test edilmiştir ve mantıklı sonuçlar verdiği gözlemlenmiştir.

4. Streamlit Arayüz Planı (Yarım Kaldı)  
   - Bu sistem için interaktif bir arayüz (Streamlit) kurma planı yapılmıştır.  
   - Ancak bu kısım, Streamlit eğitimine ihtiyaç duyulduğu için askıya alınmıştır.  
   - Arayüz geliştirme daha sonraki versiyonlara bırakılmıştır.

## Kullanılan Kütüphaneler

pandas  
numpy  
scikit-learn  
matplotlib  
seaborn  


## Proje Yapısı

06_MovieRecommendation/  
├── data/  
│   └── movies.csv  
├── notebook/  
│   └── movie_recommendation.ipynb  
├── images/  
│   ├── en_fazla_filme_sahip_yonetmenler.png  
│   ├── en_fazla_filme_dahil_olan_oyuncular.png  
│   ├── oyuncu_yonetmen_eslesme_frekanslari.png  
│   └── en_fazla_farkli_yonetmenle_calisan_oyuncular.png  
├── README.md  
├── requirements.txt  
└── .gitignore

## Notlar

Bu proje, içerik temelli öneri sistemlerinin mantığını kavramak ve metin verisini işleyerek benzerlik karşılaştırması yapmak için hazırlanmıştır.  
Streamlit arayüzü henüz tamamlanmamıştır; ancak veri ve öneri sistemi bileşenleri hazırdır.  
Gelecek versiyonlarda kullanıcı etkileşimli arayüz eklenecektir.