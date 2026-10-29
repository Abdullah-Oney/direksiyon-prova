# Direksiyon Provası — B sınıfı sınav simülasyonu

Mobil ve masaüstü tarayıcıda çalışan, eğitim amaçlı bir sürüş sınavı provası. Orijinal arayüz, SVG çizimleri ve basitçe modellenmiş bir otomobil kullanır; herhangi bir gerçek araç markasının veya ticari oyunun modeli/varlığı kullanılmamıştır.

## İçerik

- **Bagaj kontrolü:** Stepne, kriko, bijon anahtarı, reflektör, ilk yardım çantası ve ek donanımlar arasından her oyunda rastgele 3 öğe seçilir.
- **Kaput kontrolü:** Motor, akü, yağ dolum kapağı/ölçüm çubuğu, soğutma sıvısı, cam yıkama suyu ve diğer parçalar arasından rastgele 3 öğe seçilir.
- **Kokpit ve göstergeler:** Sinyal, silecek, sis lambası, dörtlü ikaz, uyarı sembolleri, hız göstergesi ve park freniyle ilgili rastgele 3 soru gelir.
- **Perspektifli 3B sürüş:** Takip kameralı temsili otomobil, tekerlek ve direksiyon hareketi, park alanları, trafik konileri, hız sınırı ve yokuş geçişi.
- **Görevler:** Güvenli kalkış, paralel geri park, 25 metre geri gitme, geri giderken sağa L dönüş, dar alanda U dönüşü, yokuşta kalkış ve güvenli bitiş.
- **Puanlama:** Her bölümün doğru tamamlanması puan kazandırır; yanlış cevap, hız aşımı, koni teması, kemersiz kalkış denemesi ve diğer belirli hatalarda puan düşer. Hatalarda oyun doğrudan bitmez; parkuru tamamlamaya devam edebilirsin.
- **Dokunmatik kontrol:** Direksiyon, fren, gaz, vites, emniyet kemeri ve sinyal düğmeleri telefon ekranında kullanılabilir.

## Çalıştırma

### Yerel bilgisayarda

1. Arşivi çıkar.
2. `index.html` dosyasını güncel bir tarayıcıda aç. 3B bölüm için internet bağlantısı gerekir; Three.js kütüphanesi CDN üzerinden yüklenir.
3. Tarayıcıda yerel dosya kısıtlamasıyla ilgili sorun çıkarsa proje klasöründe basit bir HTTP sunucusu çalıştır:

   ```bash
   python -m http.server 8000
   ```

   Ardından `http://localhost:8000` adresini aç.

### GitHub Pages üzerinde yayınlama

1. GitHub'da yeni bir repository oluştur.
2. **Bu klasörün içindeki dosyaları** repository'nin kök dizinine yükle (`index.html`, `app.js`, `style.css`, `assets/` ve `README.md`). `index.html` bir alt klasöre gömülmemeli.
3. Repository'de **Settings → Pages** bölümüne gir.
4. **Deploy from a branch** seç; `main` ve `/ (root)` ayarını seçip kaydet.
5. GitHub Pages'in oluşturduğu web adresini aç. İlk yüklemede CDN'den Three.js'in gelmesi için internet erişimi gerekir.

## Kontroller

### Telefon

- **Sol / sağ ok düğmeleri:** Direksiyon
- **FREN / GAZ:** Basılı tuttukça fren veya gaz
- **R / N / 1:** Geri, boş, birinci vites. Vites değiştirmek için araç durmalı.
- **Kemer:** Emniyet kemerini tak / çıkar
- **Sol sinyal / Sağ sinyal:** İlgili sinyali aç/kapat
- **△:** Dörtlü ikaz
- **Far:** Kısa farı aç/kapat

### Bilgisayar

- **W / ↑:** Gaz
- **S / ↓ / Space:** Fren
- **A / ←, D / →:** Direksiyon
- **1 / N / R:** Vites
- **Q / E:** Sol / sağ sinyal
- **H:** Dörtlü ikaz
- **F:** Far
- **B:** Emniyet kemeri

## Önemli notlar

- Bu sürüm, oyunlaştırılmış bir eğitim prototipidir; MEB'in resmî sınav sistemi, onaylı parkur ölçüleri veya resmî puanlama formu değildir.
- Parkur ölçüleri ve puan kesintileri öğrenme amacıyla temsilî olarak ayarlanmıştır. Gerçek sınavda güncel MEB değerlendirme formu, komisyon yönlendirmesi, sınava girilen araç ve güzergâh esas alınır.
- Araç kumandaları ve motor bölümü parçalarının yerleri modelden modele değişebilir. Semboller ve yerleşim çizimleri öğretici örneklerdir; gerçek araç kullanma kılavuzuna bakılmalıdır.
- Fizik simülasyonu eğlenceli bir pratik içindir; gerçek araçta debriyaj, fren, direksiyon ve manevra çalışması yetkili sürücü eğitmeniyle yapılmalıdır.

## Proje dosyaları

- `index.html` — Ekranlar ve arayüz
- `style.css` — Mobil/masaüstü tasarım
- `app.js` — Rastgele testler, puanlama, 3B sahne, araç fiziği ve görev mantığı
- `assets/favicon.svg` — Projeye özel simge
