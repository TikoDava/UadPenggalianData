# UasPenggalianData

# Pipeline Analisis Putusan MA Menggunakan Case-Based Reasoning (CBR)

Repositori ini berisi pipeline lengkap untuk menganalisis putusan Mahkamah Agung menggunakan pendekatan Case-Based Reasoning (CBR), termasuk tahapan preprocessing, representasi dokumen (TF-IDF & BERT), klasifikasi menggunakan SVM, dan evaluasi model.

## Struktur Tahapan

Pipeline dibagi ke dalam 5 notebook:

1. `Tahap1.ipynb` - Preprocessing dan ekstraksi metadata
2. `Tahap2.ipynb` - Labeling & klasifikasi pasal
3. `Tahap3.ipynb` - Representasi teks (TF-IDF dan BERT)
4. `Tahap4.ipynb` - Pelatihan dan evaluasi model klasifikasi (SVM)
5. `Tahap5.ipynb` - Pipeline akhir & visualisasi hasil

---

## Instalasi

1. **Clone repositori** (jika menggunakan GitHub):
    ```bash
    git clone https://github.com/username/nama-repo-cbr.git
    cd nama-repo-cbr
    ```

2. **Aktifkan virtual environment** (opsional tapi disarankan):
    ```bash
    python -m venv env
    source env/bin/activate  # Untuk Linux/macOS
    .\env\Scripts\activate   # Untuk Windows
    ```

3. **Instal dependencies**:
    Semua dependensi tersedia di file `requirements.txt`:
    ```bash
    pip install -r requirements.txt
    ```

---

## Cara Menjalankan

Seluruh pipeline dapat dijalankan secara berurutan di Google Colab atau lokal dengan Jupyter Notebook.

1. Jalankan notebook secara berurutan:
   - `Tahap1.ipynb` → `Tahap2.ipynb` → ... → `Tahap5.ipynb`
   - Pastikan path ke file dan folder (`/content/drive/MyDrive/ProyekA/...`) telah sesuai

2. Contoh struktur direktori data:
   ```
   /content/drive/MyDrive/ProyekA/
   ├── data/
   │   ├── raw/
   │   ├── CSV/
   │   ├── PDF/
   └── logs/
   ```

---

## Contoh Perintah di Notebook

Beberapa potongan kode penting dalam pipeline meliputi:

- **Preprocessing**:
    ```python
    clean_text = preprocess_dokumen(teks_pdf)
    ```

- **TF-IDF Vectorization**:
    ```python
    vectorizer = TfidfVectorizer(max_features=5000)
    X_tfidf = vectorizer.fit_transform(corpus)
    ```

- **Klasifikasi dengan SVM**:
    ```python
    svm = SVC(kernel='linear')
    svm.fit(X_train, y_train)
    ```

- **Evaluasi**:
    ```python
    print(classification_report(y_test, y_pred))
    ```

---

## Output yang Dihasilkan

- File CSV hasil klasifikasi
- File PDF, cleaning.log, prediction.csv, txt, cases.json, retrieval_matrics.csv, queries.jason
- Grafik evaluasi akurasi dan confusion matrix

---

## Catatan

- Pastikan file Google Drive Anda sudah sinkron dengan path yang benar
- Untuk pengguna Colab, jangan lupa mount drive:
    ```python
    from google.colab import drive
    drive.mount('/content/drive')
    ```

---

## Kontributor

- Tiko Dava Pratama – [tikodava@webmail.umm.ac.id]
- Muhammad Roofiif Aflah Robbaanii - [roofiifaflah@webmail.umm.ac.id]
---

## Lisensi

Repositori ini menggunakan lisensi bebas untuk keperluan akademik.

