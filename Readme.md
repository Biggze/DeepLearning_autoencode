# Autoencoder untuk Transformasi Sketsa ke Gambar Berwarna

Proyek ini mengimplementasikan autoencoder convolutional untuk mengubah gambar sketsa (input) menjadi gambar berwarna (output).

## Dataset

Dataset terdiri dari pasangan gambar:
- Input: Gambar sketsa hitam putih (20+ gambar)
- Output: Gambar berwarna yang sesuai (20+ gambar)

Dataset dikumpulkan dari berbagai sumber dan diproses agar memiliki ukuran yang seragam (256x256 piksel).

Contoh pasangan gambar:
![Contoh Input](data/input/sample1.jpg)
![Contoh Output](data/output/sample1.jpg)

## Arsitektur Model

Autoencoder ini menggunakan arsitektur encoder-decoder dengan lapisan convolutional:

**Encoder:**
1. Conv2D (64 filters) + ReLU
2. MaxPooling
3. Conv2D (128 filters) + ReLU
4. MaxPooling
5. Conv2D (256 filters) + ReLU
6. MaxPooling (bottleneck)

**Decoder:**
1. Conv2D (256 filters) + ReLU
2. UpSampling
3. Conv2D (128 filters) + ReLU
4. UpSampling
5. Conv2D (64 filters) + ReLU
6. UpSampling
7. Conv2D (3 filters) + Sigmoid (output)

## Performa Model

Model ditraining dengan loss function MSE (Mean Squared Error)

## Contoh Hasil

Beberapa contoh hasil transformasi:

![Input 1](results/input_sample1.png)
![Output 1](results/output_sample1.png)

![Input 2](results/input_sample2.png)
![Output 2](results/output_sample2.png)

## Cara Menggunakan

1. Install dependencies:
```bash
pip install -r requirements.txt
