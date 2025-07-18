# AC-DC Güç Kaynağı (115-250V AC -> 24V 5A)

Bu proje, 115-250V AC girişten 24V DC / 5A çıkış sağlayan bir **izole AC-DC güç kaynağı** devresidir. Yüksek güç yoğunluğu, güvenlik ve verimlilik odaklı olarak tasarlanmıştır.

## 📦 Özellikler

- **Giriş Gerilimi:** 115V - 250V AC
- **Çıkış Gerilimi:** 24V DC
- **Çıkış Akımı:** 5A (maksimum)
- **Topoloji:** Half-Bridge
- **Güvenlik ve Koruma Özellikleri:**
  - Yüksek sıcaklık koruması
  - Sigorta (Fuse)
  - Gaz Deşarj Tüpü (GDT)
  - EMI/RFI Giriş Filtresi
  - Aşırı Gerilim için Shutdown devresi (>27V)

## ⚡ Tasarım Bileşenleri

### Güç Faktörü Düzeltme (PFC)
- **Kontrolcü:** L6563
- **Fonksiyon:** Giriş AC sinyalini düzeltir ve 400V DC seviyesine çıkarır.

### Anahtarlama Aşaması
- **Topoloji:** Half-Bridge Konfigürasyonu
- **Kontrolcü:** L6599D
- **MOSFET’ler:** STP20H100
- **Trafo:** Yalıtımlı ve yüksek frekanslı dönüşüm için tasarlanmıştır.

### Çıkış Doğrultma ve Regülasyon
- **Çıkış Doğrultması:** STP20H100 MOSFET ile yüksek verimli doğrultma
- **Geribildirim (Feedback):**
  - **Optokuplör:** LTV-817S ile izole çıkış voltajı kontrolü
  - **Shutdown Devresi:** BC847 transistörü ile 27V üzerindeki çıkışlar için devreyi kapatma

## 🔥 Koruma ve Filtreleme

- **Giriş Filtresi:** EMI ve RFI bastırma için LC filtre
- **Sigorta ve GDT:** Aşırı akım ve yıldırım darbelerine karşı koruma
- **Yüksek Sıcaklık Koruması:** Termistör/NTC ile izleme

## 📐 PCB Özellikleri

- **Katman Sayısı:** 2 katman
- **İzole Alanlar:** Yüksek gerilim ve düşük gerilim bölgeleri arasında güvenli izolasyon
- **Soğutma:** Güç bileşenleri için yeterli soğutma alanı ve heatsink montaj noktaları

## 🛠 Kullanım

1. **Bağlantı:**
   - Giriş: L, N, Toprak terminalleri üzerinden AC şebekeye bağlayın.
   - Çıkış: +24V ve GND terminallerinden yük bağlantısı yapın.

2. **Çalıştırma:**
   - Güçü açmadan önce bağlantıları kontrol edin.
   - İlk açılışta boşta test yapılması önerilir.

3. **Koruma Devreleri:**
   - Çıkış aşırı gerilim durumunda (>27V) devre BC847 tarafından kapatılır.
   - Aşırı akım veya kısa devre durumunda sigorta atar.

## 📁 Dosyalar

- `AC-DC Güç Kaynağı.kicad_pro` – KiCAD proje dosyası
- `AC-DC Güç Kaynağı.kicad_sch` – Devre şeması
- `AC-DC Güç Kaynağı.kicad_pcb` – PCB yerleşim dosyası
- `BOM.csv` – Parça listesi
- `Fabrikation_Toolkit` – Üretim için gerber dosyaları

## ⚠️ Dikkat

> Yüksek gerilim içeren bu devre **hayati tehlike** arz eder. Lütfen yalnızca deneyimli kişiler tarafından çalıştırılsın.

## 📜 Lisans

Bu proje açık kaynaklıdır ve kişisel/akademik kullanım için ücretsizdir.
