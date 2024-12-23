# Deteksi_Objek
Berikut adalah kodingan untuk Algoritma Deteksi Objek :
```python

# Langkah 1: Clone repositori YOLOv5 dan instal dependensi
!git clone https://github.com/ultralytics/yolov5.git
%cd yolov5
!pip install -r requirements.txt

# Langkah 2: Upload gambar atau video yang akan dideteksi
from google.colab import files
uploaded = files.upload()

# Langkah 3: Jalankan deteksi objek
import os

# Pastikan file yang diupload ada di direktori saat ini
input_file = list(uploaded.keys())[0]  # Ambil nama file pertama yang diupload

# Jalankan deteksi menggunakan model YOLOv5 pre-trained (misalnya YOLOv5s)
!python detect.py --weights yolov5s.pt --img 640 --conf 0.25 --source {input_file}

# Langkah 4: Lihat hasil deteksi
from IPython.display import Image, display

# Temukan file hasil deteksi di folder "runs/detect/"
output_dir = 'runs/detect'
last_run = sorted(os.listdir(output_dir))[-1]  # Folder hasil terakhir
output_path = os.path.join(output_dir, last_run, input_file)

# Tampilkan hasil
display(Image(filename=output_path))

```
Hasil Output: 

![download (2)](https://github.com/user-attachments/assets/57212fe0-aa2d-4ccb-b6db-ddc0ff89cbf9)

Kode di atas mencakup langkah-langkah berikut:

1. Clone Repositori YOLOv5: Mengambil repositori YOLOv5 dari GitHub.
2. Install Dependensi: Menginstal semua paket Python yang diperlukan untuk menjalankan YOLOv5.
3. Unggah File: Memungkinkan Anda mengunggah gambar atau video untuk diproses.
4. Deteksi Objek: Menggunakan model YOLOv5 pra-terlatih untuk mendeteksi objek dalam file yang diunggah.
5. Lihat Hasil: Menampilkan hasil deteksi dalam format gambar.
