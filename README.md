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

---

AC-DC Power Supply (115-250V AC -> 24V 5A)
This project is an isolated AC-DC power supply circuit that converts 115-250V AC input to 24V DC / 5A output. It is designed for high power density, safety, and efficiency.

📦 Features
Input Voltage: 115V - 250V AC

Output Voltage: 24V DC

Output Current: 5A (maximum)

Topology: Half-Bridge

Safety and Protection Features:

Over-temperature protection

Fuse protection

Gas Discharge Tube (GDT)

EMI/RFI input filter

Shutdown circuit for overvoltage (>27V)

⚡ Design Components
Power Factor Correction (PFC)
Controller: L6563

Function: Rectifies the AC input and boosts it to 400V DC.

Switching Stage
Topology: Half-Bridge Configuration

Controller: L6599D

MOSFETs: STP20H100

Transformer: Designed for isolated, high-frequency power conversion.

Output Rectification and Regulation
Output Rectification: High-efficiency rectification using STP20H100 MOSFET

Feedback:

Optocoupler: LTV-817S for isolated output voltage control

Shutdown Circuit: BC847 transistor to shut down the system when output exceeds 27V

🔥 Protection and Filtering
Input Filter: LC filter for EMI and RFI suppression

Fuse and GDT: Protection against overcurrent and lightning surges

Over-Temperature Protection: Monitored via Thermistor/NTC

📐 PCB Features
Layer Count: 2 layers

Isolation Zones: Safe separation between high-voltage and low-voltage areas

Cooling: Sufficient area for heatsinks and power component thermal management

🛠 Usage
Connections:

Input: Connect to AC mains via L, N, and Ground terminals.

Output: Connect the load to +24V and GND terminals.

Operation:

Verify all connections before powering on.

Recommended to perform no-load testing on initial startup.

Protection Circuits:

The BC847 transistor shuts down the system if the output voltage exceeds 27V.

The fuse blows in case of overcurrent or short circuit.

📁 Files
AC-DC Güç Kaynağı.kicad_pro – KiCAD project file

AC-DC Güç Kaynağı.kicad_sch – Schematic file

AC-DC Güç Kaynağı.kicad_pcb – PCB layout file

Bomlist.xlsx – Bill of Materials

Fabrikation_Toolkit – Gerber files for manufacturing

⚠️ Warning
This circuit involves high voltages and poses a risk of electric shock. It should only be operated by experienced individuals.

📜 License
This project is open-source and free for personal/academic use.
