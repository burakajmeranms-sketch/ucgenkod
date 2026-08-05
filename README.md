ÜÇGENKOD V5 — Gerçek SaaS / Cloudflare

Bu paket bilgisayarsız kurulum için klasörsüz hazırlanmıştır. GitHub'a yalnızca 4 kök dosya yüklenir:
- worker.js
- wrangler.jsonc
- package.json
- README.md

Cloudflare Workers > Create application > Import a repository yoluyla GitHub deposunu bağlayın. Deploy komutu varsayılan npx wrangler deploy olarak kalabilir. Wrangler 4.68+ D1 ve R2 bindinglerini otomatik provision eder.

V5 özellikleri:
- Kayıt / giriş / HttpOnly oturum çerezi
- Her kullanıcıya ayrı işletme ve kalıcı slug
- D1 üzerinde kategori/ürün/ayarlar/veri
- R2 üzerinde logo ve ürün görselleri
- Kalıcı /m/isletme-slug menü adresi
- Kalıcı QR SVG
- Çok cihazlı panel senkronizasyonu
- Menü görüntülenme istatistiği
- Tema paletleri

Not: Ödeme/abonelik sağlayıcısı henüz bağlanmamıştır. Veritabanında plan alanı hazırlanmıştır.


## V5.1 HOTFIX
- Worker adı `ucgenkod` olarak eşitlendi.
- `/api/health` D1/R2 ve şema durumunu gösterir.
- `/api/diag` D1 tablolarını doğrular.
- Kayıt akışı aşama bazlı hata teşhisi ve güvenli temizlik içerir.
- Geçici olarak API hataları `requestId`, `stage` ve kısa `detail` döndürür; sorun çözüldükten sonra ayrıntı alanı kaldırılabilir.


## V5.2 Signup Fix
- Kayıt hatası artık arayüzde `stage · detail` olarak görünür.
- Oturum bitiş tarihi SQLite fonksiyonuna bırakılmadan Worker tarafından ISO tarih olarak yazılır.
- PBKDF2 maliyeti mobil/Workers uyumu için 120.000 iterasyona ayarlandı.
- `/api/diag/schema` temel D1 tablolarının kolonlarını gösterir.
- Worker adı `ucgenkod` ile eşitlendi.


## V5.3 PBKDF2 Fix
- Cloudflare Workers PBKDF2 sınırına uyum için iterasyon sayısı 120000'den 100000'e indirildi.
- Kayıt ve giriş akışındaki diğer V5.2 düzeltmeleri aynen korundu.

## V5.4 Studio Pro
- İşletme paneli baştan tasarlandı: premium mobil/desktop Studio arayüzü.
- D1, R2, kayıt, giriş, kalıcı menü ve QR backend davranışı değiştirilmedi.
- Ürün işlemlerine kaydetme durumu, boyut kontrolü ve daha güvenli hata geri bildirimi eklendi.
- Görünüm ekranına gerçek canlı menü iframe önizlemesi eklendi.
- Mobil Safari için safe-area, bottom navigation ve modal/klavye davranışları iyileştirildi.

## V5.5 Studio Final Polish
- Üst marka alanındaki bozuk şekil giderildi; gerçek üçgen marka işareti kullanıldı.
- Mobil kartlar, boşluklar ve tipografi daha kompakt hale getirildi.
- Alt navigasyon inceltildi; içerik alanı büyütüldü.
- Ürün/kategori kartları ve hızlı işlemler daha az dikey alan kullanıyor.
- Backend/D1/R2/QR işlevlerine dokunulmadı.

## V5.9 Scannable ÜÇGEN QR
- Bozuk/standart dışı üçgen QR motorları kaldırıldı.
- QR matrisi eksiksiz korunur ve ECC-H kullanılır.
- Veri modülleri üçgen biçiminde çizilir.
- Finder pattern'lar standart konum ve geometride bırakılır; telefon kamerası uyumluluğu korunur.
- Merkezde küçük üçgen marka işareti bulunur.
- `/api/qr/:slug` standart yedek QR olarak korunur.

## V6.0 Production Final
- QR veri matrisi ve finder pattern'lar eksiksiz korunur.
- Veri hücreleri iki üçgen parçayla neredeyse tam hücre doluluğunda çizilir.
- ECC-H kullanılır ve merkez marka işareti küçük tutulur.
- Temsilî `/m/test-cafe` URL'si üzerinde decode doğrulaması yapıldı:
  - native boyut: başarılı
  - 600 / 480 / 360 / 300 / 240 px: başarılı
  - ±4° ve ±8° rotasyon: başarılı
  - hafif blur: başarılı
- Standart QR yedeği `/api/qr/:slug` olarak korunur.
- D1, R2, auth, ürün ve menü altyapısına dokunulmadı.

## V6.1 Signature Site
- QR & Yayın ekranı onaylanan siyah/altın üçgen ürün görseline göre yeniden tasarlandı.
- Üçgen plaka, üç köşe işaretleri, beyaz nokta dokusu, merkez ÜÇGENKOD imzası ve mermer taban hissi eklendi.
- Taranabilir QR çekirdeği, üçgen objenin içinde güvenli biçimde korunur.
- D1, R2, auth, ürün, kategori ve müşteri menüsü backend'i değiştirilmedi.

## V6.2 Logo QR Final
- QR standardı kare matris olarak korunur.
- ECC-H hata düzeltme seviyesi kullanılır.
- Üçgen ÜÇGENKOD logosu QR'ın merkezine sabit yerleştirilir.
- Logonun altında küçük 'ÜÇGENKOD' yazısı bulunur.
- Merkez marka alanı konservatif tutulur; üç finder pattern ve quiet zone korunur.
- `/api/qr/:slug` standart yedek QR olarak kalır.

## V6.3 Clean Logo QR Final
- Eski büyük üçgen iskelet, üçgen plaka ve ekstra QR gözleri QR & Yayın ekranından tamamen kaldırıldı.
- Ekranda tek bir standart kare QR gösterilir.
- QR merkezinde küçük üçgen ÜÇGENKOD logosu ve küçük ÜÇGENKOD yazısı bulunur.
- ECC-H, quiet zone ve üç finder pattern korunur.
- Standart yedek QR endpoint'i korunur.

## V7.0 Red / White / Black Elite
- Tema kırmızı, beyaz ve siyah premium kimliğe geçirildi.
- Tam ekran kırmızı intro eklendi.
- Intro merkezinde küçük ÜÇGENKOD üçgen logosu bulunur.
- Altında %0 → %100 animasyonlu sayaç ve ince yükleme çizgisi çalışır.
- Panel kartları, navigasyon, formlar ve QR ekranı koyu elit tasarıma uyarlandı.
- Backend, D1, R2, auth, ürün ve QR üretim mantığına dokunulmadı.
