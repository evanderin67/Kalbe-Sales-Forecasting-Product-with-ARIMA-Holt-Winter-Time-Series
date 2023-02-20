# Plant Nutrition Prediction with Supervised Machine Learning

Project ini memiliki tujuan untuk membuat model *sales forecast* untuk Category A, Category B, Product A1, Product A2, Product B1 & Product B2

# Penjelasan File pada Github

Repository ini terdiri dari beberapa file yaitu :

- Folder `deployment` = Berisi mengenai file yang digunakan untuk *deployment* ke `HuggingFace`(berisi model, python application dll)
- `kalbe_ftds_rmt17_evan_derin_ihsanudin.ipynb` = File ini adalah *notebook* utama yang digunakan untuk pengerjaan model (dari data *exploration*, data *cleaning*, *building model* hingga *model evaluation*)
- `inferencing_kalbe_ftds_rmt17_evan_derin_ihsanudin.ipynb`= File ini adalah *notebook* yang digunakan untuk *testing inference*. Inferencing dilakukan pada *notebook* terpisah **untuk membuktikan bahwa model dapat berjalan pada *notebook* yang *clean* dari variabel**
- `url.txt` = File ini berisi *deployment* ke `HuggingFace`

# Summary singkat Project

Alur dari *project* ini adalah yang pertama EDA (*Exploratory Data Analysis*) untuk mengetahui gambaran dasar dari *dataset*. Kemudian dilakukan *cleaning* dan *preprocessing* terhadap *dataset*. Kemudian saya melakukan *modeling* dengan rincian sebagai berikut :
    - Kategori A : ARIMA (`MAE` 3.69)
    - Kategori B : ARIMA (`MAE` 194.48)
    - Produk A1 : ARIMA (`MAE` 7.4)
    - Produk A2 : ARIMA (`MAE` 1.73)
    - Produk B1 : Holt Winter (`MAE` 120.9)
    - Produk B2 : Holt Winter (`MAE` 118.66)

# Kesimpulan Project

- Sebelum membuat model maka saya perlu mengetahui dan eksplorasi mengenai data yang tersedia. Hasil eksplorasi adalah sebagai berikut :
    1. Produk Kategori A memiliki rata-rata sales 1.415 dan *range* 1.100 - 1.767
    2. Produk Kategori B memiliki rata-rata sales 1.716 dan *range* 0 - 6.435
    3. Produk A1 memiliki rata-rata sales 150 dan *range* 100 - 210
    4. Produk A2 memiliki rata-rata sales 1.265 dan *range* 1.000 -1.558,76
    5. Produk B1 memiliki rata-rata sales 1.063 dan *range* 970 - 1.734
    6. Produk B2 memiliki rata-rata sales 2.761,88 dan *range* 10 - 4.980,66

- Kemudian saya membuat 6 model, berikut hasil evaluasi dari 6 model tersebut

    1. Model Forecast Sales Kategori A
        - Model dapat memodelkan trend dan seasonality pada dataset 
        - Model ini memiliki error sejumlah +- 3,69. **Error ini termasuk kecil karena *range* sales pada kategori A berkisar antara 1.100-1.767**
        - Model cenderung memprediksi sales lebih tinggi dari nilai aktual

    2. Model Forecast Sales Kategori B
        - Model dapat memodelkan trend dan seasonality pada dataset 
        - Model ini memiliki error sejumlah +- 194,48. **Error ini termasuk kecil karena *range* sales pada kategori B berkisar antara 970-6.435**
        - Model cenderung memprediksi sales lebih tinggi dari nilai aktual

    3. Model Forecast Sales Produk A1
        - Model dapat memodelkan trend dan seasonality pada dataset 
        - Model ini memiliki error sejumlah +- 7,4. **Error ini termasuk kecil karena *range* sales pada produk A1 berkisar antara 100-210**
        - Model cenderung memprediksi sales lebih tinggi dari nilai aktual

    4. Model Forecast Sales Produk A2
        - Model dapat memodelkan trend dan seasonality pada dataset 
        - Model ini memiliki error sejumlah +- 1,73. **Error ini termasuk kecil karena *range* sales pada produk A2 berkisar antara 1.000-1.558**
        - Model cenderung memprediksi sales lebih rendah dari nilai aktual

    5. Model Forecast Sales Produk B1
        - Model sudah dapat menangkap seasonal dari dataset akan tetapi model ini masih belum dapat menangkap trend dengan baik
        - Model ini memiliki error sejumlah +- 120,9. **Error ini termasuk kecil karena *range* sales pada produk B1 berkisar antara 970-1.734**
        - Model cenderung memprediksi sales lebih tinggi dari nilai aktual


    6. Model Forecast Sales Produk B2
        - Model sudah dapat menangkap seasonal dari dataset akan tetapi model ini masih belum dapat menangkap trend dengan baik
        - Model ini memiliki error sejumlah +- 118,66. **Error ini termasuk kecil karena *range* sales pada produk B2 berkisar antara 10-4.980**
        - Model cenderung memprediksi sales lebih tinggi dari nilai aktual

- Kemudian untuk *continuous improvement* :

    Improvement Model
    1. Untuk mengontrol *trend* dan *seasonality* maka produk bisa diklasifikasikan lebih dalam lagi ke kategori *fast moving* dan *slow moving*. Sebagai contoh ada produk kategori A *Slow Moving* dan produk kategori A *fast moving*. Untuk datanya lebih baik dipisah, agar saat modelling tidak ada kerancuan saat pembacaan *trend* dan *seasonality*
    2. Untuk produk yang *slow moving* bisa menggunakan data *dummy* hasil konsultasi dengan pakar domain atau data kompetitor. Karena jika data kurang (cth produk B2), maka dikhawatirkan *forecast* tidak merepresentasikan aktual *sales*

    Business Insight
    1. Product yang memiliki prediksi sales tinggi, bisa dipersiapkan dari segi *raw material*, *level buffer stock*, sistem *supply chain* yang tepat agar dapat merespon permintaan *market*. Sehingga tidak kehilangan *customer* karena produk tidak tersedia
    2. Kemudian untuk product yang memiliki prediksi sales rendah, juga perlu hati-hati dalam pengaturan level *stock material*, MOQ produksi dll. Perlu juga ada validasi antara *demand* vs *shelf life material & product*, untuk memastikan apakah ada potensi *expired* sebelum produk habis atau tidak