# Donanım

Kayıt tarihi: 22.10.2026
Bilgisayar: ASUS ROG Zephyrus G14 (Ryzen 5800H, 8 çekirdek / 16 iş parçacığı)

## GPU
- Model: NVIDIA GeForce RTX 3050 Laptop GPU
- VRAM: 4096 MiB (4 GB)
- Sürücü (Windows tarafı, KMD): 610.62
- nvidia-smi sürümü: 610.43.02
- Güç sınırı: 75 W

Özet komutu:
nvidia-smi --query-gpu=name,memory.total,driver_version --format=csv

## Bu ne anlama geliyor
- Bir modelin her 1 milyar parametresi 16-bit hassasiyette yaklaşık 2 GB yer kaplar.
  Üstüne çalışma sırasında KV cache ve ara hesaplamalar için ek bellek gerekir.
- 4 GB VRAM ile yerelde rahat çalışabileceklerim:
  - 16-bit: 0,5–1,5 milyar parametrelik modeller
  - 4-bit quantize: 3 milyar parametreye kadar
- Daha büyük modeller (7B ve üstü) için saatlik bulut GPU kiralayacağım.

## CUDA notu
- nvidia-smi'deki "CUDA UMD Version: 13.3", bilgisayarda CUDA kurulu olduğu anlamına gelmiyor.
- Bu sayı, sürücünün desteklediği EN YÜKSEK CUDA sürümü.
- PyTorch gibi kütüphaneleri kurarken seçtiğim CUDA sürümü bundan yüksek olmamalı.

## Ortam notu (WSL2)
- NVIDIA sürücüsü sadece Windows'a kurulu. WSL2 içindeki Linux GPU'yu bu sürücü üzerinden görüyor.
- Ubuntu'nun içine ayrıca NVIDIA sürücüsü KURMUYORUM, ortamı bozar.
- Linux'ta nvidia-smi'nin çalışması, GPU'nun WSL2'den erişilebilir olduğunun kanıtı.

## Ham çıktı
```
Thu Oct 22 21:21:57 2026       
+-----------------------------------------------------------------------------------------+
| NVIDIA-SMI 610.43.02              KMD Version: 610.62        CUDA UMD Version: 13.3     |
+-----------------------------------------+------------------------+----------------------+
| GPU  Name                 Persistence-M | Bus-Id          Disp.A | Volatile Uncorr. ECC |
| Fan  Temp   Perf          Pwr:Usage/Cap |           Memory-Usage | GPU-Util  Compute M. |
|                                         |                        |               MIG M. |
|=========================================+========================+======================|
|   0  NVIDIA GeForce RTX 3050 ...    On  |   00000000:01:00.0 Off |                  N/A |
| N/A   46C    P0              9W /   75W |       0MiB /   4096MiB |      0%      Default |
|                                         |                        |                  N/A |
+-----------------------------------------+------------------------+----------------------+

+-----------------------------------------------------------------------------------------+
| Processes:                                                                              |
|  GPU   GI   CI              PID   Type   Process name                        GPU Memory |
|        ID   ID                                                               Usage      |
|=========================================================================================|
|  No running processes found                                                             |
+-----------------------------------------------------------------------------------------+
```
