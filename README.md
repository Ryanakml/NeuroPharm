# NeuroPharm - Platform AI End-to-End untuk Penemuan Obat

Proyek ini adalah prototipe platform AI untuk memprediksi afinitas ikatan antara molekul ligan dan protein target, sebagai bagian dari alur kerja penemuan obat.

## Arsitektur

Platform ini terdiri dari tiga komponen utama:

1. **Jupyter Notebook (`drug_discovery_pipeline.ipynb`):** Berisi seluruh alur kerja dari pengumpulan data, pemodelan, hingga validasi docking, dengan penjelasan mendetail.
    
2. **API Backend (folder `api/`):** Sebuah API berbasis FastAPI yang menyajikan model GNN terlatih untuk prediksi.
    
3. **Dashboard Frontend (`app.py` dan folder `pages/`):** Aplikasi web interaktif berbasis Streamlit untuk interaksi pengguna dan visualisasi hasil.
    

## Teknologi yang Digunakan

- **Backend:** Python, FastAPI, PyTorch, PyTorch Geometric, Transformers (ESM-2)
    
- **Data:** RDKit, Biopython, Pandas, NumPy
    
- **Simulasi:** AutoDock Vina, Open Babel
    
- **Frontend:** Streamlit, stmol (py3Dmol)
    

## Instalasi

1. Clone repository:
    
    git clone https://github.com/your-username/ai-drug-discovery.git
    
    cd ai-drug-discovery
    
2. **Instal AutoDock Vina & MGLTools/OpenBabel:**
    
    - Ikuti petunjuk instalasi dari situs resmi mereka. Pastikan `vina` dan `obabel` dapat diakses dari command line.
        
3. Buat dan aktifkan environment conda:
    
    conda env create -f environment.yml
    
    conda activate drug_discovery_env
    

## Cara Menjalankan

1. Jalankan Jupyter Notebook:
    
    jupyter notebook drug_discovery_pipeline.ipynb
    
    - Jalankan sel-sel di dalam notebook untuk melatih model dan menghasilkan file-file yang diperlukan (misalnya, model yang disimpan, file PDBQT).
        
2. Jalankan API Backend:
    
    cd api
    
    uvicorn main:app --reload
    
    - API akan berjalan di `http://127.0.0.1:8000`.
        
3. Jalankan Dashboard Frontend:
    
    cd..
    
    streamlit run app.py
    
    - Buka browser dan akses `http://localhost:8501`.
        