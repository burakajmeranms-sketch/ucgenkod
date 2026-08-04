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
