Final-Project-Kelompok-5-J.A.R.V.I.S
HR Analytics: Job Change of Data Scientists

Dataset: https://www.kaggle.com/datasets/arashnic/hr-analytics-job-change-of-data-scientists
Konteks dan Konten

Sebuah perusahaan yang bergerak di bidang Big Data dan Data Science ingin merekrut ilmuwan data di antara orang-orang yang berhasil lulus beberapa kursus yang diadakan oleh perusahaan. Banyak orang mendaftar untuk pelatihan mereka. Perusahaan ingin mengetahui kandidat mana yang benar-benar ingin bekerja untuk perusahaan setelah pelatihan atau mencari pekerjaan baru karena membantu mengurangi biaya dan waktu serta kualitas pelatihan atau perencanaan kursus dan kategorisasi kandidat. Informasi terkait demografi, pendidikan, pengalaman ada di tangan dari pendaftaran dan pendaftaran kandidat.

Dataset ini dirancang untuk memahami faktor-faktor yang menyebabkan seseorang meninggalkan pekerjaan saat ini untuk penelitian SDM juga. Dengan model yang menggunakan kredensial, demografi, data pengalaman saat ini, Anda akan memprediksi kemungkinan seorang kandidat untuk mencari pekerjaan baru atau akan bekerja untuk perusahaan, serta menginterpretasikan faktor-faktor yang memengaruhi keputusan karyawan.
Inspirasi

    Memprediksi probabilitas seorang kandidat akan bekerja untuk perusahaan
    Menafsirkan model sedemikian rupa sehingga menggambarkan fitur mana yang memengaruhi keputusan kandidat

Daftar Isi

    STAGE 1 EDA, INSIGHTS, AND VISUALIZATION
        Data Exploration
        Business-Insight
    STAGE 2 DATA PREPROCESSING
        Data Cleansing
        Feature Enginering
    STAGE 3 MACHINE LEARNING MODELLING AND EVALUATION
        Modelling
        Feature Importance

STAGE 1 EDA, INSIGHTS, AND VISUALIZATION
A. Data Exploration

Hasil Pengamatan:

    Data ini terdiri dari 19158 baris
    Sebagian besarnya adalah kategorikal
    Presentase missing value terbesar yaitu company_type, company_size, gender, dan major_discipline
    Tampak beberapa kolom masih memiliki null/missing values (Non-Null Count < jumlah baris
    Sepertinya terdapat kolom yang bisa ditindak lanjut : experience, company_size, dan last_new_job
    Data numerik tidak terdapat missing values

B. Business-Insight

Setelah dilakukan EDA, didapatkan beberapa bussiness insight :

    City Development Index :
        Kandidat dengan CDI rendah (0,66) cenderung memiliki keinginan untuk mencari pekerjaan baru
        Kandidat dengan CDI tinggi (0.9) cenderung sangat tidak tertarik mencari pekerjaan baru
    Training Hours :
        Kandidat dengan training hours kurang lebih 20 jam memiliki kecenderungan untuk mencari pekerjaan baru
        Dapat dilihat jumlah waktu course yang diikuti kandidat adalah sekitar 46-48 jam
        Semakin banyak jumlah training hours maka semakin sedikit kecenderungan untuk mencari pekerjaan baru
    Gender :
        88.9% kandidat laki-laki cenderung mencari pekerjaan baru
        Hanya 9.62% kandidat perempuan yang cenderung akan mencari pekerjaan baru
    Company Type :
        Kandidat dari Company Type Pvt Ltd paling banyak ingin mencari pekerjaan baru, yaitu sebesar 74.17%
    Education Level :
        Kandidat dengan education level graduate paling banyak mencari pekerjaan baru yaitu sebesar 69.44%
    Major Discipline :
        Kandidat dengan Major discipline STEM (Science Technology Engineering Math) paling banyak mencari pekerjaan baru yaitu sebesar 89.66%
    Relevant Experience :
        61.98% kandidat dengan relevant experience cenderung akan mencari pekerjaan baru
        38.02% kandidat dengan non-relevant experience cenderung akan mencari pekerjaan baru
    Experience - kandidat yang cenderung akan mencari pekerjaan baru adalah kandidat dengan total experience:
        Di atas 20 tahun experience (10.58%)
        3 tahun experience(9.61%)
        4 tahun experience(10.05%)
    Last New Job :
        Kandidat yang memiliki perbedaan 1 tahun antara pekerjaan lama dan pekerjaannya sekarang cenderung akan mencari pekerjaan baru (45.97%)

STAGE 2 DATA PREPROCESSING
A. Data Cleansing

    Handle Missing Values: mengisi kolom kosong menggunakan mice iterative imputer
    Handle Duplicated Data: menghapus 49 row yang duplicate
    Handle Outlier:
        Outlier Detection Technique: menggunakan 3 teknik yaitu: Visualizing the Data, Z Score, dan IQR Method
        Dealing with Outliers: menggunakan Imputation
    Feature Transformation:
        Log Transformation: feature training_hours memiliki distribusi right-skewed, perlu diubah ke distribusi normal
        Standarisasi dan Normalisasi: feature training_hours, feature city_development_index karena distribusi datanya sudah mendekati normal
    Feature Encoding: feature kategorikal yang memiliki urutan dan feature yang memiliki dua unique value diubah menjadi numerik dengan pendekatan Label Encoder. Sedangkan feature kategorikal lainnya diubah menggunakan teknik One Hot Encoding
    Handle Class Imbalance: menggunakan teknik SMOTE dan SVM SMOTE

B. Feature Enginering

    Feature Selection: dari hasil heatmap correlation, maka disimpulkan bahwa feature yang akan dihapus adalah enrollee_id karena feature ini merupakan unique keys, sehingga kita tidak memerlukannya dalam proses model machine learning
    Feature Extraction: kita dapat melakukan feature extraction pada kolom yang cardinal valuenya tinggi yaitu experience dan company size dengan melakukan pengelompokan yang lebih sederhana
    Additional Feature
        Backgroud kandidat: Age, Marital status, Number of dependences, Previous Salary, Kenaikan gaji, Rata-rata jam kerja, GPA
        Training Score: Training satisfaction, Training absent, Last training evaluation

STAGE 3 MACHINE LEARNING MODELLING AND EVALUATION
A. Modelling
Base Model

Setelah dilakukan Modeling, didapatkan hasil:

  ![image](https://user-images.githubusercontent.com/84758353/180401623-74442e41-0269-4de0-9c0f-f51c6da24563.png)
Model Hyperparameter Tuning



B. Feature Importance
![image](https://user-images.githubusercontent.com/84758353/180401902-3b9bc045-8d7d-4e52-b635-3c3c26cbcb5a.png)

Rekomendasi:
![image](https://user-images.githubusercontent.com/84758353/180402287-c5d737e7-7c4d-4612-9509-a984d483b3c9.png)


