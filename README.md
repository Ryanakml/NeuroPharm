# 1) Markdown cell (penjelasan singkat)

## Setup environment (venv) dan instal dependency

Gunakan virtual environment agar dependency terisolasi.
Perintah di bawah membuat `./venv`, mengaktifkannya, lalu meng-install semua paket dari `requirements.txt` menggunakan binary `./venv/pip`.

**Catatan:** Jangan memanggil `pip install ...` langsung (global). Selalu gunakan `./venv/bin/pip` (Linux/mac) atau `./venv\Scripts\pip.exe` (Windows).


---

# 2) Bash cell (Linux / macOS)

## 1) buat venv
python3 -m venv ./venv

## 2) aktifkan (opsional saat manual)
source ./venv/bin/activate

## 3) upgrade pip/setuptools/wheel pakai python dari venv
./venv/bin/python -m pip install --upgrade pip setuptools wheel

if there is a mistake delete it by

rm -rf venv

## 4) tulis requirements.txt (atau ganti dengan file yang sudah ada)
cat > requirements.txt << 'REQ'

Salin semua nya yang di bawah ini

```
# Core data + science
pandas>=1.5
numpy>=1.24
scikit-learn>=1.2
matplotlib>=3.7
ipywidgets>=8.0

# Cheminformatics & bio
rdkit-pypi>=2023.9.5
biopython>=1.80
chembl-webresource-client>=0.10
openbabel

# ML / DL
torch>=2.0
torchvision
torchaudio
### NOTE: torch-geometric installation often requires platform-specific wheels
torch-geometric
transformers>=4.35

# Utilities
tqdm
xgboost
jupyter
streamlit
nglview
stmol

REQ
```

## 5) install dari venv pip (gunakan -r untuk production)
./venv/bin/pip install -r requirements.txt

---

# 3) PowerShell / Windows (cmd / PS)

## PowerShell
python -m venv .\venv
## aktifkan
.\venv\Scripts\Activate.ps1    ## (atau .\venv\Scripts\activate.bat untuk cmd)

## upgrade pip
.\venv\Scripts\python.exe -m pip install --upgrade pip setuptools wheel

## install dari requirements
.\venv\Scripts\pip.exe install -r requirements.txt


⸻

# 4) Catatan penting & tips
	•	torch-geometric sering perlu wheel spesifik (CUDA/CPU). Jika kamu pakai CUDA, install sesuai instruksi PyG: gunakan perintah yang cocok dengan versi torch dan CUDA (lihat docs resmi PyG). Jika tidak yakin, pakai CPU wheel.
	•	rdkit-pypi adalah cara cepat install RDKit lewat pip; untuk performa/compatibility lebih baik gunakan conda jika mengalami masalah.
	•	AutoDock Vina dan OpenBabel bukan paket pip murni — ikuti instalasi resmi mereka (binaries) dan pastikan vina & obabel berada di PATH. Contoh singkat:
	•	macOS: brew install vina open-babel
	•	Ubuntu: sudo apt install autodock-vina openbabel (atau unduh release dari situs resmi)
	•	Jika kamu menggunakan container / server tanpa GUI, pastikan dependency native terinstall (libglu, etc.) untuk tools visualisasi.

⸻

# 5) Cara menambahkan ke notebook secara otomatis (opsional)

Kamu bisa jalankan cell Python ini untuk menulis requirements.txt dari notebook:

requirements_text = open('requirements.txt').read()
print(requirements_text)