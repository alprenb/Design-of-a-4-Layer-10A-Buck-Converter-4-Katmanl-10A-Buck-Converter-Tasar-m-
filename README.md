*4-Layer 10A Synchronous Buck Converter Design ⚡

Endüstriyel standartlara ve IPC-2152 üretim kısıtlarına azami düzeyde uyularak tasarlanmış, yüksek verimli ve 10A sürekli akım kapasiteli senkron düşürücü (buck) dönüştürücü PCB tasarımıdır. 

 📊 Elektriksel Özellikler
Tasarım konfigürasyonları ve komponent seçimleri Designer simülasyonları ile doğrulanmıştır.

   **Parametre Değerleri 
   Giriş Gerilimi (Vin) : 12V - 15V 
   Çıkış Gerilimi (Vout) : 5V 
   Maksimum Çıkış Akımı (Iout): 10A 
   Anahtarlama Frekansı (SW): 200 kHz
   Fiziksel Boyutlar: 70 mm x 70 mm 

 🛠️ PCB Katman Mimarisi (4-Layer Stack-Up)
Karmaşık güç akışını (Power Flow) ve hassas sinyal yollarını (Signal Integrity) izole etmek amacıyla 4 katmanlı (4-Layer) mimari tercih edilmiştir:

  L1 (Top Layer):** Ana güç bileşenleri (MOSFET, İndüktör), yüksek frekanslı SW düğümü ve Vin/Vout güç poligonlarının bulunduğu ana katman.
  L2 (Inner 1 - PGND Shield):  EMI kalkanlaması sağlamak ve dönüş akımlarına en düşük empedanslı yolu sunmak için kesintisiz Güç Toprağı (PGND) düzlemi.
  L3 (Inner 2 - Power Mirror): Yüksek akım taşıma kapasitesini artırmak için Vin ve Vout güç yollarının aynalanmış (mirrored) katmanı.
  L4 (Bottom Layer - Analog):  LM25145 kontrolcü entegresi, geri besleme (FB) gibi hassas analog sinyaller ve Analog Toprak (AGND) düzleminin bulunduğu izole katman.

 ⚙️ Donanımsal Kısıtlar ve EMC/Termal Yönetim

* PGND ve AGND İzolasyonu (Net-Tie): Gürültülü güç elemanlarının toprağı (PGND) ile hassas ölçüm yapan analog elemanların toprağı (AGND) birbirinden fiziksel olarak ayrılmış; toprak döngülerini (ground loops) engellemek için yalnızca U1 kontrolcüsünün altında bir " Net-Tie " ile tek noktadan birleştirilmiştir.
* SW Düğümü Optimizasyonu: 200 kHz'de anahtarlama yapan ve en büyük EMI kaynağı olan SW düğümü, kapasitif kuplajı önlemek adına minimum yüzey alanında tutulmuş ve altındaki L2 katmanı PGND ile kalkanlanmıştır. Altından hiçbir sinyal hattı geçirilmemiştir.
* Termal Yönetim (Via Stitching): Isınan güç MOSFET'leri ve endüktans için özel soğutucu (heatsink) bloklar kullanmak yerine, ısının bakır yüzeylere dağıtılması stratejisi izlenmiştir. IPC-2152 standartları referans alınarak (35µm PCB, 0.3mm via başına 1A), geniş Solid Region (poligon) kaplamalar atılmış ve bol miktarda termal via stitching uygulanmıştır.
* Dead-Time Kontrolü: İletim geçişleri sırasında oluşabilecek kısa devre (shoot-through) senaryolarını engellemek için kontrolcü üzerinden ölü zaman ayarları yapılmıştır.

 📂 Üretim Dosyaları (DFM Ready)
Tasarım Altium Designer ortamında elektriksel ve fiziksel Kural Denetimlerinden (DRC) sıfır hata ile geçmiştir. Tamamen üretime hazır (manufacturing-ready) formattadır:
* RS-274X Gerber Dosyaları (Top, Bottom, Inner Layers, Solder Mask, Silkscreen)
* NC Drill Dosyaları
* BOM (Bill of Materials) Listesi

---
📸 *Not: Projeye ait Altium 3D görsellerini, katman dağılımlarını (Layer Manager) ve WEBENCH şematik çıktılarını `images` klasöründe bulabilirsiniz.*
