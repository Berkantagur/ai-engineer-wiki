Problem 1: Windows üzerine WSL ile ilk kurulumdan sonra Ubuntu açılıp kapanıyor, E_UNEXPECTED hatası veriyor. 
Kayıt Tarihi: 22.10.2026 15:44
Kök Neden: WSL eski sürümde takılı kalmış.
Çözüm: wsl --update   ->   wsl --shutdown   ->   wsl -d Ubuntu
Notlar: Ben bu problemi bu şekilde çözdüm ama öncesinde BIOS'um üzerinde sanallaştırma açık mı kontrol ettim. Eğer kapalı olsaydı onu açmak gerekecekti. Çünkü E_UNEXPECTED hatası bu iki nedenden biri dolayısıyla olur.
